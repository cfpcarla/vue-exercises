<template>
  <div> 
  <h1> Minha lista de tarefas</h1>
<button @click="() => showList = !showList"> Ver a Lista </button>
<br>
<input type="text" v-focus>
<ul v-if="showList">
<li v-for="(task, index) in tasks"
:key="`${task}-${index}`"
>
{{ task.name }}

</li>
</ul>
<p v-else> Lista de tarefas escondidas </p>
  </div>
</template>

<script>
const focus = {
  inserted: (el) => {
    el.focus()
  }
}
export default {
  directives: {
    focus
  },
    data: () => ({
      showList:false,
        tasks: [
            {name:'fazer o curso', isDone: false}
        ]
    })
}                                
</script>