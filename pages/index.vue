<template>
  <div class="container">

     <div class="jumbotron">
        <h1 class="display-2">Willkommen bei</h1>
        <img src="~/assets/logo.jpg" alt="">
        <h1 class="display-2">Leo's Restaurant</h1>
        <p class="lead">Wer bei Leo's isst kann sich sicher sein, dass alle Zutaten nur aus den besten Quellen bezogen werden</p>
        <hr class="my-4">
        <p></p>
        <p class="lead">
          <a class="btn btn-primary btn-lg" href="speisekarte" role="button">Direkt zu den Speisen</a>
        </p>
    </div>
    
  </div>
</template>

<script>
export default {}
</script>

<style>
#image {
  
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
