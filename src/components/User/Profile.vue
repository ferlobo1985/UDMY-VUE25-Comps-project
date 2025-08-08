<template>
    <div class="user_profile">
        <h3>User information</h3>
        <ul>
            <li><span>Name:</span> {{ name }}</li>
            <li><span>Know as:</span> {{ alsoKnownAs }}</li>
            <li><span>Lastname:</span> {{ userLastname }}</li>
            <li><span>Age:</span> {{ userAge }}</li>
            <h3>Parents:</h3>
            <ul>
                <li v-for="(value,key,index) in userParents" :key="index">
                    <span>{{ key }}:</span> {{ value }}
                </li>
            </ul>
        </ul>
        <hr/>
        <button @click="emit('update-lastname','Michaelson')">Change from the child</button>
    </div>
</template>

<script setup>
    const emit = defineEmits(['update-lastname'])
    const props = defineProps({
        alsoKnownAs:String,
        userLastname:String,
        userAge: Number,
        userParents: Object
    })
    const name = 'Steve';


</script>

<style scoped>
    span {
        font-weight: 800;
    }
    .user_profile {
        border: 1px solid #2196F3;
        padding: 10px;
    }
</style>