<template>
    <div class="wrapper-parent">
        <h1>Props</h1>

        <props-example
            name="John"
            last-name="Johns"
            :number="1"
        />
        <props-example
            name="Eric"
            :number="2"
        />
        <props-example
            :name="dataName"
            :last-name="dataLastName"
            :number="dataNumber"
        />
        <props-example
            name="Ben"
            :last-name="computedName"
        />
        <br>

        <div class="input input-group input-group-sm">
            <label for="inputName" class="input-group-text">Name: </label>
            <input
                id="inputName"
                v-model="dataName"
                type="text"
                class="form-control text-primary border-primary border border-3"
            >
        </div>
        <div class="input input-group input-group-sm">
            <label for="inputLastName" class="input-group-text">Last Name: </label>
            <input
                id="inputLastName"
                v-model="dataLastName"
                type="text"
                class="form-control text-danger border-danger border border-3"
            >
        </div>
        <div class="input input-group input-group-sm">
            <label for="inputNumber" class="input-group-text">Number: </label>
            <input
                id="inputNumber"
                v-model="dataNumber"
                type="text"
                class="form-control text-success border-success border border-3"
            >
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
@import '~bootstrap/dist/css/bootstrap.css';

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

    margin: 0 50px;
}

</style>
