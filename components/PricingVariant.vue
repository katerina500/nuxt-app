<template>
    <div class="card" :class="{ ['card-' + data.color]: true}">
       <h3>{{ data.title }}</h3>
       <br>
       <h2>{{  data.price }}</h2>
       <br>
       <br>
       <ul>
        <li v-for="element, index in data.features" :key="index">{{ element }}</li>
       </ul>
    </div>
</template>

<script>
export default {
    props: ['data'],
} 
</script>

<style scoped>
.card{
    text-align: center;
    border-width: 0px 1px 1px;
    border-style: solid;
    border-color: rgb(214, 214, 214);
    border-image: initial;
    border-radius: 0px 0px 6px 6px;
    padding: 22px 40px;
    line-height: 1.5;
    color: rgb(106, 106, 106);
    position: relative;
}
.card::before {
    content: "";
    position: absolute;
    background: rgb(229, 229, 229);
    top: -8px;
    left: -1px;
    width: calc(100% + 2px);
    height: 8px;
    border-radius: 6px 6px 0px 0px;
}
.card-grey::before {
    background: rgb(229, 229, 229);
}
.card-green::before {
    background: rgb(15, 169, 88);
}
.card-blue::before {
    background: rgb(85, 81, 255);
}
.card-orange::before {
    background: rgb(242, 78, 30);
}
.card-violet::before {
    background: rgb(162, 89, 255);
}
ul {
    margin: 0;
    padding: 0;
}
li {
    margin-bottom: 8px;
    padding-left: 24px;
}
</style>