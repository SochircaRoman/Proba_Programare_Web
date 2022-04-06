<script>
import ListPersons from './components/ListPersons.vue';
import DetailsPersons from './components/DetailsPersons.vue';

export default {
    components: { ListPersons, DetailsPersons },
    data() {
        return {
            personInformation: {},
        }
    },
    methods: {
        emitPersonInformation(person) {
            this.personInformation["name"] = person.name;
            this.personInformation["phone"] = person.phone;
            this.personInformation["email"] = person.email;
        }
    },


}

</script>

<template>

    <div class="app">
        <list-persons @emitPersonInformation="emitPersonInformation"></list-persons>
        <details-persons :personInformation="personInformation"></details-persons>
    </div>


  
</template>

<style scoped>

.app{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

</style>
