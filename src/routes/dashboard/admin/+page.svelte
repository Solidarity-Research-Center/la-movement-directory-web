<script lang="ts">

    import "../../../app.css";
    
  function submitneworg() {
    fetch("https://backend.movementdirectory.org/makeorg", {
      "method": "POST",
      "headers": {
        "content-type": "application/json"
      },
      body: JSON.stringify({
        name: (document.getElementById("orgname") as HTMLInputElement).value,
        description: "",
        website: "",
        banner_url: (document.getElementById("submit-banner-url") as HTMLInputElement).value,
        profile_url: (document.getElementById("profile-url") as HTMLInputElement).value,
        university: (document.getElementById("grid-uni") as HTMLInputElement).value,
        neighbourhood: (document.getElementById("grid-ne") as HTMLInputElement).value,
        city: (document.getElementById("grid-neighbourhood") as HTMLInputElement).value,
        state: (document.getElementById("grid-state") as HTMLInputElement).value,
        zip: (document.getElementById("grid-zip") as HTMLInputElement).value,
        auth_emails: [],
        categories: []
      })
    })
  }
    </script>
    
    <div>
    
        <h1 class='font-bold text-xl'>Admin Console</h1>        
    
        <div class='bg-gray-100 mt-2 rounded-lg py-2 w-fit'>
            <h2 class='pl-3'>Add New Organization</h2>

            <form class="w-full max-w-lg">
                <div class="flex flex-wrap  mb-6">
                    <div class="w-full  px-3 mb-6 md:mb-0">
                      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="orgname">
                        Organization Name
                      </label>
                      <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-1 leading-tight focus:outline-none focus:bg-white" id="orgname"
                       type="text" placeholder="UCLA Climate Activists">
                      <p class="text-red-500 text-xs italic">Please fill out this field.</p>
                    </div>
                    <div class="w-full  px-3">
                      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" 
                      for="submit-banner-url">
                        Banner URL
                      </label>
                      <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 
                      rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" 
                      id="submit-banner-url" type="text" placeholder="https://pbs.twimg.com/profile_banners/130036197/1644895977/1500x500">
                    </div>
                  </div>
      
                  <div class="w-full  px-3">
                      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="profile-url">
                      Profile URL
                      </label>
                      <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="profile-url" type="text" 
                      
                      placeholder="https://pbs.twimg.com/profile_images/1155981018555277312/vnvrRsV0_400x400.jpg">
                   
                  </div>
                
                <div class="w-full  px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-uni">
                      University (Optional)
                    </label>
                    <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-uni" type="text" 
                    placeholder="University of California, Los Angeles">
                  </div>

                  <div class="w-full  px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-ne">
                      Neighbourhood
                    </label>
                    <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-ne" type="text" 
                    placeholder="Westwood">
                  </div>

                  <div class="w-full  px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-neighbourhood">
                      City
                    </label>
                    <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-neighbourhood" type="text" placeholder="Los Angeles">
                  </div>
                
                <div class="flex flex-wrap mb-2">
                  <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-city">
                      City
                    </label>
                    <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-city" type="text" placeholder="Los Angeles">
                  </div>
                  <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-state">
                      State
                    </label>
                    <div class="relative">
                      <select class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-state">
                        <option>California</option>
                      </select>
                      <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
                        <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                      </div>
                    </div>
                  </div>
                  <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-zip">
                      Zip
                    </label>
                    <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-zip" type="text" placeholder="00000">
                  </div>
                </div>
                
                <button
                on:click={() => {submitneworg()}}
                on:keydown={(e) => {if (e.key === "Enter") {submitneworg()}}}
                class='ml-3 bg-blue-500 text-white rounded-lg font-bold px-4 py-2'>
                    Create
                </button>
              </form>
        </div>

        <div>
            <h2 class='font-bold text-lg'>List of Organizations</h2>
        </div>
    
    </div>