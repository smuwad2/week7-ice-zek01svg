<script>
    export default { 

       data() {
            return {
                moods: ['Happy', 'Angry', 'Sad'],
                subject: '',
                entry: ''
            }
       },
       methods: {
            submitPost () {

                const url = 'http://localhost:3000/addPost'
                var params = {
                    // the post endpoint is expecting a json object with three properties: subject, entry, and mood
                    "subject": this.subject,
                    "entry": this.entry,
                    "mood": this.mood
                }
                axios.post(url, params)
                .then(response => { console.log(response.data) })
                .catch(error => { console.log(error.message) })
            }
       }
    }
    
</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
        <select>
            <option v-for="mood in moods">
                {{ mood }}
            </option>
        </select>

        <br>

        <br>
        <button @click="submitPost()">Submit New Post</button>

        <hr> Click  <a><router-link to="/ViewPosts/">here</router-link></a>  to return to Main Page
       
    </div>
</template>

