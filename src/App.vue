<template>
    <div>
        <app-header/>
        <div class="container">
            <UserProfile
                :alsoKnownAs="data.name"
                :userLastname="data.lastname"
                :userAge="data.age"
                :userParents="data.parents"
                @update-lastname="data.lastname = $event"
                @say-hello="alerthello"
                :updateAge="updateAge"
            />
            <button @click="updateName">Update name</button>
        </div>
    </div>
</template>

<script setup>
    import UserProfile from '@/components/User/Profile.vue';
    import { reactive } from 'vue';

    const data = reactive({
        name:'Rocket',
        lastname:'Joness',
        age:28,
        parents:{
            father:'Mario',
            mother:'Martha'
        }
    })

    const updateName = () => {
        data.name = "Golden child"
    }
    const updateAge = (value) => {
        data.age = value
    }

    const alerthello = () => {
        alert('Hello !!')
    }

</script>

<style>
    body {
        padding:0;
        margin:0;
        font-family: 'Roboto',sans-serif;
    }
    .container {
        min-height:84vh;
        box-sizing: border-box;
        padding: 20px;
    }
</style>