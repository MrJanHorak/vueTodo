<template>
  <div
    class="listItem  "
    v-on:click="$event.target.classList.toggle('isComplete')"
    :key="task.id"
    v-for="task in list"
  >

    <h2><span v-if="!isComplete">&ensp;</span><span v-if="isComplete">&#x2713;</span>{{ task.item }}</h2>

  </div>
</template>

<script>

export default {
  name: 'ListItem',
  props: ['list'],
  data:()=>({
    isComplete: false
  })
}
</script>

<style>
  h2 {
    margin-left: 48px;
  }

.listItem {
  color: gray;
  border: solid 2px gray;
  border-radius: 15px;
  width: 60vw;
  text-align: left;
  margin: 12px;
}

.isComplete {
  color: green;
  text-decoration: line-through;
}

/* .taskRow {
  display: flex;
  flex-direction: row;
} */

</style>
