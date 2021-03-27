<script lang="tsx">
import {defineComponent, ref} from 'vue'
export default defineComponent({
    name: 'TodoListJsx',
    setup() {
      const inputValue = ref('')
      const todoItemValue = ref<any[]>([])
      const handlerInputChange = (e: any) => {
        inputValue.value = e.target.value
        todoItemValue.value.push(e.target.value)
        inputValue.value = ''
      }
      const handlerItemClick = (index: number) => {
        delete todoItemValue.value[index]
      }
        return () => (
            <div>
              <label>
                TSX:
                <input value={inputValue.value} onChange={handlerInputChange} />
              </label>
              <div>{ todoItemValue.value.map((v, index) => {
                return <li onClick={() => handlerItemClick(index)}>{v}</li>
              }) }</div>
            </div>
        )
    }
})
</script>
