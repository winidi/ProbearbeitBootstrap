<template>
    <div class="container">
        <h1>Admin Bereich</h1>

        <div class="eintraege">
                <ul v-for="(gast, index) in gastbuch" :key="index">
                    <hr>

                 <p class="pgast">
                <label>name:<br></label>
                <input class="center-block" type="text" v-model="gast.name">
                </p>
                <label>text:<br></label>
                <input class="center-block" type="text" v-model="gast.text">
                    
                    
                <button class="edit" v-on:click="editEintrag(index)">edit</button>
                <button class="adminbutton" v-on:click="deleteGasteintrag(index, gast.id)">Eintrag löschen</button>
              
                </ul>

    	</div> 
        

    </div>
</template>


<script>
export default {
    data(){
        return{
            test: '',
            name: '',
            gastbuch: [],
            
        }
    },
   mounted() {
        this.gastbuch = JSON.parse(localStorage.getItem('STORAGE_KEY'))
    },
    methods: {
        deleteGasteintrag: function(index) {
            //alert(index)
            this.gastbuch.splice(index, 1,);
            localStorage.setItem('STORAGE_KEY', JSON.stringify(this.gastbuch));
            this.gastbuch = JSON.parse(localStorage.getItem('STORAGE_KEY'))
        },
        editEintrag: function(index){
            this.gastbuch.splice(index , 1, this.gastbuch[index])
            localStorage.setItem('STORAGE_KEY', JSON.stringify(this.gastbuch));
            this.gastbuch = JSON.parse(localStorage.getItem('STORAGE_KEY'))
        }        
    }
}
</script>
<style >

.container {
    padding-bottom: 3.2em;
}

.adminbutton {
    
    margin-left: 2em;
}
.content{  
    margin: 0;
    width: 100%;
    min-height: 100vh;
    background-image: linear-gradient(
        #f8bcb8,	
        rgb(212, 179, 179),    
        #B5D5D8);
}
</style>

<style scoped>

.container{
    padding-top: 4em;
}

</style>