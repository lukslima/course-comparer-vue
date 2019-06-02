<template>
  <div>
      <b-row class="my-1">
        <b-col sm="4">
          <label for="asdf" >Carreira {{ courseNumber }}</label>
        </b-col>
        <b-col sm="8">
          <vue-simple-suggest
            v-model="chosen"
            :list="simpleSuggestionList"
            :filter-by-query="true"
            @select="onSuggestSelect">
          </vue-simple-suggest>
        </b-col>
      </b-row>

      <Card 
        courseName="Teste"
        cardName="Resumo do curso"
      />  

      <div v-for="section in sections" :key="section.id" >
        <b-button block
          :class="section.showCollapse ? 'collapsed' : null"
          :aria-expanded="section.showCollapse ? 'true' : 'false'"
          aria-controls="collapse-4"
          @click="section.showCollapse = !section.showCollapse"
        >
          {{ section.descricao }}]
        </b-button>
        
        <b-collapse id="collapse-4" v-model="section.showCollapse" class="mt-2">
          <b-card>I should start open!</b-card>
        </b-collapse>
        <br>
      </div>
  </div>
</template>

<script>
import Card from '~/components/card';
import VueSimpleSuggest from 'vue-simple-suggest'
import 'vue-simple-suggest/dist/styles.css'

export default {
  name: 'CourseSearch',
  components: {
    Card,
    VueSimpleSuggest,
  },
  data() {
    return {
      chosen: '',
      sections: [
        {id: 1, descricao: 'Sobre', showCollapse: true},
        {id: 2, descricao: 'O que faz', showCollapse: true},
        {id: 3, descricao: 'Concorrecia no curso', showCollapse: true},
        {id: 4, descricao: 'Como é o curso', showCollapse: true},
        {id: 5, descricao: 'Qual a grade curricular', showCollapse: true},
        {id: 6, descricao: 'Onde o profissional trabalha', showCollapse: true},
        {id: 7, descricao: 'Quanto ganha', showCollapse: true},
      ],
    }
  },
  props: {
    courseNumber: {
      type: Number,
    }
  },
  methods: {
    simpleSuggestionList() {
      return [
        'Vue.js',
        'React.js',
        'Angular.js'
      ]
    },
    onSuggestSelect(value) {
      console.log(`Valor escolhido ${value}`);
    }
  },
  async asyncData ({ params }) {
    // let { data } = await axios.get(`https://my-api/posts/${params.id}`)
    // return { title: data.title }
    return {"name": "Direito", "description": "<div class=\"canonical-course-about__text-wrapper\"><h2 class=\"heading heading--1\">Sobre o curso de Direito</h2><p class=\"paragraph paragraph--lg\">O curso de <strong>Direito</strong> prepara profissionais para cuidar da aplica\u00e7\u00e3o das leis e normas jur\u00eddicas vigentes em um pa\u00eds ou regi\u00e3o. Durante as aulas, o estudante adquire conhecimento te\u00f3rico e t\u00e9cnico sobre Legisla\u00e7\u00e3o Brasileira e Legisla\u00e7\u00e3o Internacional, al\u00e9m de vis\u00e3o cr\u00edtica e consci\u00eancia pol\u00edtica e social.</p>\n<p class=\"paragraph paragraph--lg\"> Ao final do curso, o aluno pode atuar como advogado, sendo necess\u00e1rio passar no exame da Ordem dos Advogados do Brasil (OAB), ou seguir carreira jur\u00eddica. O curso de <strong>Direito</strong> forma bachar\u00e9is, com \u00eanfases em diversas \u00e1reas de atua\u00e7\u00e3o.</p>\n<p class=\"paragraph paragraph--lg\"> No mercado de trabalho, o profissional de<strong> Direito</strong> pode da aulas, atuar profissionalmente nos setores p\u00fablico e privado ou seguir carreira diplom\u00e1tica. O candidato a juiz, promotor ou delegado de pol\u00edcia deve passar em concurso p\u00fablico. Para se tornar juiz \u00e9 necess\u00e1rio, ainda, ter dois anos de inscri\u00e7\u00e3o na OAB como advogado.</p>\n</div>"}
  }
}
</script>

<style>
</style>
