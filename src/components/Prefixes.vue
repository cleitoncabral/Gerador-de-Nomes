<template>
    <div>
        <b-card header="Prefixos">
            <b-list-group v-for="prefixe in prefixes" :key="prefixe">
                <b-list-group-item>{{prefixe}}</b-list-group-item>
            </b-list-group>
            <b-input-group>
                <b-input type="text" v-model="prefixe" @keyup.enter="addPrefixe(prefixe)"></b-input>
                <b-input-group-append >
                    <b-button variant="info" @click="addPrefixe(prefixe)" placeholder="Escreva o prefixo">+</b-button>
                </b-input-group-append>
            </b-input-group>
        </b-card>
    </div>
</template>

<script>
import bus from '../bus.js'
export default {
    data() { 
        return {
            prefixe: '',
            prefixes: []

        }
    },
    methods:{
        addPrefixe(prefixe){
            this.prefixes.push(prefixe)
            bus.$emit('generate', prefixe)
            this.prefixe = ''
        }
    }
}
</script>

<style>

</style>