<template>
  
<html>

<body>
    <!-- SHOW ALL -->
    <button onclick="getAny()">send to db</button>
     <p id="output"></p>

    <!-- CREATE USER -->
    <form id="createUser">
        <div>
        <input type="name" id="name">
        </div>
        <div>
        <textarea name="email" id="email" cols="30" rows="10"></textarea>
        </div>
        <input type="submit" value="Submit" onclick="createUser()">
    </form>

    <!-- UPDATE USER -->

    <form id="updateUser">
        <div>
        <input type="number" id="idu">
        </div>
        <div>
        <input type="nameu" id="nameu">
        </div>
        <div>
        <textarea name="emailu" id="emailu" cols="30" rows="10"></textarea>
        </div>
        <input type="submit" value="Submit" onclick="updateUser()">
    </form>
    
    <!-- DELETE USER -->
    <div>
    <input type="text" name="userid" id="userid">
    <button onclick="deleteUser()">Delete User</button>
    </div>

    
<button v-on:click="getAny()">getany</button>
<input type="text" id="idu">
<button v-on:click="deleteUser()">delete user</button>
<button v-on:click="tryPost()">addUser</button>

<input type="text" placeholder="name" v-model="User.name">
<input type="text" placeholder="email" v-model="User.email">
<button v-on:click="addUser()">addUser</button>

     <div v-for="user in users" :key="user.id">
        <li :to="'/users/' + user.id">{{user.name + " " + user.email}}</li>
     </div>

</body>




</html>
</template>

  
<script>

import axios from 'axios'

export default {

    data() {
        return{
            User: {name: '' , email: ''},
        }
    },

    async asyncData() {
        const{data} =await axios.get('http://win.cim.local:3001/users')
        return {users:data}

    },

    methods: {

     addUser(){
         let newUser = {
             name: this.User.name,
             email: this.User.email,
         }
         console.log(newUser);
         axios.post('http://win.cim.local:3001/users/' ,newUser)
         .then((Response) => {
             console.log(response);
         })
         .catch((error) => {
             console.log(error);
         })
     },


    // //  deleteUser: async function(){
    // //     let idu = document.getElementById('idu');
    // //     await axios.delete(`http://win.cim.local:3001/users/${idu}`)
    // //     return asyncData()

    // //  },

    // //  getAny: function(){
    // //          axios.post('http://win.cim.local:3001/users', {
                
    // //             name: "testname",
    // //             email: "Testemail"
                 
    // //         })
    // //     },
        
    // // tryPost(){

    // //     let name = document.getElementById('name').value;
    // //     let email = document.getElementById('email').value;
        
    // //     axios.post('http://win.cim.local:3001/users', {  
    // //         method: 'POST',
    // //             headers: {
    // //                 'Accept': 'application.json, text/plain, */*',
    // //                 'Content-type':'application/json'
    // //             },
    // //             body:JSON.stringify({name, email})
    // //         })
    // //         .then((res) => res.json())
    // //         .then((data) => console.log(data))
    // //     }
    


    }
        
}
   



//     export default {
//     data(){
//         return{
           
//         }  
//     },

//     methods: {
    
//         getAny: function(){
//             fetch('http://win.cim.local:3001/users')
//                 .then(response =>{ console.log(response); return response.json()} )
//                 .then(data => { 
//                     let output = '<h2>User</h2>'
//                     data.forEach(function(user){
//                         output += `
//                             <ul>
//                                 <li>ID: ${user.id}</li>
//                                 <li>User: ${user.name}</li>
//                                 <li>Email: ${user.email}</li>
//                             </ul>
//                         `;
//                     });
//                     document.getElementById('output').innerHTML = output;
//                 })
//           },

//         async getAny(){
//             const response = await fetch('http://win.cim.local:3001/users');
//             console.log(response);
//             const data = await response.json();
//             let output = '<h2>User</h2>'
//             data.forEach(function(user){
//                 output += `
//                     <ul>
//                         <li>ID: ${user.id}</li>
//                         <li>User: ${user.name}</li>
//                         <li>Email: ${user.email}</li>
//                     </ul>
//                 `;
//             });
//             document.getElementById('output').innerHTML = output;

//           },

//         tryingFetch() {
//             fetch('http://win.cim.local:3001/users')
//                 .then(response =>{ console.log(response); return response.json()} )
//                 .then(data => { 
//                     let output = '<h2>User</h2>'
//                     data.forEach(function(user){
//                         output += `
//                             <ul>
//                                 <li>ID: ${user.id}</li>
//                                 <li>User: ${user.name}</li>
//                                 <li>Email: ${user.email}</li>
//                             </ul>
//                         `;
//                     });
//                     document.getElementById('output').innerHTML = output;
//                 })
//         },

//         async asyncData({ $axios }) {
//          const ip = await $axios.$get('http://icanhazip.com')
//         return { ip }
// }
//     }

// }
</script>
    