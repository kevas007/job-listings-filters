<template>
    <div class="app">
        <div :class=" ajout.length > 0 ? 'sche flex justify-evenly h-16 border shadow-md bg-white' : 'dis'">
            <div class="flex justify-center align-center" v-for="(aj, index) in ajout" :key="index">
                <h5>
                    {{ aj }}
                    <button @click="eff">X</button>
                </h5>
            </div>

            <div :class="ajout.length > 0 ? 'flex justify-end' : 'dis'">
                <button @click="del">Clear</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            // display: false
        };
    },

    props: {
        ajout: {
            type: Array,
        },
    },
    methods: {
        eff() {
            this.ajout.splice(this.index, 1);
            console.log(this.ajout);
        },
        del() {
            this.ajout.splice(this.index,this.ajout.length);
            console.log(this.ajout);
        },
        clear() {
            if (this.ajout.length > 0) {
                this.display = true;
            }

        }

    },
};
</script>

<style scoped>
.sche {
    width: 900px;
    margin-left: 23%;
}
.dis{
    display: none;
}
</style>
