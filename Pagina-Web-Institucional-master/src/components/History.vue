<template>
  <v-row class="d-flex justify-center margin-top-10">
    <div class="text-center">
      <h1 class="display-1 font-weight-bold mb-4 title-text">Nuestra Historia</h1>
    </div>
  </v-row>
  <v-row class="d-flex justify-center">
    <v-col cols="6">
      <v-timeline align="start" class="custom-timeline">
        <v-timeline-item
          v-for="(year, i) in years"
          :key="i"
          :dot-color="year.color"
          size="small"
        >
          <template v-slot:opposite>
            <div
              :class="`pt-1 headline font-weight-bold year-text text-${year.color}`"
              v-text="year.year"
            ></div>
          </template>
          <div class="timeline-content">
            <h2 :class="`mt-n1 headline font-weight-light mb-4 text-${year.color}`">
              {{ year.title }}
            </h2>
            <div class="content-text">
              {{ year.description }}
            </div>
          </div>
        </v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>

<script setup>
const years = [
  {
    color: 'cyan-lighten-2',
    year: '1960',
    title: 'Fundación',
    description: 'Inicio de nuestras operaciones con la visión de servir a la comunidad y crecer junto a ella.'
  },
  {
    color: 'cyan-lighten-1',
    year: '1970',
    title: 'Primera Expansión',
    description: 'Ampliación de nuestros servicios y cobertura para llegar a más personas necesitadas.'
  },
  {
    color: 'cyan',
    year: '1980',
    title: 'Consolidación',
    description: 'Establecimiento como líder en el sector y reconocimiento por nuestra labor social.'
  },
  {
    color: 'cyan-darken-1',
    year: '1990',
    title: 'Innovación',
    description: 'Implementación de nuevas tecnologías y métodos para mejorar nuestros servicios.'
  },
  {
    color: 'cyan-darken-2',
    year: '2000',
    title: 'Crecimiento Sostenible',
    description: 'Expansión nacional con compromiso ambiental y responsabilidad social corporativa.'
  },
]
</script>

<style scoped lang="scss">
.title-text {
  color: #1976D2;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
}

.custom-timeline {
  :deep(.v-timeline-item__body) {
    background: linear-gradient(135deg, #E3F2FD 0%, #F5FBFF 100%);
    border: 1px solid #B3E5FC;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 12px rgba(0, 150, 200, 0.1);
  }
  
  :deep(.v-timeline-divider__before),
  :deep(.v-timeline-divider__after) {
    background-color: #B3E5FC;
  }
  
  :deep(.v-timeline-item__dot) {
    box-shadow: 0 0 0 4px white, 0 0 0 8px currentColor;
  }
}

.year-text {
  color: #01579B !important;
  font-size: 1.5rem;
}

.timeline-content {
  h2 {
    color: #0288D1 !important;
    font-weight: 600 !important;
  }
}

.content-text {
  color: #455A64;
  line-height: 1.6;
  font-size: 1rem;
}

.margin-top-10 {
  margin-top: 40px;
}

// Efectos hover para las tarjetas de timeline
:deep(.v-timeline-item__body):hover {
  transform: translateY(-2px);
  transition: all 0.3s ease;
  box-shadow: 0 8px 20px rgba(0, 150, 200, 0.15) !important;
}

// Ajustes responsivos
@media (max-width: 960px) {
  :deep(.v-timeline-item__opposite) {
    display: none !important;
  }
  
  .v-col {
    cols: 12 !important;
  }
}
</style>