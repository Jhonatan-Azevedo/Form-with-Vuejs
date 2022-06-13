<template>
  <div>
    <i
      v-for="estrela in estrelas"
      :key="estrela.id"
      :class="estrela.estilo"
      @Click.prevent="marcarAvaliacao(estrela.id)"
    ></i>
  </div>
</template>

<script>
export default {
  name: "InputEstrelas",

  props: { numeroEstrelas: Number },

  data() {
    return {
      estrelas: [],
      avaliacao: 0,
    };
  },

  created() {
    this.iniciarEstrelas();
  },

  methods: {
    iniciarEstrelas() {
      this.estrelas = [];
      for (let i = 0; i < this.numeroEstrelas; i++) {
        this.estrelas.push({ id: i, estilo: "bi bi-star estrela" });
      }
    },

    marcarAvaliacao(params) {
      this.iniciarEstrelas();

      this.avaliacao = params + 1;
      for (let i = 0; i < this.avaliacao; i++) {
        this.estrelas[i].estilo = "bi bi-star-fill estrela preenchida";
      }

      // this.$emit("avaliar", this.avaliacao);
      this.$emit("update:avaliar", this.avaliacao);
    },
  },
};
</script>

<style scoped>
.estrela {
  font-size: 1.5rem;
  color: #999;
  margin-inline: 1px;
  cursor: pointer;
}

.preenchida {
  color: #fc0;
}
</style>