<template>
  <div>
  <b-navbar toggleable="lg" type="dark" variant="dark">

    <b-navbar-brand>
       <b-link class="logo-link"  :to="''"> Leo's Restaurant </b-link>
    </b-navbar-brand>
    

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <ul class="navbar-nav">
        <li class="nav-item">
           <b-link class="nav-link" :to="'historie'">Historie</b-link>
        </li>
    </ul>
    <ul class="navbar-nav">
        <li class="nav-item">
             <b-link class="nav-link" :to="'kontakt'">Kontakt</b-link>
           
        </li>
    </ul>
    <ul class="navbar-nav">
        <li class="nav-item">
             <b-link class="nav-link" :to="'speisekarte'">Speisekarte</b-link>
        </li>
    </ul>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>

      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
          
       <ul class="navbar-nav">
        <li class="nav-item">
             <b-link class="nav-link" :to="'gaestebuch'">Gästebuch</b-link>
        </li>
    </ul>

      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<style scoped>
.logo-link {
    color: white;
}

.navbar-nav > li{
  padding-left:20px;
  padding-right:20px;
}


</style>