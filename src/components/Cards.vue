<template>
    <div class="app">
        <div
            class="cards max-w-2xl px-8 py-4 mx-auto bg-white rounded-lg dark:bg-gray-800 flex justify-between align-center"
        >
            <div class="left flex">
                <div class="border ">
                    <!-- <img :src="" alt /> -->
                    <img :src="data.logo" alt />
                </div>
                <div>
                    <div class="flex justify-around">
                        <span >{{ data.company}}</span>
                        <h5  :class=" data.new ==true ? 'text-white bg-blue-800 pl-1 pr-1 rounded-lg ml-1 mr-1' : 'texts'" >New !</h5>
                        <h4 :class=" data.featured ==true ? 'text-white bg-gray-700 pl-1 pr-1 rounded-lg ml-1 mr-1' : 'texts'">Featured</h4>
                    </div>
                    <h1>{{ data.position }}</h1>
                    <div>
                        <span>{{ data.postedAt }}</span>
                        <span>{{ data.contract }}</span>
                        <span>{{ data.loaction }}</span>
                    </div>
                </div>
            </div>
            <div class="right" v-for="(lang, index) in data.languages" :key="index">
                <span>{{ lang }}</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        data: {
            type: Object,
            required: true
        }
    },
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
