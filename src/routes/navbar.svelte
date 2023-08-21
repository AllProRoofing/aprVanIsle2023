<script>
  const navbarItems = {
    //'all pro roofing since 1995': '/',
    '24/7 Roof Repairs': '/home',
    'call us at: +1-250-522-0216': 'tel:+1-(250)-522-0216',
    'email: totalroofing01@gmail.com': 'mailto:totalroofing01@gmail.com',
  };

  const navbarExtras = {
    'Gallery':'/gallery',
    'About':'/about',
    'Awards':'/awards',
    'FAQ':'/faq',
    'Resources':'/resources',
  } 
</script>

<div id='navbarContainer'>
    <div id='navbar'>
        <a href='/'>
            <div style="width: 100% !important;">
                <img
                    src="./aprLogo40Years.svg"
                    alt="all pro roofing logo"
                >
            </div>
        </a>
        <!--<div id='navbarLinkContainer'>
          {#each Object.entries(navbarItems) as [itemName, itemLink]}
            <a href={itemLink}>
              <div>
                <p class="navbarItem">
                    {itemName}
                </p>
              </div>
            </a>
          {/each}
        </div>-->
    </div>
    <!--
    <div id='navbarExtras'>
        {#each Object.entries(navbarExtras) as [itemName, itemLink]}
            <a href={itemLink}>
                <div>
                    <p class="navbarItem" style="color: white; padding-top: 1.0rem;">
                        {itemName}
                    </p>
                </div>
            </a>
        {/each}
    </div>
    -->
</div>


<style>
    #navbarContainer { 
        width: 100%;
        position: fixed;
            top: 0px;
    }
    #navbar {
        background-color: #222;
        border-radius: 0px;
        display: grid;
            grid-template-columns: 
                repeat(auto-fit, minmax(20rem, 1fr));
        margin: 0px;
        padding: 0px;
        text-align: center;
    }
    .navbarItem {
        background-color: transparent;
        color: var(--colorPrimary);
        height: 1rem;
        margin: 0px;
        padding: 0px;
    }
    #navbarLinkContainer {
        color: var(--colorTextDark) !important; 
        display: flex;
            flex-direction:column;
            justify-content: space-around;
    }
    #navbarLinkContainer>a>div>p {
        color: var(--colorTextDark) !important; 
    }
    #navbarLinkContainer>a>div>p:hover {
   
        color: var(--colorPrimary) !important; 
    }
    #navbarExtras {
        background-color: var(--colorPrimary);
        color: white !important;
        display: flex;
            justify-content: space-around;
    }
    #navbarExtras >a>div> p {
        font-size: 1.2rem;
        transform: translateY(-0.4rem);
    }
    #navbarExtras:hover {
        color: #333;
    }
</style>
