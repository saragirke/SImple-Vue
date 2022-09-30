<template>
    <header>
        <div class="headerdiv">
        <h1>Ljudböcker</h1>
    <nav>
        <ul>
            <li><RouterLink to="/">Start</Routerlink></li>   
            <li><RouterLink to="/books">Böcker</Routerlink></li>   
            <li><RouterLink to="/info">Info</Routerlink></li>   
        </ul>
    </nav>
    </div>
    </header>
    </template>
    
    <script>
        import { RouterLink } from 'vue-router'

        export default {
            components: {
                RouterLink
            }
        }
    </script>
    
    <style scoped>
    header li {
        display:inline;
        margin:3%;
    
    }
    header {
        background-image: url("../components/headphones.jpg");
        height: 500px; /* You must set a specified height */
      background-position: center; /* Center the image */
      background-repeat: no-repeat; /* Do not repeat the image */
      background-size: cover; /* Resize the background image to cover the entire container */
    max-width: 100%;
    }
    
    .headerdiv {
    text-align: center;
    
    }
    
    .headerdiv {
      width: 100%;
      overflow: auto;
      padding: 250px 0;
    }
    
    h1 {
        color: white;
        font-family: 'Amatic SC', cursive;
        font-size:76px;
    }
    
    a {
  color: inherit;
  text-decoration: none;
  font-family: 'Quicksand', sans-serif;
  font-size: 24px;
  color:black;
  font-weight: bolder;
}

a {
  background:
    linear-gradient(
      to right,
      rgba(100, 200, 200, 1),
      rgba(100, 200, 200, 1)
    ),
    linear-gradient(
      to right,
      rgb(76, 248, 234),
      rgb(248, 186, 155),
      rgb(234, 137, 228)
  );
  background-size: 100% 3px, 0 3px;
  background-position: 100% 100%, 0 100%;
  background-repeat: no-repeat;
  transition: background-size 400ms;
}

a:hover {
  background-size: 0 4px, 100% 3px;
  color:white;
}
    
    </style>