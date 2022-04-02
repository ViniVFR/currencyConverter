<template>
    <div class="converter">
        <h2>{{currencyA}} To {{currencyB}}</h2>
        <input
            type="text"
            v-bind:placeholder="currencyA"
            v-model="currencyAValue"
        >
        <input
            type="button" 
            value="Convert"
            v-on:click="convert()"
        >
        <h3>{{currencyB}} {{currencyBValue}}</h3>
    </div>
</template>

<script>

export default {
    name: "wConverter",
    props: [
        "currencyA",
        "currencyB",
    ],
    data(){
        return{
            currencyAValue: "",
            currencyBValue: 0
        }
    },
    methods: {
        convert(){
            if(this.currencyAValue == "") return this.currencyAValue = 0;
            
            let fromTo = this.currencyA + "_" + this.currencyB;
            let url = "https://free.currconv.com/api/v7/convert?q=" + fromTo + "&compact=ultra&apiKey=c5c18ab78cb5344353da";

            fetch(url)
                .then(res =>{
                    return res.json();
                })
                .then(json =>{
                    let sum = 0;
                    let price = json[fromTo];
                    sum = price * parseFloat(this.currencyAValue);
                    this.currencyBValue = sum.toFixed(2);
                })
        }
    }
};
</script>

<style scoped>
.converter{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 4px rgba(0, 0, 0, 0.2);
}
</style>