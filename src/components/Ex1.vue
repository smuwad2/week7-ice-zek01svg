<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data() {
            return {
                x:0,
                y:0,
                selectedOp: '+',
                operators: ['+','-','*','/','%']
            }
        },
        computed: {
            result() {
                const x = this.x
                const y = this.y
                const selectedOp = this.selectedOp

                var result

                if (selectedOp == '+') {
                    result = x + y
                }
                else if (selectedOp == '-') {
                    result = x - y
                }
                else if (selectedOp == '*') {
                    result = x * y
                }
                else if (selectedOp == '/') {
                    result = x / y
                }
                else if (selectedOp == '%') {
                    result = x % y
                }

                return result
            }
        }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
