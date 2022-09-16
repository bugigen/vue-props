<template>
    <div class="wrapper-parent">
        <h1>Props</h1>

        <props-example name="John" last-name="Johns" :number="1"></props-example>
        <props-example name="Eric" :number="2"></props-example>
        <props-example :name=dataName :last-name=dataLastName :number=dataNumber></props-example>
        <props-example name="Ben" :last-name="computedName"></props-example>
        <br>

        <div class="input">
            <label for="inputName">Name: </label>
            <input v-model="dataName" type="text" id="inputName">
        </div>
        <div class="input">
            <label for="inputLastName">Last Name: </label>
            <input v-model="dataLastName" type="text" id="inputLastName">
        </div>
        <div class="input">
            <label for="inputNumber">Number: </label>
            <input v-model="dataNumber" type="text" id="inputNumber">
        </div>
    </div>
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

    .input {
        margin-bottom: 10px;
    }

    margin-left: 50px;
}

</style>
