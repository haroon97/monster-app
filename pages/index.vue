<template>
    <div class="container">
        <Player name="User" />
        <Player name="Monster" />
        <div class="btn-container">
            <button @click="$nuxt.$emit('attack')" class="btn btn-danger">Attack</button>
            <button class="btn btn-info">Heal</button>
            <button class="btn btn-warning">Special Attack</button>
            <button class="btn btn-secondary">Reset</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            turn: 'User',
        }
    }
}
</script>

<style scoped>
    .container {
        margin-top: 1.5rem;
    }
    .btn-container {
        display: flex;
        justify-content: center;
        padding-top: 2rem;
    }
    .btn {
        margin-left: 1rem;
        margin-right: 1rem;
    }
</style>
