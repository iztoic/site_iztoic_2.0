<template>
  <section id="section-about" class="section-about">
    <div class="container">
      <div class="row">
        <SubSectionContentColumn />
        <SubSectionContentImage />
      </div>
    </div>
  </section>
</template>

<script>
import SubSectionContentColumn from './section_about_content_column.vue'
import SubSectionContentImage from './section_about_image_column.vue'
export default {
  name: "SectionAbout",
  data() {
    return {
    };
  },
  components: {
    SubSectionContentColumn,
    SubSectionContentImage,
  },
  computed: {
  },
  mounted() {
  },
  methods: {
  },
};
</script>
<style scoped>

.row{
  display: flex;
  justify-content: space-evenly;
}
@media (max-width: 767px) {

}

@media (max-width: 575px) {

}
</style>