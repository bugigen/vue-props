<template>
    <div class="wrapper-parent">
        <h1>Props</h1>
    </div>

    <props-example name="John" last-name="Johns" :number="1"></props-example>
    <props-example name="Eric" :number="2"></props-example>
    <props-example :name=dataName :last-name=dataLastName :number=dataNumber></props-example>
    <props-example name="Ben" :last-name="computedName"></props-example>
</template>

<script>
import PropsExample from "@/components/PropsExample";

export default {
    name: 'App',
    components: {
        PropsExample,
    },
    data() {
        return {
            dataName: 'George',
            dataLastName: 'Georges',
            dataNumber: 3
        }
    },
    computed: {
        computedName() {
            return `${this.dataName} ${this.dataLastName}`;
        }
    }
}
</script>

<style lang="scss">
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

body {
    background: peachpuff;
    font-family: Consolas, cursive;
}

.wrapper-parent {
    h1 {
        text-align: center;
        margin-bottom: 20px;
    }
}
</style>
