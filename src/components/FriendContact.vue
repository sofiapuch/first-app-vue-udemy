<template>
    <li class="friendContact">
        <h2 class="friendContact__title">
            {{ friend.name }}{{friend.isFavourite ? ' - Fav' : ''}}
        </h2>
        <button 
            class="friendContact__button" 
            @click="toggleDetails" >
            {{ detailsButtonLabel }}
        </button>
        <button 
            class="friendContact__button"
            @click="toggleFavourite" >
            Toggle Favourite
        </button>
        <ul v-if="detailsAreVisible">
            <li><strong>Phone:</strong> {{ friend.phone }}</li>
            <li><strong>Email:</strong> {{ friend.email }}</li>
        </ul>
    </li>
</template>

<script>
export default {
    props: {
        friend: Object
    },
    emits: ['toggle-favourite'],
    data() {
        return {
            detailsAreVisible: false
        }
    },
    computed: {
        detailsButtonLabel() {
            return this.detailsAreVisible ? 'Hide details' : 'Show details';
        }
    },
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible;
        },
        toggleFavourite() {
            this.$emit('toggle-favourite', this.friend.id);
        }
    }
}
</script>

<style lang="scss">
@use './FriendContact.module.scss';
</style>