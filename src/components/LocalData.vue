<template>
    <div>
        <div v-for="product in products" :key="product">
            {{product.productName}}
        </div>
    </div>
</template>

<script>
import data from '../../data';
import axios from 'axios';
import { response } from 'express';

    export default {
        name: 'local-data',
        data(){
            return{
                products: null
            }
        },

        created() {
            axios.get('data.js')
                .then(response => {
                    this.products = response.data
                })
                .catch(e => {
                    this.errors.push(e)
                })
        }
    }
</script>

<style lang="scss" scoped>

</style>