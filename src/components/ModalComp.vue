<template>
    <transition name="modal" v-if="showModal">
        <div class="modal-mask">
          <div class="modal-wrapper">
            <div class="modal-container">

              <div class="modal-header">
                <slot name="header">
                  
                </slot>
              </div>

              <div class="modal-body">
                <slot name="body">
                  
                </slot>
              </div>

              <div class="modal-footer">
                <slot name="footer">
                  
                  <button class="modal-default-button" @click="showModal = false">
                    Fechar
                  </button>
                </slot>
              </div>
            </div>
          </div>
        </div>
    </transition>

</template>
<script setup>

defineProps({
  showModal: {
    type: Boolean,
    required: true
  }
})
</script>
