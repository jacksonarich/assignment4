<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>page description</title>
    <style>
      * {
        margin: 0;
        padding: 0;
      }
      .center-fit {
        max-width: 100%;
        margin: auto;
      }
    </style>
  </head>
  <body>
    <img class="center-fit" src="jacksonsoft-logo.png" alt="banner">

    <iframe src="https://thunkable.site/w/-7cohwoy82Tikq54IinxP" title="Profile App" height=750 width=450></iframe>

    <p id="animal1"></p>
    <p id="book1"></p>
    <p id="food1"></p>
    <p id="name1"></p>
    <br>
    <p id="animal2"></p>
    <p id="book2"></p>
    <p id="food2"></p>
    <p id="name2"></p>



<script type="module">

  // Firebase stuff
  import { initializeApp } from "firebase/app";
  import { getAnalytics } from "firebase/analytics";
  const firebaseConfig = {
    apiKey: "AIzaSyDTTAISZM2Cw9jl2UfVerbhctO-wmnnz80",
    authDomain: "project-app-b0d5c.firebaseapp.com",
    databaseURL: "https://project-app-b0d5c-default-rtdb.firebaseio.com",
    projectId: "project-app-b0d5c",
    storageBucket: "project-app-b0d5c.appspot.com",
    messagingSenderId: "891081504552",
    appId: "1:891081504552:web:89d1cd9272a0342119c21d",
    measurementId: "G-BTWR51ZRE6"
  };
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  import {getDatabase, set, get, update, remove, ref, child}
  from "https://www.gstatic.com/firebasejs/10.4.0/firebase-database.js";
  const db = getDatabase();
  const dbref = ref(db);

  // Get elements
  var animal1 = document.getElementById("animal1");
  var book1 = document.getElementById("book1");
  var food1 = document.getElementById("food1");
  var name1 = document.getElementById("name1");
  var animal2 = document.getElementById("animal2");
  var book2 = document.getElementById("book2");
  var food2 = document.getElementById("food2");
  var name2 = document.getElementById("name2");

  // Hardcode IDs
  const id1 = "1msKM1ahLRbGjOdM7qeMXeuQqn72";
  const id2 = "LCHRZCa0mbZqx8QH6svmfndDkyH3";
  
  // Set element content
  get(child(dbref, id1))
  .then((snapshot)=>{
    if (snapshot.exists()) {
      animal1.innerHTML = snapshot.val().animal;
      book1.innerHTML = snapshot.val().book;
      food1.innerHTML = snapshot.val().food;
      name1.innerHTML = snapshot.val().name;
    } else {
      alert("No data found");
    }
  })
  .catch((error)=>{
    alert(error)
  })

  get(child(dbref, id2))
  .then((snapshot)=>{
    if (snapshot.exists()) {
      animal2.innerHTML = snapshot.val().animal;
      book2.innerHTML = snapshot.val().book;
      food2.innerHTML = snapshot.val().food;
      name2.innerHTML = snapshot.val().name;
    } else {
      alert("No data found");
    }
  })
  .catch((error)=>{
    alert(error)
  })
</script>



  </body>
</html>
