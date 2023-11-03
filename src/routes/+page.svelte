<script lang="ts">
	let categories = [
        {
            "name": "Unions & Labor Organizations",
            orgs: [
                {
                    "name": "Service Employees International Union",
                bgpic: "https://pbs.twimg.com/profile_banners/70273922/1560127182/1500x500",
                pic: "https://pbs.twimg.com/profile_images/1137882096624517121/168O2pjK_400x400.png",
                }
            ]
        }, 
        {
            "name": "Racial Justice & Civil Rights",
            orgs: [
                {
                    "name": "Black Lives Matter LA",
                bgpic: "https://pbs.twimg.com/profile_banners/1604931252/1499929294/1500x500",
                pic: "https://pbs.twimg.com/profile_images/1593386420579680257/4qRZF89-_400x400.jpg",
                link: "https://blmla.org/"
                }
            ]
        },
        {
            "name": "Urban Planning & Mobility",
            orgs: [
                {
                    "name": "Streets for All",
                bgpic: "https://pbs.twimg.com/profile_banners/130036197/1644895977/1500x500",
                pic: "https://pbs.twimg.com/profile_images/1155981018555277312/vnvrRsV0_400x400.jpg",
                link: "https://streetsforall.org"
                }
            ]
        },
    ]
</script>

<div>
    <div class=' px-12 py-16 md:py-48 lg:py-64 hero text-white'>
     
        <h1 class='text-3xl font-bold text-white resetfilter'>Find Your Place to Make Change.</h1>  
        <p>Explore and connect with hundreds of local unions, collectives, and non-profits.</p>
     
    </div>
</div>

<div class='px-12 py-32'>
    {#each categories as category}
        <h2>{category.name}</h2>
        <div class='grid md:grid-cols-3 gap-x-4 gap-y-4'>
                
        {#each category.orgs as org}
            
                <div class='rounded-lg flex flex-col'>
                    <img src={org.bgpic}/>
                    <div>
                        <h4>
                            {org.name}
                        </h4>
                    </div>
                </div>
        {/each}
    </div>
    {/each}

</div>

<style>

    .hero {
background-position: center bottom;
background-size: cover;

        background:
        linear-gradient(
          rgba(0, 0, 0, 0.7), 
          rgba(0, 0, 0, 0.7)
        ),
        url("https://dynaimage.cdn.cnn.com/cnn/digital-images/org/defa2dd2-389d-40f5-a7a8-0be1437453fd.jpg");
    }
</style>