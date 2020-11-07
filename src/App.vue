<template>
    <h1>List of Friends</h1>
    <friend-contact></friend-contact>
</template>

<script>
export default {
    data() {
        return {
            friends: [
                { 
                    id: '01',
                    name: 'Manuel Lorenz',
                    phone: '01234 5678 991',
                    email: 'manuel@localhost.com' 
                },
                { 
                    id: '02',
                    name: 'Julie Jones',
                    phone: '09876 543 221',
                    email: 'julie@localhost.com' 
                }
            ]
        }
    }
}
</script>

<style lang="scss">
@use './App.scss';
</style>