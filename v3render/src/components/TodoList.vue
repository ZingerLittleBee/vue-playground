<script lang="ts">
import { defineComponent, h, ref } from 'vue'
export default defineComponent({
    name: 'TodoList',
    setup() {
        const inputValue = ref('')
        const todoItemValue = ref<any[]>([])
        return {
            inputValue,
            todoItemValue
        }
    },
    render() {
        let { inputValue, todoItemValue } = this
        const input = h('input', {
            value: inputValue,
            onChange: (e: any) => {
                inputValue = e.target.value
                todoItemValue.push(e.target.value)
            }
        })
        const deleteElement = (value: any) => {
            let number = todoItemValue.findIndex(e => e === value)
            delete todoItemValue[number]
        }
        const todoItem = todoItemValue.map(item => {
            return h(
                'li',
                {
                    onClick: () => {
                        deleteElement(item)
                    }
                },
                item
            )
        })
        const todoList = h('div', {}, todoItem)
        return h('div', {}, [input, todoList])
    }
})
</script>
