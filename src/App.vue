<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <div class="row col-md-6">
        <app-home :language="language" @languageWasChanged="language = $event"></app-home>
      </div>

      <div class="row col-md-6">
        <app-Projects :language="language" @languageWasChanged="language = $event"></app-Projects>
        <app-Team :language="language" @languageWasChanged="language = $event"></app-Team>
        <app-Contact :language="language" @languageWasChanged="language = $event"></app-Contact>
      </div>
    </div>


  </div>
</template>

<script>
import Home from './components/Home.vue'
import Projects from './components/Projects.vue'
import Team from './components/Team.vue'
import Contact from './components/Contact.vue'
export default {
  name: 'app',
  components: {
    appHome: Home,
    appProjects: Projects,
    appContact: Contact,
    appTeam: Team
  },
  data () {
    return {
      language: false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Fira Mono', monospace;
    text-align: left;
}
.container-fluid, .row {
  padding: inherit !important;
  margin: inherit !important;
}

/*for mobile device*/
@media screen and (max-width: 767px) {
  .home, .projects, .team {
    min-height: 100vh;
  }
  h3 {
    margin-top: 20px;
  }
  p {
    font-size: 12px;
    padding: 0 7px ;
  }
}

@media screen and (min-width: 768px) {
  .home {
    min-height: 100vh;
  }
  p {
    font-size: 12px;
    padding: 0 3% ;
  }
}

</style>
