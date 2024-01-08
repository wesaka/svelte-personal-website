<script>
    import './styles.css';
    import sveltesvg from '$lib/images/svelte-16-svgrepo-com.svg'
</script>

<div class="app">
    <main>
        <slot />
    </main>

    <footer>
        <p>
            <img class="svelte-logo" alt="Svelte Logo" src={sveltesvg} />
            Built with Svelte
<!--            <a href="/attribution-link"> Attributions</a> - Not doing that just yet-->
        </p>
    </footer>
</div>

<style>
    @font-face {
        font-family: 'ErbosDracoRegular';
        src: url('$lib/fonts/erbosdraco1stnbpregular-99v5.eot');
        src: url('$lib/fonts/erbosdraco1stnbpregular-99v5.eot?#iefix') format('embedded-opentype'),
        url('$lib/fonts/erbosdraco1stnbpregular-99v5.woff') format('woff'),
        url('$lib/fonts/erbosdraco1stnbpregular-99v5.ttf') format('truetype'),
        url('$lib/fonts/erbosdraco1stnbpregular-99v5.svg#erbosdraco1stnbpregular-99v5') format('svg');
        font-weight: normal;
        font-style: normal;
    }

    @font-face {
        font-family: 'ErbosDracoRegularOpen';
        src: url('$lib/fonts/erbosdraco1stopennbpregular-l5wx.eot');
        src: url('$lib/fonts/erbosdraco1stopennbpregular-l5wx.eot?#iefix') format('embedded-opentype'),
        url('$lib/fonts/erbosdraco1stopennbpregular-l5wx.woff') format('woff'),
        url('$lib/fonts/erbosdraco1stopennbpregular-l5wx.ttf') format('truetype'),
        url('$lib/fonts/erbosdraco1stopennbpregular-l5wx.svg#erbosdraco1stopennbpregular-l5wx') format('svg');
        font-weight: normal;
        font-style: normal;
    }

    footer {
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        z-index: 10;
        padding-bottom: 10px;
        text-align: center;
        font-size: 0.8em;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .svelte-logo {
        height: 1.2em;
        margin-right: 5px;
    }
</style>