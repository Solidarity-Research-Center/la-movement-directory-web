<script lang="ts">
     import { onMount } from 'svelte';
     import { initializeApp } from 'firebase/app';
     import firebase from 'firebase/compat/app';
     import 'firebase/compat/auth';
        import {redirect} from '@sveltejs/kit'
        import "../../app.css";

   
import "firebase/auth";

// Initialize Firebase

onMount(() => {

    const firebaseConfig = {
            apiKey: "AIzaSyCaVwJEqCza6CLN21ib9KhkVoAPc-uM0Ws",
  authDomain: "la-movement-directory.firebaseapp.com",
  projectId: "la-movement-directory",
  storageBucket: "la-movement-directory.appspot.com",
  messagingSenderId: "36844473114",
  appId: "1:36844473114:web:85afdd18b93b02d2f87aa3",
  measurementId: "G-752LQ6HZ8F"
        };

        firebase.initializeApp(firebaseConfig);

      


    firebase.auth().onAuthStateChanged(function(user) {
  if (user) {
    // User is signed in.

    console.log('sign in success')
    window.location.href = "/dashboard";

  } else {
    // No user is signed in.
  }
});
    })


    async function loginToGoogle() {
        try {
            const provider = new firebase.auth.GoogleAuthProvider();

            await firebase.auth().signInWithPopup(provider);
        }
        catch (e) {
            console.log(e);
        }
    }
</script>

<section class="bg-gray-50">
    <div class="flex flex-col items-center justify-center px-6 py-8 mx-auto md:h-screen lg:py-0">
        <a href="#" class="flex items-center mb-6 text-2xl font-semibold text-gray-900 ">
            <img class="h-16 mr-2" src="https://losangelesforall.org/wp-content/uploads/2022/03/Los-Angeles-for-All-logo-1.png" alt="logo">
           
        </a>
        <div class="w-full bg-white rounded-lg shadow  md:mt-0 sm:max-w-md xl:p-0 ">
            <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
                <h1 class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl ">
                    Sign in to your account
                </h1>
                <form class="space-y-4 md:space-y-6" action="#">
                    <div on:click={loginToGoogle} class='flex flex-row gap-x-4 border-gray-300 border-2 rounded-lg px-3 py-3 hover:bg-gray-50'><svg class="w-8 h-8" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <g clip-path="url(#clip0_13183_10121)"><path d="M20.3081 10.2303C20.3081 9.55056 20.253 8.86711 20.1354 8.19836H10.7031V12.0492H16.1046C15.8804 13.2911 15.1602 14.3898 14.1057 15.0879V17.5866H17.3282C19.2205 15.8449 20.3081 13.2728 20.3081 10.2303Z" fill="#3F83F8"></path><path d="M10.7019 20.0006C13.3989 20.0006 15.6734 19.1151 17.3306 17.5865L14.1081 15.0879C13.2115 15.6979 12.0541 16.0433 10.7056 16.0433C8.09669 16.0433 5.88468 14.2832 5.091 11.9169H1.76562V14.4927C3.46322 17.8695 6.92087 20.0006 10.7019 20.0006V20.0006Z" fill="#34A853"></path><path d="M5.08857 11.9169C4.66969 10.6749 4.66969 9.33008 5.08857 8.08811V5.51233H1.76688C0.348541 8.33798 0.348541 11.667 1.76688 14.4927L5.08857 11.9169V11.9169Z" fill="#FBBC04"></path><path d="M10.7019 3.95805C12.1276 3.936 13.5055 4.47247 14.538 5.45722L17.393 2.60218C15.5852 0.904587 13.1858 -0.0287217 10.7019 0.000673888C6.92087 0.000673888 3.46322 2.13185 1.76562 5.51234L5.08732 8.08813C5.87733 5.71811 8.09302 3.95805 10.7019 3.95805V3.95805Z" fill="#EA4335"></path></g><defs><clipPath id="clip0_13183_10121"><rect width="20" height="20" fill="white" transform="translate(0.5)"></rect></clipPath></defs>
                    </svg>
                
                    <p class='font-semibold text-gray-800 mt-0.5'>Signup / Login with Google</p>
                </div>
                   <!--<div>
                        <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your email</label>
                        <input type="email" name="email" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" placeholder="name@company.com" required="">
                    </div>
                    <div>
                        <label for="password" class="block mb-2 text-sm font-medium text-gray-900 ">Password</label>
                        <input type="password" name="password" id="password" placeholder="••••••••" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" required="">
                    </div>
                    <div class="flex items-center justify-between">
                        <div class="flex items-start">
                            <div class="flex items-center h-5">
                              <input id="remember" aria-describedby="remember" type="checkbox" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-primary-300" required="">
                            </div>
                            <div class="ml-3 text-sm">
                              <label for="remember" class="text-gray-500">Remember me</label>
                            </div>
                        </div>
                        <a href="#" class="text-sm font-medium text-primary-600 hover:underline">Forgot password?</a>
                    </div>
                    <button type="submit" class="w-full text-white bg-primary-600 hover:bg-primary-700 focus:ring-4 focus:outline-none focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center ">Sign in</button>
                    <p class="text-sm font-light text-gray-500">
                        Don’t have an account yet? <a href="#" class="font-medium text-primary-600 hover:underline">Sign up</a>
                    </p>-->
                </form>
            </div>
        </div>
    </div>
  </section>