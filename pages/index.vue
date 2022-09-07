<template>
  <div class="flex flex-col justify-center">
    <div>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Atque autem, consectetur consequatur dolorum ducimus eveniet, exercitationem hic illum maxime mollitia possimus quibusdam sed soluta suscipit, voluptate. Accusantium beatae laboriosam quis.</p>
      <button @click="isVisible = true">MODAL</button>
      <DiceModal :is-visible="isVisible" @cancel="isVisible = false" @confirm="isVisible = false">
        <template v-slot:title>
<!--          <p>Model Title Example</p>-->
        </template>
        <template v-slot:body>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium aspernatur consectetur cupiditate, debitis, deserunt error facilis laboriosam laborum libero nam nisi odit rem repellendus repudiandae similique tempore veniam vero voluptatem.</p>
        </template>
<!--        <template v-slot:footer></template>-->
        <template v-slot:cancelButton>
          <button>MyCancelBtn</button>
        </template>
      </DiceModal>
    </div>
  </div>
</template>

<script>
  import DiceModal from "~/components/util/DiceModal";

export default {
  name: 'IndexPage',
  components: {DiceModal},
  data() {
    return {
      isVisible: false
    }
  },
}
</script>
