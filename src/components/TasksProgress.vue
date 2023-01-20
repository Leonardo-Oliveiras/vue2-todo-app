<template>
    <div class="tasks-progress">
        <span class="progress-value"> {{ progress }} % done</span>
        <div class="progress-bar" :style="{width: progress + '%'}"></div>
    </div>
</template>

<script>
export default {
    props: {
        progress: { type: Number, default: 0 }
    }
}
</script>

<style>
    .tasks-progress {
        position: relative;
        width: 80%;
        border: 1px solid #fff;
        color: #FFF;
        border-radius: 8px;
        margin: 0.5rem;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .progress-bar {
        position: absolute;
        border-radius: 0.5rem;
        height: 100%;
        background-color: #4CAF50;
        align-self: flex-start;
    }

    .progress-value {
        z-index: 1;
        font-size: 1.5rem;
        font-weight: 500;
    }
</style>