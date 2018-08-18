<template>
    <div>
        <b-form-input
            v-model="count"
            type="text"
            class="text-center mb-4"
            disabled
        >
        </b-form-input>

        <b-button
            size="lg"
            block
            class="text-white"
            variant="primary"
            @click="increment"
        >
            Incrementar
        </b-button>

        <h1 class="text-center">{{ count }}</h1>

        <b-button
            size="lg"
            block
            class="text-white"
            variant="warning"
            @click="decrement"
        >
            Decrementar
        </b-button>
    </div>
</template>

<script>
    import {mapState, mapMutations} from 'vuex'
    export default {
        methods: {
            ...mapMutations(['increment', 'decrement']),
        },
        computed: {
            ...mapState(['counter']),
            count: {
                get () {
                    return this.counter
                },
                set (val) {
                    console.log(val)
                }
            }
        }
    }
</script>
