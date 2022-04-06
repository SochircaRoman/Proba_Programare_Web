<template>
    <div class="wraper" v-if="personInformation.name !== undefined">
        <div class="element">
            <label for="name"><strong>Name:</strong></label>
            <span id="name"><i>{{ ` ${personInformation.name}` }}</i></span>
        </div>
        <div class="element">
            <label for="phone"><strong>Phone:</strong> </label>
            <span id="phone"><i>{{ ` ${personInformation.phone}` }}</i></span>
        </div>
        <div class="element">
            <label for="email"><strong>Email:</strong></label>
            <span id="email"><i>{{ ` ${personInformation.email}` }}</i></span>
        </div>
    </div>
    <div v-else-if="this.getFromLocalStorage()">
        <div class="wraper">
            <div class="element">
                <label for="name"><strong>Name:</strong></label>
                <span id="name"><i>{{ ` ${personInfoFromLocalStorage.name}` }}</i></span>
            </div>
            <div class="element">
                <label for="phone"><strong>Phone:</strong> </label>
                <span id="phone"><i>{{ ` ${personInfoFromLocalStorage.phone}` }}</i></span>
            </div>
            <div class="element">
                <label for="email"><strong>Email:</strong></label>
                <span id="email"><i>{{ ` ${personInfoFromLocalStorage.email}` }}</i></span>
            </div>
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
                personInfoFromLocalStorage: {},
            }
        },
        methods: {
            getFromLocalStorage() {
                this.personInfoFromLocalStorage = JSON.parse(localStorage.getItem("personInfo"));
                if(this.personInfoFromLocalStorage.length != 0) {
                    return true;
                } else {
                    return false;
                }
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