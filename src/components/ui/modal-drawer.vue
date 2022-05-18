<template>
    <div class="drawer">

        <i class="close" @click="closeModal" @keydown.esc="closeModal">
            &times;
        </i>
        <h1 class="white">Hello World!</h1>
    </div>

</template>

<script>
export default {
    name: "modal-drawer",
    props: {
        value: Boolean,
    },
    methods: {
        closeModal() {
            this.$emit("input", false);
        }
    }
}
</script>

<style scoped>
.drawer {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    overflow: hidden;
    overflow-y: auto;
    -webkit-overflow-scrolling: touch;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
    z-index: 99;
    padding:30px 0;
    width: 100%;
    height: 100%;
    background: #2c3e50;
}
.white {
    color: #ffffff;
}
.close {
    position: absolute;
    top: 10px;
    right: 20px;
    font-size: 30px;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    font-style: normal!important;
    cursor: pointer;
    color: #ffffff;
}
</style>
