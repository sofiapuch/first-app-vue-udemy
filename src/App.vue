<template>
    <h1>List of Friends</h1>
    <friend-contact 
        v-for="friend in friends" 
        :key="friend.id"
        :friend="friend"
        @toggle-favourite="toggleFavouriteStatus"
    ></friend-contact>
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
                    email: 'manuel@localhost.com',
                    isFavourite: true
                },
                { 
                    id: '02',
                    name: 'Julie Jones',
                    phone: '09876 543 221',
                    email: 'julie@localhost.com',
                    isFavourite: false
                }
            ]
        }
    },
    methods: {
        toggleFavouriteStatus(friendId) {
            const friendFound = this.friends.find( friend => friend.id === friendId);
            friendFound.isFavourite = !friendFound.isFavourite;
        }
    }
}
</script>

<style lang="scss">
@use './App.scss';
</style>