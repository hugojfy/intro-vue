<template>
    <div class="form">
    <div class="form-group">
        <label>Título</label>
        <input  class="form-control" v-model="quote.title" type="text">
    </div>
    <br/>
    <div class="form-group">
        <label>Nota: </label>
        <textarea class="form-control" v-model="quote.text"></textarea>
    </div>
    <br/>
    <div class="form-group">
        <button @click="onClick" class="btn btn-primary">
            Agregar nota
        </button>
    </div>
    </div>
</template>

<script>
export default {
    name:"Form",
    props:{
        quoteContainer:{
            type: Array
        }
    },
    components:{
        
    },
    data() {
        return {
            quote:{
                title:'ejemplo',
                text:'ejemplo'
            }
        }
    },
    methods:{
        onClick(){
            if(this.quote.title.length>3 && this.quote.text.length>3){
                this.quoteContainer.push(this.quote);//add the quote
                this.quoteContainer= this.quoteContainer.reverse();//Reverse de array. LIFO
                this.quote={};
            }
        }
    }    
}
</script>
