<script setup>

</script>

<template>
    <article>
<h1>FRITIDSINTRESSE</h1>
<h2>Ljudböcker</h2>
<section>
<p>
Mitt frtidsintresse är ljudböcker. Jag lyssnar på ljudbok vid appen Nextory och lyssnar varje dag. <br>
Jag har alltid tyckt om att läsa, och ljudböcker har gjort det mer tillgängligt att ta del av berättelser<br>
eftersom det går att lyssna medans man gör annat, som exempelvis när jag kodar CSS.<br><br>
Anledningen till att jag tycker så mycket om att lyssna på böcker än att exempelvis se på serier är <br>
framförallt att jag i böckertycker att jag lär känna karaktärerna bättre. <br><br>
    </p></section>
    <h2>Favoritförfattare</h2>
<section>
    <p>Två favoritförfattare är B.A Paris och JK. Rowling. B.A Paris skriver thrillers som verkligen är svåra att slita sig ifrån.<br>
    Och Harry Potter böckerna är självklara favoriter sedan barndomen.
    
    Dessa böcker har jag läst flera gånger.</p><br><br>
    <img class="picture" src="../components/harryp.jpg">
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
   