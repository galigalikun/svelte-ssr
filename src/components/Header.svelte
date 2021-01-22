<script lang="ts">
    import logo from 'images/toC_logo.svg';

    let active = false;

    function handleToggle() {

    }
</script>

<style>
    header {
        width: 100%;
        background-color: #fff;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 100;
    }
    div {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    aside {
        display: none;
        width: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background-color: rgba(0, 0, 0, .4);
        z-index: 1001;
    }
    aside.active {
        display: block;
    }
    nav {
        width: 250px;
        box-sizing: border-box;
        background-color: #fff;
        min-height: 100vh;
    }
    ul {
        list-style: none;
    }
    .logo a {
        width: 100px;
        height: 0;
        padding: 30px 0 0;
        margin: 10px;
        display: block;
        overflow: hidden;
        background-repeat: no-repeat;
        background-position-x: center;
        background-position-y: top;
        background-size: 100% auto;
    }
</style>
<header>
    <div>
        <span on:click={() => active = !active} class="header_btn"><i class="fa fa-bars">aaa</i></span>
        <p class="logo"><a href="/" style="background-image: url({logo});">unisize(ユニサイズ)</a></p>
        <div>
            <a href="/items/search" class="header_btn"><i class="fa fa-search"></i>search</a>
        </div>
    </div>
    <aside class:active={active} on:click={() => active = !active} >
        <nav>
            <ul>
                <li class="logo">
                    <a href="/">unisize</a>
                </li>
                <li>
                    <a href="/keyword">キーワードから探す</a>
                </li>
                <li>
                    <a href="/brands">ブランドから探す</a>
                </li>
                <li>
                    <a href="https://makip.co.jp/#contact_us_area" target="_blank">お問い合わせ</a>
                </li>
                <li>
                    <a href="https://makip.co.jp/#company" target="_blank">会社概要</a>
                </li>
                <li>
                    <a href="https://makip.co.jp/unisize-terms.html" target="_blank">利用規約</a>
                </li>
                <li>
                    <a href="https://makip.co.jp/privacy-policy.html" target="_blank">プライバシーポリシー</a>
                </li>
            </ul>
        </nav>
    </aside>
</header>
