
<template>
  <MDBCard class="mt-5 mb-6">
    <MDBCardBody>
      <MDBCardTitle>Skills</MDBCardTitle> 
      <template v-for="(skill, key) in skills" :key="key">
        <span class="h5">
          <MDBBadge color="primary" pill >{{ skill }}</MDBBadge>
        </span>
      </template>
    </MDBCardBody>
  </MDBCard>
</template>

<script>
  import { MDBCard, MDBCardTitle, MDBCardBody, MDBBadge } from "mdb-vue-ui-kit";

    export default {
      name: "WorksSection",
      components: {
        MDBBadge,
        MDBCard,
        MDBCardTitle,
        MDBCardBody,
      },
      data: function () {
        return {
          skills: []
        }
      },
      mounted() {
        document.getElementById('skills').getElementsByTagName('li').forEach((value) => {
          this.skills.push(value.innerText)
        })
      },
    };
</script>
