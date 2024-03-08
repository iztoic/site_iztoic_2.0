<template>
  <div>
    <section id="section-team">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h3 class="section-subheading">Conheça nossa equipe</h3>
          </div>
        </div>
        
          <SubSectionInfoCards />
      </div>
    </section>
  </div>
</template>

<script>
import SubSectionInfoCards from './section_team_infocards.vue';
export default {
  name: "SectionTeam",
  
  components: {
    SubSectionInfoCards,
  },
  methods: {
    
  },
};
</script>

<style scoped>
@import url('./src/assets/style/styles.css');

h3 { 
  font-size: var(--all_text_size_h3);
  color: var(--primary_gold_color);
  text-shadow: var(--all_page_text_shadow);
}

  .container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
  flex-direction: column;
}

@media (max-width: 768px) {

  h3 { 
  font-size: calc(var(--all_text_size_h3)/1.2);
}

}

@media (max-width: 575px) {
h3 { 
  font-size: calc(var(--all_text_size_h3)/2.1);
}

}
</style>
