<template>
    <nav class="headerNav">
        <div class="headerHome">
            <h2 class="homeIcon">Home</h2>
        </div>
        <div class="headerCallTo">

        </div>
    </nav>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.headerNav{
    display: grid;
    align-items: center;
    width: 100%;
    grid-template-columns: 0.5fr 1fr;
    justify-items: center;
    >.headerHome{
        display: grid;
    }

    >.headerCallTo{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }
}
</style>