<template>
  <div class="s-content">
      <h2 class="s-content-section-title" >Busque por categoria:</h2>
    <div class="s-content-section">
      <ItemCategComp
        v-for="item in categories"
        :key="item.src"
        :imgSrc="item.src"
        :textSrc="item.text"
      ></ItemCategComp>
    </div>
    <h2 class="s-content-section-title" >Produtos que estão bombando!</h2>
    <div class="s-content-section">
      <CardItemComp
        v-for="prod in products"
        :key="prod.src"
        :imgSrc="prod.src"
        :textSrc="prod.text"
        :description="prod.description"
        :prize="prod.prize"
      >
    </CardItemComp>
    </div>
    <h2 class="title" >Conheça todas nossas facilidades</h2>
    <div class="s-content-section bg-facilities">
    <FacilityComp
        v-for="icon in icons"
        :key="icon.src"
        :imgSrc="icon.src"
        :textSrc="icon.text"
        :description="icon.description"
      ></FacilityComp>
    </div>
    <div class="s-content-section">
      <div class="s-content-block">
        <blockquote>
          Quer receber nossas novidades, promoções exclusivas e 10% OFF na
          primeira compra? Cadastre-se!
        </blockquote>
        <div class="s-input-block">
            <input type="text" placeholder="Digite seu email" >
            <button>Enviar</button>
        </div>
      </div>
    </div>
  </div>


  <footer>
   {{year}} | Desenvolvido por Natalie
  </footer>
</template>
<script>
import ItemCategComp from '@/components/ItemCategComp.vue'
import CardItemComp from '@/components/CardItemComp.vue'
import FacilityComp from '@/components/FacilityComp.vue'
import { ref } from 'vue'
import { listCategories, listCards, listIcons } from '@/assets/const/const.js'

export default {
  data() {
    return {
      categories: ref([]),
      products: ref([]),
      icons: ref([]),
      year: ref(""),
    }
  },
  created() {
    this.categories = listCategories;
    this.products = listCards;
    this.icons = listIcons;

    const now = new Date;
    this.year = now.getFullYear()
  },

  methods: {
  },
  components: { ItemCategComp, CardItemComp, FacilityComp }
}
</script>
