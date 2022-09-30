
<template>
    <h1> Böcker jag läst</h1>
    <p>Böckerna i taballen med siffra 1 några av de böcker som jag läst i år. Böcker med siffran 0 är böcker som jag vill läsa.</p>

    <p id="error"> </p>
<table>

    <tr>
        <th>Namn</th>
        <th>Författare</th>
        <th>Genre</th>
        <th>Publicerad</th>
        <th>Läst?</th>
        <th>Hantera</th>
        <th>Hantera</th>
    </tr>
    <Book @deleteBook="deleteBook(book.id)" @updateBook="updateBook(book.id)" v-for="book in books" :book="book" :key="book.id" />


</table>
<br><br>
<AddBook @bookAdded="getBook()" />







</template>

<script>
import Book from "../components/Book.vue";
import AddBook from "../components/AddBook.vue";

export default {

    // Reaktiv data
    data() {
        return {
            books: []
        }
    },

    components: {
        Book,
        AddBook
    },

    //Funktioner
    methods: {
    //GET books
    async getBook() {

        //Fetch till restwebbtjänst
        const resp = await fetch("https://intense-plateau-16424.herokuapp.com/api/books"); 

        // När vi fått svar från webbtjänsten ska data lagras
        const data = await resp.json();

        this.books = data;
},

    //Radera
   async deleteBook(id){
        const resp = await fetch("https://intense-plateau-16424.herokuapp.com/api/books/" + id, {
            //Deleteanrop
            method: "DELETE",
            //Headers
            headers:{
                "Accept": "application json",
                "Content-Type": "application/json"

            }
        });

        const data = await resp.json();

        //Läs in böcker på nytt
        this.getBook();
   }, 

   async updateBook(id){

    if(this.name != 0 & this.author != 0 & this.genre != 0 & this.released != 0 & this.read === 0 | 1) { 

                // Hämtar innehåll i td-element 
                let bookname= document.getElementById("name" + id).innerHTML;
                let bookauthor= document.getElementById("author"+ id).innerHTML;
                let bookgenre= document.getElementById("genre" + id).innerHTML;
                let bookreleased= document.getElementById("released" + id).innerHTML;
                let bookread= document.getElementById("read" + id).innerHTML; 


                        //Javascript objekt
                        let bookBody = {
                        name: bookname,
                        author: bookauthor,
                        genre: bookgenre,
                        released: bookreleased,
                        read: bookread
                    }; 

                    

            const resp = await fetch("https://intense-plateau-16424.herokuapp.com/api/books/" + id, {

            method: "PUT",
                        headers: {
                            "Accept": "application/json",
                            "Content-type": "application/json"
                        },
                        body: JSON.stringify(bookBody)

                   
            });
            const data = await resp.json();

            document.getElementById("error").innerHTML = "Ändrad!";
            console.log(bookBody);           
                    
                }else {
                    document.getElementById("error").innerHTML = "Alla fält måste vara ifyllda!";
                } 
   }
    },
    mounted() {
        this.getBook();
    }
}

</script>

<style scoped>
    h1 {
        text-align: center;
        font-family: 'Quicksand', sans-serif;
    }

    p {
        font-family: 'Quicksand', sans-serif;
        text-align: center;
    }
    div {
    overflow-x:auto;
}
</style>