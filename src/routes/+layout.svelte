<script>
    import { onMount } from "svelte";
    import firebase from 'firebase/compat/app';
import 'firebase/compat/auth';
    import "../app.css";

    let 
    show = true;


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

      

        if (window.location.href.indexOf("/dashboard") != -1) {
            show = false;
        }
    })

    
  </script>

  <nav class={`bg-white border-b border-gray-400 ${show ? ' ' : 'hidden'}`}>

    <div class='flex items-center px-3 py-2'>
        <img src='/laforall.png'
        class='h-12'
        />
        <p class='font-bold text-xl pb-1'>movement directory</p>

        
    <div class='ml-auto font-semibold underline text-amber-600'>Org Login</div>
    </div>
   

  </nav>
  
  <slot />