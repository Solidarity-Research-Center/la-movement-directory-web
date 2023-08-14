<script>
    import { onMount } from "svelte";
    import firebase from 'firebase/compat/app';
import 'firebase/compat/auth';
    import "../app.css";

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

      


    })
  </script>
  
  <slot />