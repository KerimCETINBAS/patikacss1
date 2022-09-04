
<div id="container">
    <nav>
        <ul>
            <li><a href="/products">Tumu</a></li>
            <li><a href="/products/guitar">Gitar</a></li>
            <li><a href="/products/piano">Piyano</a></li>
            <li><a href="/products/violin">Keman</a></li>
        </ul>
    </nav>

    <div id="content">
        <slot />
    </div>
</div>



<style lang="less">
    #container {
        display: flex;
        flex-direction: row;
  
        nav {
            padding: 0;
            margin: 0;
            ul {
                list-style: none;
                padding: 0;
                li a {
                    display: inline-block;
                    padding: .4rem 2rem;
                }
            }

            background: rgb(214, 153, 196);
            height: 352px;
        }
        #content {
            flex-grow: 1;
        }
    }



</style>