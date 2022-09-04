<script lang="ts">
    import { page } from "$app/stores"
    export const prerender = true
</script>


<div id="container">
    <!-- #region nav -->
    <nav>
        <ul>
            <li>
                <a 
                class:active={$page.url.pathname == "/"}
                href="/">Anasayfa</a>
            </li>
            <li>
                <a 
                class:active={$page.url.pathname == "/products"}
                href="/products">Muzik Aletleri</a>

                <ul id="sub-menu">
                    <li><a href="/products/piano">Piyanolar</a></li>
                    <li><a href="/products/guitar">Gitarlar</a></li>
                    <li><a href="/products/violin">Kemanlar</a></li>
                </ul>
            </li>
            <li>
                <a 
                class:active={$page.url.pathname == "/about"}
                href="/about">Hakkimizda</a>
            </li>
        </ul>
    </nav>
    <!-- #endregion /nav -->

    <!-- #region content -->
    <main>
        <slot />
    </main>
    <!-- #endregion /content -->
</div>




<style lang="less">
    nav {
       padding: 50px 4rem;
       width: 1100px;
       margin: 0px auto;
       ul {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: row;
            gap: 1rem;
            list-style: none;
            li {
                position: relative;
                a {
                    text-decoration: none;
                    cursor: pointer;
                    color:darkslateblue;
                    &:hover {
                        color: palevioletred;
                    }
                    &.active {
                        color: fuchsia;
                    }
                }

                ul {
                    display: none;
                }

                &:hover {
                    ul {
                        display: block;
                        position: absolute;
                        width: 100%;
                        z-index: 999;
                        li {
                            background-color: darkslateblue;
                            a {
                                color: aliceblue;
                                display: inline-block;
                                padding: 4px;
                                &:hover {
                                    color:palevioletred;
                                }
                            }
                        }
                    }
                }
            }
       }
    }

    main {
        padding: 0 4rem;
        width: 1100px;
       margin: 0 auto;
    }

    #container {
        width: 100%;
        min-height: 100vh;
        margin: 0;
        padding: 0;
        background: rgb(230, 221, 224);
    }

    :global(body) {
        margin: 0;
    }
</style>