<template>
    <div>
        <li class="list-group-item active">
            <h1>Chat Room</h1>
        </li>
        <ul class="list-group">
            <li class="list-group-item" v-for="text in chat.message">{{ text }}</li>
        </ul>
        <li class="list-group-item" style="padding: 0px;">
            <input type="text" class="form-control" placeholder="Enter Your Message" v-model="message" @keyup.enter="send" autofocus>
        </li>
    </div>
</template>

<style>
    .list-group {
        overflow-y: scroll;
        height: 400px;
    }
</style>

<script>
    export default {
        data () {
            return {
                message: "",
                chat: {
                    message: []
                }
            }
        },
        methods: {
            send () {
                if (this.message !== "") {
                    console.log(this.message)
                    this.chat.message.push(this.message)
                    this.message = ""
                }
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>