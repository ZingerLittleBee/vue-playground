<script lang="ts">
import { defineComponent, h, ref } from 'vue'
export default defineComponent({
  name: 'Test',
  setup() {
    const inputValue = ref('')
    const todoItemValue = ref<any[]>([])
    const input = h('input', {
      value: inputValue.value,
      onChange: (e: any) => {
        inputValue.value = e.target.value
        todoItemValue.value.push(e.target.value)
        inputValue.value = ''
      }
    }, inputValue.value)
    const todoList = h('div', {}, todoItemValue.value.map(v => {
      return h('li', {}, v)
    }))
    return () => h('div', {}, ['setup-h:', input, todoList])
  }
})
</script>
