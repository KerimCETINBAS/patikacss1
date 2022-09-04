<script lang="ts">
    export let header:string = ""
    export let content:string = ""
    export let id: number
</script>

<div id="card">
    <div id="card-img-container">
      <a href="/product/{id}">
        <img src="{$$props["src"]}" alt="{$$props["alt"]}">
      </a>
    </div>

    <h3>
        {header}
    </h3>

    <p>
        {content}
    </p>
</div>



<style lang="less">
    div#card {
        background-color: palevioletred;
        width: 100%;
        margin: 0;
        #card-img-container {
            display: inline-block;
            width: 100%;
            margin: 0;
            img {
                padding: 10px;
                width: calc(100% - 20px);
                height: 220px;
                object-fit: cover;
                margin: 0;
            }
        }

        h3 {
            padding: 0 10px;
            color: white;
        }

        p {
            padding: 0 10px;
            color: pink;
        }
    }
</style>