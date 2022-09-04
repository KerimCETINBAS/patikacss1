<script>
import InsturmentCard from "$lib/components/insturmentCard.svelte";
import Section from "$lib/components/section.svelte";
import _ from "underscore"
import Data from "$lib/_data"
import store from "$lib/persistentStore"

</script>

<Section>
    <strong slot="header">Super Muzik Aletlerine Hos Geldiniz</strong>
    <span slot="content">Sitemizde bir cok kategoride bir birinden kaliteli muzik aletlerine ulasabilirsiniz!</span>
</Section>
<section>
    <h2>
        En cok begenilenler
    </h2>

    <div class="favorites">
        {#each  _.sample(Data, 4) as {src, brand, model, id}}
            <InsturmentCard {src}  {id} header={brand}, content={model} />
        {/each}
    </div>
</section>



<section>
    <h2>
        Baktiginiz Urunler
    </h2>
    <div class="favorites">
        {#each Data.filter(x => $store.includes(x.id))  as {src, brand, model, id}}
           
            <InsturmentCard {src}  {id} header={brand}, content={model} />
          


        {:else}
            <span>Henuz hic bir urune bakmadiniz</span>
        {/each}
    </div>
</section>
<style lang="less">
    h2 {
        font-size: 1rem;
        font-weight: 600;
        margin-top: 2rem;
    }
   
   .favorites {
    display: grid;
    gap: 2rem;
    grid-template-columns: 1fr 1fr 1fr 1fr;
   }
</style>