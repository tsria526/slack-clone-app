<template>
 <div class="chat-container">
   <div class="thumbnail-container">
     <img v-bind:src="message.user.thumbnail" />
   </div>
   <div class="message-container">
     <div class="user-name">{{ displayName }}</div>
     <div class="message">{{ message.text }}</div>
   </div>
 </div>
</template>

<script>
export default {
    data() {
        return {
            message: {
                text: '今日も良い天気ですね',
                user: {
                    thumbnail: require('~/static/man.jpg'),
                    name: 'note'
                }
            }
        }
    },
    computed: {
        displayName() {
            return "@" + this.message.user.name
        }
    }
}
</script>

<style scoped>
    .chat-container {
    display: flex;
    padding: 8px;
    }

    .thumbnail-container {
    margin-right: 16px;
    }

    .thumbnail-container img {
    width: 50px;
    height: 50px;
    border-radius: 10px;
    object-fit: cover;
    }

    .user-name {
    font-weight: bold;
    }
</style>