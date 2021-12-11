<template>
  <div class="container">
     <div class="row">
          <!-- Image with text -->
          <div class="col">
            <Test :source="'sky.jpg'" :message="'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.'" :title="'Beauty'" :desc="'Image of sky'"/>
            <Test :source="'sky.jpg'" :message="'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.'" :title="'Beauty'" :desc="'Image of sky'"/>
          </div>
      </div>
  </div>
</template>

<script>

export default {
  layout: 'Test',
  paragraph: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.'
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

@import "../scss/_base.normalize.scss";
@import "../scss/_components.content.scss";
@import "../scss/_settings.responsive.scss";
@import "../scss/_settings.variables.scss";
@import "../scss/style.scss";


</style>
