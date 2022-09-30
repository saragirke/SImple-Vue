<template>        
<!-- mustascher för att hämta böckerna-->
<!-- Eventlyssnare @-->
  <tr>
    <td v-bind:id="'name' + book.id" contenteditable>{{book.name}}</td>
    <td v-bind:id="'author' +book.id" contenteditable>{{book.author}}</td>
    <td v-bind:id="'genre' +book.id" contenteditable>{{book.genre}}</td>
    <td v-bind:id="'released' +book.id" contenteditable>{{book.released}}</td>
    <td v-bind:id="'read' +book.id" contenteditable> {{book.read}}</td>
    <td class="remove" @click="$emit('deleteBook')">Radera</td>
    <td class="remove" @click="$emit('updateBook')">Ändra</td>
  </tr> 
</template>

<!-- Tar emot böckerna som objekt-->
<script> 
export default {
    props: {
        book: Object
    }
}
</script>


<style scoped>
    article{
        text-align:Center;
        font-family: 'Quicksand', sans-serif;
        font-size: 18px;
        margin: 0 auto;
        border: 1px black solid;
        width:90%;
        border-radius: 15px;
        margin-top:1%;
        box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px, rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
        background-color: rgba(243, 226, 253, 0.202);
    }

    h1{
        text-align: center;
        font-family: 'Quicksand', sans-serif;
    }
div {
    overflow-x:auto;
}
</style>