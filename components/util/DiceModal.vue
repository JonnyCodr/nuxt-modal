<template>
  <div v-if="isVisible">
    <div class="fixed inset-0 z-50 flex justify-center items-center overflow-x-hidden" @click="emitCancel">
      <div class="flex flex-col min-w-5xl max-w-2xl rounded shadow-lg bg-white">
        <div class="p-2">
          <div class="flex justify-between items-start">
            <h3 class="text-2xl font-semibold"><slot name="title"></slot></h3>
            <button class="p-1 leading-none">
              <div class="text-xl h-3 w-3">
                <span class="font-light hover:font-extrabold" @click="emitCancel">X</span>
              </div>
            </button>
          </div>
        </div>
        <div class="p-6">
          <slot name="body"></slot>
        </div>
<!--        <slot title="footer">-->
<!--          <div class="p-6 flex justify-end items-center">-->
<!--            <button @click="emitCancel">-->
<!--              <slot name="cancelButton">-->
<!--                <button @click="emitCancel">Cancel</button>-->
<!--              </slot>-->
<!--            </button>-->
<!--            <button @click="emitConfirm">-->
<!--              <slot name="confirmButton">-->
<!--                <button class="ml-2" @click="emitCancel">Confirm</button>-->
<!--              </slot>-->
<!--            </button>-->
<!--          </div>-->
<!--        </slot>-->
      </div>
    </div>
    <div class="opacity-60 bg-black fixed inset-0 z-40 bk-black"></div>
  </div>
</template>

<script>
export default {
  name: "DiceModal",
  props: {
    isVisible: false
  },
  methods: {
    emitCancel() {
      this.$emit('cancel')
    },
    emitConfirm() {
      this.$emit('confirm')
    }
  }
}
</script>

<style scoped>

</style>
