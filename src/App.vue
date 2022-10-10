<script setup lang="ts">
import AtributoInfo from './components/AtributoInfo.vue'
import { ref } from 'vue'

const forca = ref(10)
const destreza = ref(10)
const saude = ref(10)
const mente = ref(10)
const carisma = ref(10)
</script>

<template>
  <div
    bg="dark-800"
    flex="~ col"
    m="x-auto"
    justify="center"
    align="items-center"
    h="screen"
  >
    <div text="light-800" font="mono" m="b-10">
      <h1 text="4xl" font="bold">Ficha Base</h1>
      <p>
        Acrescente os pontos disponíveis na ficha.<br />
        O valor máximo dos atributos é 16 e o mínimo é 0.
      </p>
    </div>
    <table border="~  light-800 opacity-50">
      <thead>
        <tr text="xl uppercase light-800" font="mono bold ">
          <th p="4">atributos</th>
          <th p="4" border="x light-800 opacity-50">valor</th>
          <th p="4">bônus</th>
        </tr>
      </thead>
      <tbody>
        <AtributoInfo
          atributo="força"
          :count="forca"
          @plus="forca += 1"
          @minus="forca -= 1"
        />
        <AtributoInfo
          atributo="destreza"
          :count="destreza"
          @plus="destreza += 1"
          @minus="destreza -= 1"
        />
        <AtributoInfo
          atributo="saúde"
          :count="saude"
          @plus="saude += 1"
          @minus="saude -= 1"
        />
        <AtributoInfo
          atributo="mente"
          :count="mente"
          @plus="mente += 1"
          @minus="mente -= 1"
        />
        <AtributoInfo
          atributo="carisma"
          :count="carisma"
          @plus="carisma += 1"
          @minus="carisma -= 1"
        />
      </tbody>
    </table>

    <div flex="~ col" align="items-center" text="center light-800" p="6">
      <p font="bold mono" m="b-1">pontos disponíveis</p>
      <div
        text="xl"
        font="mono"
        border="~  light-800 opacity-50 rounded-md"
        w="20"
      >
        <span>{{ -forca - destreza - saude - mente - carisma + 58 }}</span>
      </div>
    </div>
  </div>
</template>
