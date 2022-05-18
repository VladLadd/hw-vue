<template>
<div class="dialog" @click="closeModal">
    <div class="window">
        <i class="close" @click="closeModal" @keydown.esc="closeModal">
            &times;
        </i>
        <h1>Hello World!</h1>
    </div>

</div>
</template>

<script>
export default {
    name: "modal-dialog",
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
.dialog {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
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
}
.window {
    z-index: 100;
    background: #fff;
    width: 600px;
    max-width: 100%;
    border-radius: 10px;
    transition: transform 0.15s ease 0s, opacity 0.15s ease 0s;
    transform: scale(1);
}
.close {
    position: absolute;
    top: 5px;
    right: 10px;
    font-size: 30px;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    font-style: normal!important;
    cursor: pointer;
}
</style>
