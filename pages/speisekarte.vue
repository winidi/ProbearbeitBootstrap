<template>
        <div class="container">
                        <div class="row">
                            <div class="col-lg-10">
                        <h1>Speisekarte</h1>
                        <div class="row">
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Pilzsuppe</h2>
                        <h3>mit frischen Pilzen der Saison</h3>
                        <button v-on:click="addPilz()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1 ">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                    <h2>TomatenSuppe</h2>
                        <h3>mit frischen Tomaten</h3>
                        <button v-on:click="addTomate()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Kräutersuppe</h2>
                        <h3>mit Kräutern der Provinz</h3>
                        <button v-on:click="addKraeuter()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="cont" ></div>
                    
                                </div>
                        <div class="row">
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Pilzsuppe</h2>
                        <h3>mit frischen Pilzen der Saison</h3>
                        <button v-on:click="addPilz()" class="btn  btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                    <h2>TomatenSuppe</h2>
                        <h3>mit frischen Tomaten</h3>
                        <button v-on:click="addTomate()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Kräutersuppe</h2>
                        <h3>mit Kräutern der Provinz</h3>
                        <button v-on:click="addKraeuter()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="cont" ></div>
                    
                        </div><div class="row">
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Pilzsuppe</h2>
                        <h3>mit frischen Pilzen der Saison</h3>
                        <button v-on:click="addPilz()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                    <h2>TomatenSuppe</h2>
                        <h3>mit frischen Tomaten</h3>
                        <button v-on:click="addTomate()" class="btn btn-warning float-right">zufügen</button>
                        </div>
                        <div class="col-sm-1">
                        </div>
                        <div class="col-sm-2 d-flex flex-column">
                        <h2>Kräutersuppe</h2>
                        <h3>mit Kräutern der Provinz</h3>
                        <button v-on:click="addKraeuter()" class="btn btn-warning float-right" >zufügen</button>
                        </div>
                        <div class="cont" ></div>
                    </div>
                    
                        
                </div>
                 
                 <div class="col-xs-12 ">
                
                       
                    <div v-if="this.pilzsuppe || this.tomatensuppe || this.kraeutersuppe" class="containerbestellungen position-fixed">
                        <h1>Bestellung</h1>
                        
                        <h3>{{this.pilzsuppe}}</h3>
                        <h3>{{this.tomatensuppe}}</h3>
                        <h3>{{this.kraeutersuppe}}</h3>
                    </div>   
                    
                 
                 </div>
            </div>
        </div>
</template>


<script>
export default {
    data(){
        return{
            test: 12,
            pilzint: 0,
            pilzsuppe: '',
            tomateint: 0,
            tomatensuppe: '',
            kraeuterint: 0,
            kraeutersuppe: '',
        }  
    },

    methods: {
        addPilz: function(){
            this.pilzint = this.pilzint +1;
            this.pilzsuppe = this.pilzint + ' x Pilzsuppe'
            
        },
        addTomate: function(){
            this.tomateint = this.tomateint +1;
            this.tomatensuppe = this.tomateint + ' x Tomatensuppe'
        },
        addKraeuter: function(){
            this.kraeuterint = this.kraeuterint +1;
            this.kraeutersuppe = this.kraeuterint + ' x Kräutersuppe'
        }

    }
}
</script>

<style scoped>

.container{
    padding-bottom: 3.2em;
}

.btn{
    margin-top: auto;
}

.col-xs-6 {
    background-color: red;
}


.cont {
    background-color: indigo;
    
    }

.row{
    padding-top: 4em;
    
    
}

.col-sm{
    border: 8px solid grey;
    
}
.btnspeisekarte {
    float: right;
}

</style>