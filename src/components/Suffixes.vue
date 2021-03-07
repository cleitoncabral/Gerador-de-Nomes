<template>
    <div>
        <b-card header="Sufixos">
            <b-list-group v-for="suffixe in suffixes" :key="suffixe">
                <b-list-group-item>{{suffixe}}</b-list-group-item>
            </b-list-group>
            <b-input-group>
                <b-input type="text" v-model="suffixe" @keyup.enter="addSuffixe(suffixe)"></b-input>
                <b-input-group-append >
                    <b-button variant="info" @click="addSuffixe(suffixe)" placeholder="Escreva o prefixo">+</b-button>
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
            suffixe: '',
            suffixes: []
        }
    },
    methods:{
        addSuffixe(suffixe){
            this.suffixes.push(suffixe)
            bus.$emit('generate', suffixe)
            this.suffixe = ''
        }
    }
}
</script>

<style>

</style>