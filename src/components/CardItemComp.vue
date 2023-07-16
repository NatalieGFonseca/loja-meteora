<template>
  <div class="cards">
    <div class="information">
      <img :src="imgSrc" :alt="textSrc" />
      <div class="block">
        <h3 class="label">{{ textSrc }}</h3>
        <p class="description">{{ description }}</p>
        <p class="prize">{{ prize }}</p>
        <button @click="showModal = true">Ver mais</button>
      </div>
    </div>
  </div>
  <transition name="modal" v-if="showModal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">
          <div class="modal-header">
            <slot name="header"> Confira detalhes sobre o produto </slot>
            <button class="modal-default-button" @click="showModal = false">X</button>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="col">
                <img :src="imgSrc" :alt="textSrc" />
              </div>
              <div class="col">
                <h3 class="label">{{ textSrc }}</h3>
                <p class="description  border">{{ description }}</p>
                <p class="prize">{{ prize }}</p>
                <p class="about">Vendido e entregue por Meteora</p>
                <div class="options">
                  <p>Cores:</p>
                  <ul>
                    <li><input type="radio"><label>Azul Claro</label></li>
                    <li><input type="radio"><label>Preto </label></li>
                    <li><input type="radio"><label>Branco</label></li>
                  </ul>
                </div>
                <div class="options">
                  <p>Tamanho:</p>
                  <ul>
                    <li><input type="radio"><label>PP</label></li>
                    <li><input type="radio"><label>M </label></li>
                    <li><input type="radio"><label>GG</label></li>
                  </ul>
                </div>
                <button >Adicionar à sacola</button>
              </div>
            </slot>

          </div>
        </div>
      </div>
    </div>
  </transition>
</template>
<script setup>
defineProps({
  imgSrc: {
    type: String,
    required: true
  },
  textSrc: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  prize: {
    type: String,
    required: true
  },
  showModal: {
    type: Boolean,
    required: true
  }
})
</script>
<style>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 700px;
  margin: 0px auto;
  padding: 20px 20px 10px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header {
  padding: 20px;
  color: var(--primary-color);
  background-color: var(--primary-pallete-1);
}

.modal-body {
  margin: 20px 0 20px 0;
  display: flex;
}

.modal-body .col {
  flex-direction: column;
  margin-right: 10px;
}

.border {
  border-bottom: var(--primary-pallete-1) solid 3px;
  padding: .2rem;
}

.col .prize{
  font-weight: bold;
  padding: 10px 0px 10px 0px;
  font-size: 20px;
}

.col .about{
  color: var(--primary-pallete-2);
  border-bottom: var(--primary-pallete-2) solid 2px;
  padding: .2rem;
  margin-bottom: 10px;
}

.col button{
  background-color: var(--primary-pallete-4);
  color: var(--primary-pallete-2);
  padding: 10px;
  border-color: var(--primary-pallete-4);
  justify-content: center;
  margin-top: 20px;
}

.modal-default-button {
  float: right;
  background-color: var(--primary-pallete-1);
  color: var(--primary-pallete-3);
}

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}

.options {
  text-align: left;
}

.options p{
  font-weight: bold;
  margin-top: 10px;
}

.options ul{
  text-decoration: none;
  list-style-type: none;
  display: flex;
}

.options ul li{
  flex-direction: row;
  padding-right: 15px;
  word-wrap: break-word;
}

.options ul li input{
  margin-right: 1.1px;
}


</style>
