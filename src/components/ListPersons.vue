<template>
    <div class="wraper">
        <div
            v-for="(person, index) in personsArr"
            :key="index"
            class="element"
            @click="personInformation(person)"
        ><strong>{{ person.name }}</strong></div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            personsArr: [
                {name: "Sochirca Roman", phone: "068465958", email: "romansochirca@gmail.com"},
                {name: "Mihai Eminescu", phone: "069785643", email: "mihaieminescu@gmail.com"},
                {name: "Ion Creanga", phone: "069896056", email: "ioncreanga@gmail.com"},
                {name: "Andrei Ciobanu", phone: "069666777", email: "andreiciobanu@gmail.com"},
            ],
        }
    },
    methods: {
        personInformation(person) {
            this.$emit("emitPersonInformation", person);
            this.saveToLocalStorage(person);
        },
        saveToLocalStorage (object) {
            localStorage.setItem("personInfo", JSON.stringify(object));
        }
        
}
}
</script>

<style scoped>

.wraper{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items:flex-start;
    margin-top: 50px;
    margin-right: 50px;
}

.element {
    border: 1px solid #000;
    padding: 15px;
    width: 170px;
    cursor: pointer;
}

.element:hover {
  border: 3px solid aquamarine;
}


</style>