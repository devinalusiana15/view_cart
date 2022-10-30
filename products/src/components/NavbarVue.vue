<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark p-md-2">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="../assets/logogeo.svg" class="img-fluid">
        </a>
        <div class="container">
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNavDropdown"
          aria-controls="navbarNavDropdown"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
          
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item dropdown">
            
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Category
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
              <li><a class="dropdown-item" href="#">satu</a></li>
              <li><a class="dropdown-item" href="#">dua</a></li>
            </ul>
            </li>
            <li class="nav-item">
              <button class="btn btn-outline-light" type="submit" >Join Partnership With Us</button>
            </li>
            <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Lang
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
              <li><a class="dropdown-item" href="#">ENG</a></li>
              <li><a class="dropdown-item" href="#">ID</a></li>
            </ul>
            </li>
          </ul>
        </div>
      </div>
      </div>
    </nav>
  </div>
</template>
  
  <script>
export default {
  name: "NavbarVue",
};
</script>

<style scoped>
.navbar {
  background-color: #59cfd7;
  display: flex;
}
li{
  margin-right: 10px;
}
</style>

