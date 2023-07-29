<template>
    <div class="progress-bar-container">
        <div class="progress-bar" :style="{ width: progress + '%' }"></div>
    </div>
</template>
  
<script>
export default {
    props: {
        progress: {
            type: Number,
            required: true,
        },
    },
};
</script>
  
<style>
.progress-bar-container {
    width: 80%;
    margin: auto;
    margin-top: 20px;
    background-color: #f2f2f2;
    border-radius: 4px;
    overflow: hidden;

}

.progress-bar {
    height: 20px;
    background-color: #4caf50;
    border-radius: 4px;
    transition: width 0.3s ease;
}
</style>
  