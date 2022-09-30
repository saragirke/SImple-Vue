<script setup>

</script>

<template>
    <article>
<h1>Tankar kring uppgiften</h1>

<section>
<p>
Jag tycker att det var ganska enkelt att komma igång med uppgiften och att använda Vue. <br>
Allt eftersom så har det klarnat hur filer hänger ihop och därmed fördelarna.<br>
Jag gillar att kunna dela upp koden, det blir bättre struktur och enklare att hitta fel.<br>
 Att kunna stylea med CSS för en specifik sida har också känts smidigt. <br>


    <br><br>
    </p></section>

<section>
    <h2> Svårigheter</h2>
    <p> 
        Det är många nya delar att lära sig som behöver nötas. Blir bra att arbeta vidare<br>  
        med Vue i projektet för lära in mer. Jag fastnade på att få till uppdateringen och <br> 
         specifikt att skriva ut varje rads id i tabellen. Med hjälp från Malin så gick det <br> 
         sedan bra att göra PUT-metoden. Något jag inte fått ordning på är att ändra i <br> 
         kolumnerna för "läst". När siffran ändras så adderas även elementet br till siffran<br> 
        vilket gör att det inte uppdateras. 
    </p>
</section>
</article>
</template>



<style scoped>

    article {
       margin:0 auto;
       background-color: rgba(250, 235, 215, 0.415);
       width: 70%;
       border-radius: 15px;
       box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px, rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
       text-align: center;
       padding-bottom:5%;
       margin-top:2%;
       padding-top:1%;
    }
   
      h1{
           text-align: center;
           font-family: 'Quicksand', sans-serif;
           font-size:35px;
       } 
       
       h2 {
           text-align: center;
           font-family: 'Quicksand', sans-serif;
       }
   
       p {
           font-family: 'Quicksand', sans-serif;
          
       }
   
   section {
    text-align: center;
    margin:0 auto;
    margin:2%;
   }

   .picture {
    max-width: 100%;
    height: auto;
   }


   @media screen and (max-width: 700px) {

article {
    width: 90%;
}
}
   </style>
   