<template>
    <div>
        <h2>{{ title }}</h2>
        <img 
            :src="src" 
            :alt="alt" 
            :class="[isActive ? 'hasBorder' : 'noBorder']" 
            @click="toggleBorder()"
        />
       <p>{{ alt }}</p>
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
                console.log('test')
            }
        }
    }
    export default {
        name: 'imgGen',
        props: {
            title: String, 
            src: String, 
            alt: String,
        },
        mixins: [toggleBorder],
    }
</script>

<style scoped>
p {
    font-style: italic;
}
img {
    margin: 0 3rem 1rem 3rem;
    max-width: 75%;
    min-width: 75%;
}
.hasBorder {
    border: 3px solid rgb(6, 48, 7);
}
.noBorder {
    border: none;
}
</style>