<script>
    let selectedSport = "";
    let isDisabled = true;

</script>

<h1 class="title">Not Gambling</h1>
<h3 class="subtitle">
<label for="sportsDropdown" >Select your sport</label></h3>
<select name="sportDropdown" id="sportDropdown" bind:value={selectedSport} on:change={() => isDisabled = false}>
    <option value="" selected disabled hidden > Choose Here</option>
    <option value="basketball">Basketball</option>
    <option value="football">Football</option>
    <option value="hockey">Hockey</option>
    <option value="Soccer">Soccer</option>
</select>

<button id="loginBtn" disabled={isDisabled}><a href="./{selectedSport}">Go!</a></button>

<style>
    a {
        text-decoration: none;
        color: inherit;
    }

    button:disabled {
    color: grey;
   }
</style>