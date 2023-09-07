<script lang="ts">

import "../../app.css";

import firebase from 'firebase/compat/app';
import 'firebase/compat/auth';

async function testfirebase() {
    const auth = firebase.auth();

// Get the current user's ID token
const idToken = await auth.currentUser.getIdToken();

if (idToken) {
    fetch("https://https://backend.movementdirectory.org/testfirebase", {
        method: "POST",
        mode: "cors",
        headers: {
            "Content-Type": "application/json",
            "Authorization": idToken
        }
    })
        .then((res) => res.json())
        .then((data) => {
            console.log(data);
        });
}


}

</script>

<div>

    <h1>Dashboard</h1>

    <h2>
        My Organizations
    </h2>

   <button on:click={testfirebase}>Test Firebase Endpoint</button>

</div>