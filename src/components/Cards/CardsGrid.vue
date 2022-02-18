<template>
    <div class="card-grid">
    <h2>Mis Notas:</h2>
        <div class="row">
            <div class="col-sm-3"  v-for="(quote, index) in quoteContainer" :key="index" >
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">{{quote.title}}</h5>
                        <p class="card-text">{{quote.text}}</p>
                        <a @click="deleteQuote(index)" href="#" class="btn btn-primary">Eliminar</a>
                    </div>
                </div> 
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "CardsGrid",
    components:{

    },
    props:{
        quoteContainer:{
            type:Array
        }
    },
    methods:{
        deleteQuote(index){
            if (index > -1) {
                this.quoteContainer.splice(index, 1); // 2nd parameter means remove one item only
            }
        }
    }
}
</script>