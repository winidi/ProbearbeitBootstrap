<template>
    <div class="container">
       <h1> Herzlich Willkommen! Tragen Sie sich gerne ein.</h1>
        <div class="col-xl">
        <label> <strong>Name: </strong></label><br>
       <input class="input" type="text" v-model="fname"><br>
       <label><strong> Ihre Nachricht: </strong></label><br>
       <textarea type="text" v-model="guesttext"></textarea><br>
       <button class="sendbutton" @click="addGuestPost">Abschicken</button>
        </div>
        <hr>

    <div class="eintraege">
                
                <ul v-for="gast in gastbuch" :key="gast.id">
                    <hr>
                    <strong>Name:</strong>
                <p class="pgast">{{gast.name}}</p>
                <strong>Nachricht:</strong><br>
                {{gast.text}}
                
                </ul>        
    	    </div>
        

    </div>
</template>


<script>
export default {
    data(){
        return {          
            
            fname: ' ',
            guesttext: '',
            id: 1,

           
            gastbuch: [
              {id: 1, name: 'Leo', text: 'Der erste Eintrag'},
           
            ],
            
        }
    },
    methods: {
        addGuestPost: function () {
            
            this.gastbuch.id = this.gastbuch.id + 1;
            this.gastbuch.push ({id: this.id, name: this.fname, text: this.guesttext});
            localStorage.setItem('STORAGE_KEY', JSON.stringify(this.gastbuch));
        }
    },
    
    mounted() {
        if(localStorage.getItem('STORAGE_KEY')!= null)
        this.gastbuch = JSON.parse(localStorage.getItem('STORAGE_KEY'))
    }
    
    
}
</script>

<style scoped>

.sendbutton{

}

.eintraege {
    border: solid black;
}
.center-block {
  margin: auto;
  
}
.cincont{
 width: 50%;
 margin: 0 auto;
}
.guestbookbox {
    padding-left: 1em;
    width: 33em;
    margin: auto;
    border: 2px solid #ccc;
}
#msg{
  width: 33em;
  height: 16em;
}
</style>

<style scoped>

.col-xl {
    padding-top: 2em;
}

textarea {
    width: 44em;
    height: 12em;
}

.container {
    padding-top: 4em;
}

</style>