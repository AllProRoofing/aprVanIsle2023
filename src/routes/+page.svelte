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
</style>

