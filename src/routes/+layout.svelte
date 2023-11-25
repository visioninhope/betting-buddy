<script>

    let date = new Date(); 
    let currentYear = date.getFullYear();
</script>

<head>
    <title>Sports App Test</title>
</head>

<slot></slot>

<footer>
    <p>Howdy we did it</p>
    <p>Copyright {currentYear}</p>
</footer>

<style global>
   :root {
    font-family: 'Poppins', sans-serif;
   }

   button:disabled {
    color: grey;
   }

</style>