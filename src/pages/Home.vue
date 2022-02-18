<template>
    <div class="padre">
        <h1 class="title">{{title}}</h1>
        <Form :quoteContainer="quoteContainer"/>
        <Cards :quoteContainer="quoteContainer"/>

    </div>
</template>

<script>
//import Form from '../components/Forms';
import Cards from '../components/Cards';

export default {
    name:"Home",
    components:{
        Form:()=>import('../components/Forms'),
        Cards
    },
    data(){
        return{
            title:" Gestión de notas",  
            quoteContainer:[]
        }
    }

}
</script>

<style scoped>
.padre.title #h1{

} 
</style>