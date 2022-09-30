<template>
    <div>
    <form @submit.prevent="addBook()">
        <h2>Lägg till bok i listan</h2>
        <label for="name">Bokens namn:</label><br>
        <input v-model="name" type="text" id="name" name="name"><br>

        <label for="author">Författare:</label><br>
        <input  v-model="author" type="text" id="author" name="author">

        <label for="genre">Genre:</label><br>
        <input v-model="genre" type="text" id="genre" name="genre">

        <label for="released">Publiceringsår:</label><br>
        <input v-model="released" type="number" id="released" name="released"><br>

        <input  v-model="read" type="radio" id="read" name="read" value="1">
        <label for="read">Jag har läst boken</label>

        <input  v-model="read" type="radio" id="read" name="read" value="0">
        <label for="read">Jag har inte läst boken</label><br> <br><br>
<p id="error2"> </p>
        <input type="submit" value="Submit">
    </form>
   
</div>
</template>

<script>
    //Komponent
    export default {
        data() {
            return {
                name: "",
                author: "",
                genre: "",
                released: "",
                read: ""
            }
        },
        emits: ["bookAdded"],
        methods: {
            async addBook() {
               //Kontrollerar att fälten + radiobutton i är fyllda
               if(this.name != 0 & this.author != 0 & this.genre != 0 & this.released != 0 & this.read >=0) { 

                
                    //Javascript objekt
                    let bookBody = {
                        name: this.name,
                        author: this.author,
                        genre: this.genre,
                        released: this.released,
                        read: this.read
                    };
 
                    //FETCH
                    const resp = await fetch ("https://intense-plateau-16424.herokuapp.com/api/books", {
                        method: "POST",
                        headers: {
                            "Accept": "application/json",
                            "Content-type": "application/json"
                        },
                        body: JSON.stringify(bookBody)
                    });

                    const data = await resp.json();

                    /*Töm fälten efter lagring*/
                    this.name = "";
                    this.author = "";
                    this.genre = "";
                    this.released = "";
                    this.read = ""; 
                    
                    //Emit för att ladda om sidan
                    this.$emit("bookAdded");
                
                    document.getElementById("error2").innerHTML = "Bok tillagd till listan!";
                    
                }else {
                    document.getElementById("error2").innerHTML = "Alla fält måste vara ifyllda!";
                }
            }
        }
    }
</script>











<style scoped>
    form {
        font-family: 'Quicksand', sans-serif;
        font-size:18px;  
        background-image: linear-gradient(rgba(154, 152, 154, 0.5), rgba(154, 152, 154, 0.5)), url("../components/books.jpg");
          /* Control the height of the image */
  min-height: 380px;

/* Center and scale the image nicely */
background-position: center;
background-repeat: no-repeat;
background-size: cover;
  position: relative;  padding: 50px;
  margin-top: 15%;
  margin-left:5%;
  margin-right:5%;  
  margin: 0 auto;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  border: 1px solid black;
  width:60%;
  border-radius: 15px;
  color: white;
  font-weight: bolder;
    }


    input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  font-family: 'Quicksand', sans-serif;
}
input[type=number], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  font-family: 'Quicksand', sans-serif;
}

input[type=submit] {
  width: 40%;
  background-color: rgba(150, 210, 194, 0.931);
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-family: 'Quicksand', sans-serif;
  font-size:18px;  
}

input[type=submit]:hover {
  background-color: #f9cdf1;
  font-weight: bolder;
}



#error {
    font-family: 'Quicksand', sans-serif;
    font-weight: bolder;

}

h2 {
    text-align: center;
}
</style>