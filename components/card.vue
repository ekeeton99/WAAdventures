<template>
    <div>
        <article
        class="default"
        :class="[isActive ? 'highlight' : 'normal']" 
        @click="toggleBorder()">
            <div class="pt-3 pl-3 pr-3">
                <h3>{{ time }}</h3>
                <p>High: {{ high }}°</p>
                <p>Low: {{ low }}°</p>
                <p>UV Index: {{ uv }}</p>
            </div>
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
    border: 5px solid rgb(0, 186, 25);
}
.normal{
    border: 3px solid rgb(6, 48, 7); 
}
.default {
    margin: 1rem auto;
    max-width: 70%;
    background-color: white;
}
</style>