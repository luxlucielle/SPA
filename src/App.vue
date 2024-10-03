<template>
  <div id="app" class="container my-5 text-center">
    <h1 class="display-4">{{ name }}</h1>
    <h2 class="mt-4 text-muted">{{ title }}</h2>
    <p class="lead">{{ objective }}</p>

    <div class="row">
      <div class="col-md-6 mx-auto">
        <h2 class="mt-5">Education</h2>
        <div class="card mb-4">
          <div class="card-body">
            <strong>{{ degree }}</strong> - {{ university }} <br>
            Expected Graduation: {{ graduationDate }}
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-6 mx-auto">
        <h2 class="mt-5">Skills</h2>
        <button class="btn btn-primary" @click="showSkillsModal">View Skills</button>
      </div>
    </div>

    <!-- Skills Modal -->
    <div class="modal fade" id="skillsModal" tabindex="-1" role="dialog" aria-labelledby="skillsModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="skillsModalLabel">Skills</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close" @click="hideSkillsModal">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <ul class="list-group">
              <li v-for="skill in skills" :key="skill" class="list-group-item">{{ skill }}</li>
            </ul>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal" @click="hideSkillsModal">Close</button>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-6 mx-auto">
        <h2 class="mt-5">Projects</h2>
        <ul class="list-group">
          <li v-for="project in projects" :key="project.title" class="list-group-item">
            <strong>{{ project.title }}</strong>: {{ project.description }}
          </li>
        </ul>
      </div>
    </div>

    <footer class="mt-5">
      <p class="text-muted">&copy; {{ new Date().getFullYear() }} {{ name }}. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      name: 'Ryle P. Sundiam',  
      title: '3D Animator',
      objective: 'Driven by passion.',
      degree: 'Bachelor of Science in Information Technology',
      university: 'Holy Angel University', 
      graduationDate: 'April, 2026',  
      skills: ['Character Animation', 'Vehicle Animation', '3D Art'], 
      projects: [
        {
          title: 'Animation Portfolio',
          description: 'A website to showcase my works to potential directors.'
        }
      ]
    }
  },
  methods: {
    showSkillsModal() {
      $('#skillsModal').modal('show'); // Use jQuery to trigger the modal
    },
    hideSkillsModal() {
      $('#skillsModal').modal('hide'); // Use jQuery to hide the modal
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

h1, h2 {
  font-weight: normal;
}

footer {
  margin-top: 30px;
}
</style>
