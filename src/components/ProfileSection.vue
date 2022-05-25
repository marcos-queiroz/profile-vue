<template>
  <MDBCard class="mt-5">
    <a v-mdb-ripple="{ color: 'light' }">
      <MDBCardImg :src="avatar" top alt="..." />
    </a>
    <MDBCardBody>
      <MDBCardTitle>
        <h1 class="h3">{{ fullName }}</h1>
      </MDBCardTitle>
      <MDBCardText>
        <p><strong>{{ formation }}</strong></p>
        <p><strong>Formas de contato</strong></p>
        <p>Email: {{ mail }}</p>
        <p>LinkedIn: <a :href="linkedInLink" target="_blank" rel="noopener noreferrer">{{ linkedIn }}</a></p>
        <p>GitHub: <a :href="gitHubLink" target="_blank" rel="noopener noreferrer">{{ gitHub }}</a></p>
        <p>Skype: <a :href="skypeLink" target="_blank" rel="noopener noreferrer">{{ skype }}</a></p>
      </MDBCardText>
    </MDBCardBody>
  </MDBCard>
</template>

<script>
  import { MDBCard, MDBCardBody, MDBCardTitle, MDBCardText, MDBCardImg, mdbRipple } from "mdb-vue-ui-kit";

  export default {
    name: "ProfileSection",
    components: {
      MDBCard,
      MDBCardBody,
      MDBCardTitle,
      MDBCardText,
      MDBCardImg
    },
    directives: {
      mdbRipple
    },
    props: {
      msg: String
    },
    data: function () {
      return {
        fullName: '',
        avatar: '',
        formation: '',
        mail: '',
        linkedIn: '',
        linkedInLink: '',
        gitHub: '',
        gitHubLink: '',
        skype: '',
        skypeLink: '',
      }
    },
    mounted() {
      this.fullName = document.getElementById('fullName').innerText
      this.formation = document.getElementById('formation').innerText
      this.avatar = document.getElementById('avatar').getAttribute('src')
      this.mail = document.getElementById('mail').innerText
      this.linkedIn = document.getElementById('linkedIn').innerText
      this.linkedInLink = document.getElementById('linkedIn').getAttribute('href')
      this.gitHub = document.getElementById('gitHub').innerText
      this.gitHubLink = document.getElementById('gitHub').getAttribute('href')
      this.skype = document.getElementById('skype').innerText
      this.skypeLink = document.getElementById('skype').getAttribute('href')
    },
  };
</script>
