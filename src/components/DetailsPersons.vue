<template>
    <div class="wraper" v-if="personInformation.name !== undefined">
        <div class="element">
            <label for="name"><strong>Name:</strong></label>
            <span id="name"><i>{{ ` ${personInformation.name}` }}</i></span>
        </div>
        <div class="element">
            <label for="name"><strong>Phone:</strong> </label>
            <span id="name"><i>{{ ` ${personInformation.phone}` }}</i></span>
        </div>
        <div class="element">
            <label for="name"><strong>Email:</strong></label>
            <span id="name"><i>{{ ` ${personInformation.email}` }}</i></span>
        </div>
    </div>
    <div v-else>No information about person</div>
</template>

<script>
    export default {
        props: {
            personInformation: {
                type: Object,
                required: true
            } 
        },
        data() {
            return {
                personInfoFromLocalStorage: [],
            }
        },
    }
</script>

<style scoped>
.wraper {
    border: 1px solid #000;
}

.element {
    padding: 10px;
}

</style>