<template>
    <div class="bar">
        <span class="porcentage">{{progress}}%</span>
        <div class="sucessBar" :style="{width: progress + '%'}" >
        </div>
    </div>
</template>

<script>
export default {
    props: {
        progress: { type: Number, default: 0 }
    }
}
</script>

<style scoped>
    .bar {
        position: relative;
        width: 80%;
        border: 1px solid white;
        color: #fff;
        border-radius: 8px;
        margin-bottom: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 1.8rem;
    }
    .sucessBar {
        position: absolute;
        border-radius: 8px;
        align-self: flex-start;
        height: 100%;
        background: #4caf50;
        
    }
    .porcentage {
        z-index: 1;
        font-size: 1.5rem;
    }
</style>