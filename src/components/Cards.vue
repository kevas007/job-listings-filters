<template>
    <div class="app">
        <div
            class="cards max-w-2xl px-8 py-4 mt-10 mx-auto bg-white rounded-lg dark:bg-gray-800 flex justify-between align-center"
        >
            <div class="left flex">
                <div class="border">
                    <!-- <img :src="" alt /> -->
                    <img :src="data.logo" alt />
                </div>
                <div>
                    <div class="flex justify-around">
                        <span>{{ data.company }}</span>
                        <h5
                            :class="data.new == true ? 'text-white bg-blue-800 pl-1 pr-1 rounded-lg ml-1 mr-1' : 'texts'"
                        >New !</h5>
                        <h4
                            :class="data.featured == true ? 'text-white bg-gray-700 pl-1 pr-1 rounded-lg ml-1 mr-1' : 'texts'"
                        >Featured</h4>
                    </div>
                    <h1>{{ data.position }}</h1>
                    <div>
                        <span>{{ data.postedAt }} -</span>
                        <span>{{ data.contract }} -</span>
                        <span>{{ data.location }}</span>
                    </div>
                </div>
            </div>
            <div class="right" v-for="(lang, index) in data.languages" :key="index">
                <button @click="tags" >{{ lang }}</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            test:[],
        };
    },
    props: {
        data: {
            type: Object,
            required: true
        }
    },
    methods: {
        tags(e) {
            this.test.push(e.target.innerText);
            // console.log(this.test);
            this.$emit('tags', this.test);
        },
     
    }
};
</script>
<style scoped>
.cards {
    box-shadow: hsl(180, 14%, 20%) 0px 5px 10px 0px;
}
.texts {
    display: none;
}
</style>
