<script lang="ts">
    import { page } from "$app/stores"
    import Data from "$lib/_data"
    import store from "$lib/persistentStore"
    const {src, brand , model, type, id} = Data.find(x => x.id == Number($page.params.product)) || {}

    $store = [...$store, Number(id)]
</script>

<section id="container">
    <img {src} alt="">
    <div>
        <h2>{model}</h2>

        <ul>
            {#if type == "piano"}
                <li>tip : Piyano</li>
            {:else if type == "guitar"}
                <li>tip : Gitar</li>
            {:else}
                <li>tip : Keman</li>
            {/if}
            <li>Marka : {brand} </li>
            <li>Model : {model}</li>
        </ul>
    </div>
</section>


<style lang="less">
    #container {
        display: flex;
        flex-direction: row ;

        img {
            width: 402px;
        }

        div {
            padding: 10px 2rem;
            ul {
                padding: 0;
                list-style: none;
                li {
                    margin-bottom: 1rem;
                }
            }
        }
    }
</style>