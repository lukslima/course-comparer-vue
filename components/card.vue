<template>

  <div class="container-course__card">

    <div class="container-course__card-course-name">
      <span>{{ courseName }}</span>
    </div>

    <div class="container-course__card-data">

      <div class="container-course__card-data-name">
        <span>{{ cardName }}</span>
      </div>

      <CardItem
        name="Tipos de formação"
        value="Bacharelado"
      />

      <CardItem
        name="Duração"
        value="8 semestres"
      />

      <CardItem
        name="Mensalidade"
        value="A partir de:"
      />

      <CardItem
        name="Área de conhecimento"
        value="Gestão e Negócios"
      />

      <CardItem
        name="Estágio obrigatório?"
        value="Não especificado"
      />

      <CardItem
        name="Bolsas de estudo"
        value="Até 83% de desconto"
      />

    </div>
  </div>
</template>

<style>
.container-course__card {
  width: 50%;
}

.container-course__card-course-name {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  width: 525px;
}

.container-course__card-data {
  border: 1px solid #cecece;
  border-radius: 5px;
  padding: 24px;
  width: 525px;
}

.container-course__card-data-name {
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 24px;
  text-align: center;
}
</style>

<script>
import CardItem from '~/components/card-item';

export default {
  name: 'card',
  components: {
    CardItem,
  },

  props: {
    courseName: {
      type: String,
      required: true,
    },
    cardName: {
      type: String,
      required: true,
    },
  },
};
</script>
