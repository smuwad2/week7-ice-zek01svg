<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter']
            }
            
        },
        methods: {
            deleteItem (index) {
                this.items.splice(index, 1)
            },
            addItem (item) {
                this.items.push(item)
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul>
        <li v-for="(item, index) in items" >
            {{ item }} <button @click="deleteItem(index)">Delete!</button>
        </li>
     </ul>

     <!-- this part is for the text input and the button -->
    <input type="text" v-model="newItem">

    </input>

    <button @click="addItem(newItem)">
        Add!
    </button>
   
</template>
