<template>
  <div>
    <b-list-group v-for="domain in domains" :key="domain">
        <b-list-group-item>{{domain}}</b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
import bus from '../bus'
export default {
    data(){
        return{
            prefixes: [],
            suffixes: [],
            domains: []
        }
    }, 
    methods:{
        generate(){
            for( const prefix of this.prefixes){
                for (const suffix of this.suffixes){
                    this.domains.push(prefix + suffix)
                }
            }
        }
    },
    created(){
        bus.$on('generate', prefixe =>{
            this.prefixes.push(prefixe)
            this.generate()
        }),
        bus.$on('generate', suffixe =>{
            this.suffixes.push(suffixe)
            this.generate()
        })
    }
}
</script>

<style>

</style>