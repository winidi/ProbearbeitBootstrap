<template>
    <div class="container">
        <h1>Admin Bereich</h1>

         <div class="eintraege" :key="componentKey">
                <ul v-for="comment in usercomments" :key="comment.id">
                <hr>
                
                <p class="pgast">
                <label>name:<br></label>
                <input class="center-block" type="text" v-model="comment.name">
                </p>
                
                <label>text:<br></label>
                <input class="center-block" type="text" v-model="comment.text">
                                 
                <button class="edit" v-on:click="editComment(comment.id, comment.name, comment.text)">edit</button>
                <button class="adminbutton" v-on:click="deleteComment(comment.id)">Eintrag löschen</button>
              
                </ul>              
    	</div> 

    </div>
</template>


<script>
import axios from 'axios'

export default {
    data(){
        return{
            //id: 1,
            text: '',
            name: '',
            //gastbuch: [],     
            componentKey: 0,
        }
    },

    async asyncData() {
        const{data} = await axios.get(`http://win.cim.local:3001/usercomments`)
        console.log(data)
        return {usercomments:data}

    },

   mounted() {
        this.gastbuch = JSON.parse(localStorage.getItem('STORAGE_KEY'))
    },
    methods: {

        async deleteComment(id) {
            axios.delete(`http://win.cim.local:3001/usercomments/${id}`)
            window.location.reload(true)
        },

        async editComment(id, uname, utext) {

            let editedComment = {
                name: uname,
                text: utext,
            }
            console.log(id);
            console.log(uname);
            console.log(utext);
            console.log(this.editedComment)
            axios.put(`http://win.cim.local:3001/usercomments/${id}`, editedComment )

            .then((Result) => {
                console.log(Result);
           })
           .catch((error) => {
               console.log(error);
           })

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