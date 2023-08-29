<script>
    import {onMount} from "svelte";

    import Navbar from "./navbar.svelte";

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

<div>
    <Navbar />
    <div id="spacer">
    you shouldn't see this 🤔
    </div>
    
    <br />

    <div>
        <h1> All Pro Roofing - Your Trusted Roofing Experts in Parksville & Qualicum Beach Since 1987 </h1>
        
        <p>
            Welcome to All Pro Roofing, the roofing company that has been serving the beautiful Parksville and Qualicum Beach areas for over three decades. With our unwavering commitment to quality and customer satisfaction, we have established ourselves as the region's premier roofing specialists.
        </p>
        <br/>

        <br>

        <h2> About Us </h2>
        <p>
            Established in 1987, All Pro Roofing has been a cornerstone of the roofing industry in Parksville and Qualicum Beach. Our journey began with a simple mission: to provide top-notch roofing solutions and exceptional customer service to our community. Over the years, we have grown and adapted to meet the ever-changing needs of our clients, while our commitment to excellence has remained constant.
        </p>
        <br/>

        <h2> Our Services </h2>
        <br/><br/>
        
        <h3> Emergency Roof Services </h3>
        <p>
            Roof emergencies don't wait for convenient hours. That's why we offer 24/7 emergency roofing services. When disaster strikes, you can count on us to be there, quickly mitigating the damage and securing your property.
        </p>

        <h3> Roof Repairs</h3>
        <p>
            Roof damage can happen unexpectedly. Whether it's due to a storm, fallen tree, or simple wear and tear, our skilled team is ready to provide prompt and efficient roof repair services. We'll assess the damage and recommend cost-effective solutions to restore your roof's functionality.
        </p>
        <br/>

        <h3> Roof Maintenance: </h3>
        <p>
            We understand that a well-maintained roof is essential to protect your home or business. Our experienced team offers comprehensive roof maintenance services, including inspections, repairs, and cleaning. Regular maintenance not only extends the lifespan of your roof but also ensures the safety and integrity of your property, and saves you money in the future.
        </p>
        <br/>

        <h3> Roof Installation And Replacement </h3>
        <p>
            When it's time for a new roof, you can trust All Pro Roofing for professional and reliable installation services. We work with a wide range of roofing materials, from traditional asphalt shingles to eco-friendly options like metal and solar roofing. Our experts will guide you through the selection process to find the perfect roofing solution for your needs.
        </p>
        <br/>

        <h2> Why Choose Us </h2>
            <h3>Local Expertise:</h3> 
            <p>With over 30 years of experience in Parksville and Qualicum Beach, we understand the unique roofing challenges of our coastal community. Our local knowledge ensures that your roofing project is tailored to withstand the Pacific Northwest's climate.
            </p>
            <br/>
            <br/>
            <br/>

            <h3>Quality Materials:</h3> 
            <p>We source the finest roofing materials available to ensure durability and longevity. Your investment in a roof from All Pro Roofing is an investment in the future protection of your property.
            </p>
            <br/>
            <br/>
            <br/>

            <h3>Skilled Craftsmanship:</h3> 
            <p>Our team of highly trained and certified roofers takes pride in their work. We adhere to industry best practices, delivering top-quality results on every project.
            </p>
            <br/>
            <br/>
            <br/>

            <h3>Customer-Centric Approach:</h3> 
            <p>We value your trust and satisfaction above all else. Our customer-centric approach means open communication, transparency, and a commitment to meeting your unique needs.
            </p>
            <br/>
            <br/>
            <br/>

            <h3>Licensed and Insured:</h3> 
            <p>Rest easy knowing that All Pro Roofing is fully licensed and insured. Your property and investment are in safe hands.
            </p>
            <br/>
            <br/>
            <br/>
    </div>
</div>
