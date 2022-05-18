<template>
  <div class="hello">
          <button class="btn" @click="show">
             SHOW
          </button>

      <transition name="fade">
          <modal-dialog v-if="modalShow" v-model="modalShow" @input="modalShow = $event" />
      </transition>
      <transition name="fade">
          <modal-drawer v-if="drawerShow" v-model="drawerShow" @input="drawerShow = $event" />
      </transition>
      <div v-if="modalShow" class="dialog__shadow dialog__shadow--show"></div>
  </div>
</template>

<script>
import ModalDialog from "@/components/ui/modal-dialog";
import ModalDrawer from "@/components/ui/modal-drawer";
export default {
  name: 'HelloWorld',
    components: {ModalDrawer, ModalDialog},
    props: {
    msg: String
  },
    data() {
      return {
          modalShow: false,
          drawerShow: false
      }
    },
    methods: {
        ololo() {
            console.log('ololo')
        },
      show() {
          const width = document.documentElement.clientWidth
          if (width >= 768 ) {
              this.modalShow = true
          } else {
              this.drawerShow = true
          }
          console.log(width)
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.btn {
    width: 100px;
    height: 40px;
    border-radius: 10px;
}
.dialog__shadow{
    position: fixed;
    border:none;
    display: block;
    width: 100%;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    overflow: hidden;
    pointer-events: none;
    z-index: 98;
    opacity: 0;
    transition: opacity 0.15s ease;
    background-color: black;
}
.dialog__shadow--show{
    pointer-events: auto;
    opacity: 0.6;
}
</style>
