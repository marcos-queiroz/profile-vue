<template>
  <MDBCard class="mt-5">
    <MDBCardBody>
      <MDBCardTitle>
        Experiência profissional
      </MDBCardTitle>
      <MDBAccordion flush>
        <MDBAccordionItem
          v-for="(work, key) in works"
          :key="key"
          v-bind:headerTitle="work.company"
          v-bind:collapseId="'collape_' + key"
        >
          <strong>Período</strong>: {{ work.startWork }} a {{ work.endWork }} <br>
          <strong>Setor</strong>: {{ work.sector }} <br>
          <strong>Cargo</strong>: {{ work.office }}  <br>
          <strong>Atividades desenvolvidas</strong>: {{ work.activities }} <br>
          <strong>Skills</strong>: <br>
          <template v-for="(skill, key) in work.skills" :key="key">
            <MDBBadge color="primary" pill >{{ skill }}</MDBBadge>
          </template>
        </MDBAccordionItem>
      </MDBAccordion>
    </MDBCardBody>
  </MDBCard>
</template>

<script>
  import { MDBCard, MDBCardTitle, MDBCardBody, MDBAccordion, MDBAccordionItem, MDBBadge } from "mdb-vue-ui-kit";

  export default {
    name: "WorksSection",
    components: {
      MDBCard,
      MDBCardTitle,
      MDBCardBody,
      MDBAccordion,
      MDBAccordionItem,
      MDBBadge,
    },
    data: function () {
      return {
        works: []
      }
    },
    mounted() {
      const ul = document.getElementById('works')
      const li = ul.getElementsByTagName('li')

      li.forEach(value => {
        const span = value.getElementsByTagName('span')

        if(span.length > 0){
          let work = {}

          span.forEach((value) => {

            const key = value.getAttribute('class')
            const val = value.innerText

            if(key == 'skills'){
              work[key] = val.split(',');
            } else {
              work[key] = val;
            }


          })
          
          this.works.push(work) 
        }
        
      });
    },
  };
</script>
