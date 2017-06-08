<template lang="html">
  <div class="translaterout">

        <section class='hero is-primary is-bold'>
          <div class="hero-body">
            <div class="container">
              <h1 class='title'>{{text}}</h1>

            </div>
          </div>
        </section>

  </div>
</template>

<script>
export default {
  name:'translaterout',
  //props to access the property from parent
  props:['text']
}
</script>

<style lang="css">
</style>
