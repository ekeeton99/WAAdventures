<template>
    <div>
        <article
        :class="[isActive ? 'highlight' : 'normal']" 
        @click="toggleBorder()">
            <h3>{{ time }}</h3>
            <p>High: {{ high }}°</p>
            <p>Low: {{ low }}°</p>
            <p>UV Index: {{ uv }}</p>
        </article>
    </div>
</template>

<script>
const toggleBorder = {
    data() {
        return{
            isActive: false,
        }
        },
    methods: {
        toggleBorder() {
            this.isActive = !this.isActive;
        }
    }
}
export default {
    name: 'card',
    props: {
        time: String,
        high: Number,
        low: Number,
        uv: Number
    },
    mixins: [toggleBorder],
}
</script>

<style>
.highlight {
    background-color: white;
    border: 5px solid rgb(27, 194, 255);
}
.normal{
    background-color: white;
    border: 3px solid rgb(6, 48, 7); 
}
</style>