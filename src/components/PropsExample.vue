<template>
    <div class="wrapper-child">
        Hello, {{ name }} {{lastName}} {{ number }}!
    </div>
</template>

<script>
export default {
    name: "PropsExample",
    props: {
        name: {
            type: String,
            required: true
        },
        lastName: {
            type: String,
            required: false,
            default: 'Unknown-last-name'
        },
        number: {
            type: Number,
            required: false,
            default: 0
        }
    }
}
</script>

<style scoped>
.wrapper-child {
    margin: 0 0 10px 30px;
}
</style>