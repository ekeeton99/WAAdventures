<template>
    <div>
        <article class="card">
            <h3>{{ time }}</h3>
            <p>High: {{ high }}</p>
            <p>Low: {{ low }}</p>
            <p>UV Index: {{ uv }}</p>
        </article>
    </div>
</template>

<script>
export default {
    props: {
        time: String,
        high: String,
        low: String,
        uv: String
    }
}
</script>

<style>
.card {
    border: 3px solid rgb(6, 48, 7);
}
</style>