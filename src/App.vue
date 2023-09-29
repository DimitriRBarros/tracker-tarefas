<template>
  <main class="columns is-gapless is-multiline" :class="{'modo-escuro': modoEscuroAtivo}">
    <div class="column is-one-quarter">
      <BarraLAteral @aoTemaAlterado="trocarTema"/>
    </div>
    <div class="column is-three-quartes conteudo">
      <Notificacoes/>
      <router-view></router-view>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLAteral from './components/BarraLAteral.vue';
import Notificacoes from './components/Notificacoes.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLAteral,
    Notificacoes
  },
  data () {
    return {
      modoEscuroAtivo: false
    }
  },
  methods: {
    trocarTema (modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = modoEscuroAtivo
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}

main {
  --bg-primario: #fff;
  --texto-primario: #000;
}

main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}

.conteudo {
  background-color: var(--bg-primario);
}
</style>
