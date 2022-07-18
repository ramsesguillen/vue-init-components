<template>
    <li>
        <h2>{{ friend.name }} {{ isFavorite ? '(Favorite)' : '' }}</h2>
        <button @click="toggleDetails">{{ detailAreVisible ? 'Hide' : 'Show Details' }}</button>
        <button @click="toggleIsFavorite">Toggle favorite</button>
        <ul v-if="detailAreVisible">
            <li><strong>Phone:</strong>{{ friend.phone }}</li>
            <li><strong>Email:</strong>{{ friend.email }}</li>
        </ul>
        <button @click="$emit('delete', friend.id)">Delete</button>
    </li>
</template>

/*  */
<script>
export default {
    // props: [ "friend" ],
    props: {
        friend: {
            type: Object,
            required: true,
            validator: function(value) {
                return value?.id ? true : false;
            }
        },
        isFavorite: {
            type: Boolean,
            required: false,
            default: false,
        }
    },
    emits: ['toggle-favorite', 'delete'],
    // emits: {
    //     'toggle-favorite': function(id) {
    //         return id ? true : false;
    //     }
    // },
    data() {
        return {
            detailAreVisible: false,
            // friendIsFavorite: this.isFavorite,
        }
    },
    methods: {
        toggleDetails() {
            this.detailAreVisible = !this.detailAreVisible
        },
        toggleIsFavorite() {
            // this.friendIsFavorite = !this.friendIsFavorite
            this.$emit('toggle-favorite', this.friend.id);
        },
        // deleteFriend() {

        // }
    },
}
</script>
