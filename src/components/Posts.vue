<template>
    <div class="container">
        <table class="table mt-4">
            <thead>
                <tr>
                    <th scope="col">User Id</th>
                    <th scope="col">Id</th>
                    <th scope="col">Title</th>
                    <th scope="col">Body</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="post in posts" :key="post.id">
                    <th scope="row">{{post.userId}}</th>
                    <td>{{post.id}}</td>
                    <td>{{post.title}}</td>
                    <td>{{post.body}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: "PostsExemple",
    data() {
        return {
            posts: [
                { id: 1, title: "Post 1", body: "Post Body 1" },
                { id: 2, title: "Post 2", body: "Post Body 2" },
                { id: 3, title: "Post 3", body: "Post Body 3" },
                { id: 4, title: "Post 4", body: "Post Body 4" }
            ]
        };
    },
    created() {
        axios.get('https://jsonplaceholder.typicode.com/posts').then(posts => {
          this.posts = posts.data;
        });
    }
};
</script>

<style>
</style>
