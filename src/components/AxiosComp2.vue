<template>
    <div>
        <div v-for="drink in drinks" :key="drink" class="drink">
            {{drink.drinks.strCategory}}
        </div>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: 'drink-api',
        data(){
            return{
                posts: null
            }
        },

        created() {
            axios.get(`https://www.thecocktaildb.com/api/json/v1/1/list.php?c=list`)
                .then(response => {
                    this.posts = response.data
                })
                .catch(e => {
                    this.errors.push(e)
                })
        }
        
    }
</script>

<style lang="scss" scoped>

</style>