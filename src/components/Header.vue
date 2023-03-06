<template>
    <header class="main-header">
        <div class="container">
            <h1>{{ title }}</h1>
        </div>
    </header>
</template>


<script>
export default {
    data() {
        return {
            title: 'Yu-gi-oh! Card list API'
        }
    }
}
</script>

<style lang="scss" scoped>
.main-header {
    text-align: center;
    font-size: 28px;
    padding: 30px 0;
    text-shadow: 4px 4px rgb(25, 21, 21);
}
</style>