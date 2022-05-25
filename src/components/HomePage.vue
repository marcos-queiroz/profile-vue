<template>
  <MDBContainer>
    <div class="row">
      <div class="col-md-4">
        <ProfileSection/>
      </div>
      <div class="col-md-8">
        <WorksSection/>
      </div>
      <div class="col-md-12">
        <SkillsSection/>
      </div>
    </div>
  </MDBContainer>
</template>

<script>
  import { MDBContainer } from "mdb-vue-ui-kit";
  import ProfileSection from './ProfileSection'
  import WorksSection from './WorksSection'
  import SkillsSection from './SkillsSection'
  export default {
    name: "HomePage",
    components: {
      MDBContainer,
      ProfileSection,
      WorksSection,
      SkillsSection,
    },
    props: {
      msg: String
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
