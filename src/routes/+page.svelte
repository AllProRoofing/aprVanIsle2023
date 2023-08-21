<script>
    import { onMount } from 'svelte';

    import HomeHeader from './homeHeader.svelte';
    import Navbar from './navbar.svelte';
    import Since1987 from './since1987.svelte';
    import Specialty from './specialty.svelte';
    import VerifiedAndAwarded from './verifiedAndAwarded.svelte';
    async function setSpacerSize() {
        return new Promise((resolve) => {
            setTimeout(() => {
                if (typeof document !== 'undefined') {
                    const navbarContainer = document.getElementById('navbarContainer');
                    if (navbarContainer) {
                        const containerHeight = getComputedStyle(navbarContainer).height;
                        resolve(containerHeight);
                    } else {
                        resolve(null);
                    }
                } else {
                    resolve(null);
                }
            }, 300);
        });
    }

    async function updateSpacerMinHeight() {
        const spacerHeight = await setSpacerSize();
        if (spacerHeight && typeof document !== 'undefined') {
            document.getElementById('spacer').style.minHeight = spacerHeight;

            console.warn('async log');
        }
    }

    onMount(() => {
        try {
            updateSpacerMinHeight();
        } catch (e) {
            console.warn('error with async', e);
        }
    });
</script>
<Navbar />

<div id="spacer">
you shouldn't see this 🤔
</div>


<HomeHeader />
<br />
<br />
<br />
<Since1987 />
<br />
<br />
<br />
<Specialty />
<br /> 
<br />
<br />
<VerifiedAndAwarded />
<br />
<br />
<br />

<style>
    /* Your CSS styles here */
:root {
    --borderRadius: 10px;

    --colorPrimary: #BF3131; 
    --colorBgPrimary: #ddDDdd;
    --colorBgSecondary: rgba(0, 0, 0 ,0.9);
    --colorTextLight: #000;
    --colorTextDark: #fff;

    --fontPrimary: sans-serif;

    --stdMargin: 1rem;
    --stdPadding: 1rem;
}

:link {
    color: var(--colorPrimary);
    cursor: pointer;
    text-decoration: none;
}

* {
    border-radius: var(--borderRadius);
    transition-duration: 200ms;
}

body {
    aspect-ratio: auto;
        height: auto;
            min-height: 110vw;
        width: auto;
    background-color: var(--colorPrimary);
    border-radius: var(--borderRadius);
    font-family: sans-serif;
    margin: 0px;
    padding: 0px; 
    overflow-x: hidden;
}

h1, h2, h3, h4, h5, h6 { 
    background-color: var(--colorBgSecondary);
    color: var(--colorTextDark);
    margin: var(--stdMargin);
    font-family: serif;
        font-style: italic;
        font-weight: bolder;
        text-transform:uppercase;
    padding: var(--stdPadding);
    text-align: center;
    width: calc((100%) - 2(var(--stdPadding)));
}

p {
    background-color: var(--colorBgSecondary);
    color: var(--colorTextDark); 
    font-family: sans-serif;
        letter-spacing: 1px;
        line-height: 1.4rem;
    margin: auto;
    padding: var(--stdPadding);
    max-width: 50rem;
}
</style>

