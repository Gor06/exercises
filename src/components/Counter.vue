<template>
    <v-container>
        <v-btn rounded @click="add" :color="color">Counter<slot></slot> {{ count }}</v-btn>
    </v-container>
</template>
<script>
export default {
    name:'Counter',
    props:{
        color:String
    },
    data:()=>({
        count:0
    }),
    methods: {
        add: function () {
            this.count++
        }
    }
}
</script>

