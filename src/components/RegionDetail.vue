  <template lang="html">
    <div v-if="region">
      <h2>{{region.shortname}}</h2>
      <p>{{region.intensity.forecast}}</p>
      <ul v-for="(title, index) in region.generationmix[0]" :object='object' :key='index'>
        <li>{{object.fuel}}{{object.perc}}</li>


      </ul>

    </div>

</template>

<script>
export default {
  name: 'region-detail',
  props: ['region']
}
</script>

<style lang="css" scoped>
</style>
