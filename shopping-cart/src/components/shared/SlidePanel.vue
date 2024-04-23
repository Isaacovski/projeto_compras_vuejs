<script setup>
import { defineProps, defineEmits } from 'vue'; // Importando defineProps e defineEmits

// Definindo props e tipos
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  visible: { // Corrigindo aqui
    type: Boolean, // Corrigindo aqui
    required: true
  }
});

// Definindo eventos
const emit = defineEmits(['update:visible']);

const closePanel = () => {
  emit('update:visible',false)
}
</script>

<template>
  <div class="panel-wrap" :class="{visible: visible}" >
    <div class="panel">
      <div>
        <!-- Botão para fechar o painel -->
        <button class="btn error-outline" @click="closePanel">
          Close 
        </button>
        <h2>{{ title }}</h2>
      </div>
      <!-- Slot para o conteúdo do painel -->
      <slot name="content"></slot>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.panel{
  position: absolute;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: #3333;
  color: azure;
  overflow: auto;
  padding: 1em;

  &-wrap{
    position: absolute;
    top:0;
    bottom: 0;
    right: 0;
    width: 30 em;
    transform: translateX(100%);
    transition: 0.3s ease-out;
    
   &.visible{
    transform: translateX(0);
}
  } }
</style>

<script>
export default {
  methods: {
    closePanel() {
      // Emitindo evento para atualizar a visibilidade
      emit('update:visible', false);
    }
  }
};
</script>
