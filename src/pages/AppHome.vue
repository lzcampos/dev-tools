
<script>
    import { reactive } from 'vue'
    export default {
      name: 'AppHome',
      setup() {
        const state = reactive({
          method: "POST",
          url: "",
          curl: "",
          body: ""
        })

        function changeMethod(e){
          state.method = e.target.value
        }

        function changeUrl(e){
          state.url = e.target.value
        }

        function changeBody(e){
          state.body = e.target.value
        }

        function generateUrl(){
          let curl = `curl -X${state.method}`
          if(state.body != "") curl += ` -d '${state.body}'`
          curl += ` '${state.url}'`

          state.curl = curl
        }

        return {
          state,
          generateUrl,
          changeMethod,
          changeUrl,
          changeBody
        }
      }
    }
</script>

<template>
  <div>

    <label for="Method">Method</label>
    <input type="text" name="method" id="method" v-bind:value="state.method" @change="changeMethod">

    <label for="Url">Url</label>
    <input type="text" name="url" id="url" v-bind:value="state.url" @change="changeUrl">

    <label for="Body">Body</label>
    <input type="text" name="body" id="body" v-bind:value="state.body" @change="changeBody">

    <input type="button" value="Generate curl" @click="generateUrl">

    <h2>CURL</h2>
    <p>{{state.curl}}</p>

  </div>
</template>


<style>

</style>