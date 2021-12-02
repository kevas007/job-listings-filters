<template>
    <div>
    <nav>
        <div class="w-full">
            <div class="app w-full h-40"></div>
        </div>
    </nav>
    </div>
</template>

<script>
export default {
    name:'Nav',

}
</script>
<style scoped>
.app {
    background-image: url('../assets/bg-header-desktop.svg');
    background-repeat: repeat-x;
     box-shadow: hsl(180, 14%, 20%) 0px 1px 5px 0px;
}
</style>