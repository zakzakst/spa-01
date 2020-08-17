<template>
  <div>
    <h1 class="title">タスク一覧</h1>
    <div class="mb-4">
      <button class="button is-primary" @click="createTask">
        <span class="icon">
          <fa :icon="['fas', 'plus']" />
        </span>
        <span>新規タスク登録</span>
      </button>
    </div>
    <div>
      <div class="panel">
        <p class="panel-heading">今日</p>
        <div v-for="task in todayTaskItems" :key="task.id" class="panel-block">
          <div class="task__item columns">
            <div class="column is-half">{{ task.text }}</div>
            <div class="column is-one-quarter">
              <span class="tag is-dark">{{ task.status }}</span>
            </div>
            <div class="column is-one-quarter">
              <div class="buttons are-small">
                <button class="button is-primary" @click="updateTask(task.id)">編集</button>
                <button class="button is-danger" @click="deleteTask(task.id)">削除</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="panel">
        <p class="panel-heading">近日</p>
        <div v-for="task in soonTaskItems" :key="task.id" class="panel-block">
          <div class="task__item columns">
            <div class="column is-half">{{ task.text }}</div>
            <div class="column is-one-quarter">
              <span class="tag is-dark">{{ task.status }}</span>
            </div>
            <div class="column is-one-quarter">
              <div class="buttons are-small">
                <button class="button is-primary" @click="updateTask(task.id)">編集</button>
                <button class="button is-danger" @click="deleteTask(task.id)">削除</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="panel">
        <p class="panel-heading">後日</p>
        <div v-for="task in laterTaskItems" :key="task.id" class="panel-block">
          <div class="task__item columns">
            <div class="column is-half">{{ task.text }}</div>
            <div class="column is-one-quarter">
              <span class="tag is-dark">{{ task.status }}</span>
            </div>
            <div class="column is-one-quarter">
              <div class="buttons are-small">
                <button class="button is-primary" @click="updateTask(task.id)">編集</button>
                <button class="button is-danger" @click="deleteTask(task.id)">削除</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todayTaskItems: [
        {
          id: 'todayTask1',
          text: '今日のタスク1',
          status: '未着手',
        },
        {
          id: 'todayTask2',
          text: '今日のタスク2',
          status: '完了',
        },
        {
          id: 'todayTask3',
          text: '今日のタスク3',
          status: '完了',
        },
      ],
      soonTaskItems: [
        {
          id: 'soonTask1',
          text: '近日のタスク1',
          status: '未着手',
        },
        {
          id: 'soonTask2',
          text: '近日のタスク2',
          status: '完了',
        },
        {
          id: 'soonTask3',
          text: '近日のタスク3',
          status: '完了',
        },
      ],
      laterTaskItems: [
        {
          id: 'laterTask1',
          text: '後日のタスク1',
          status: '未着手',
        },
        {
          id: 'laterTask2',
          text: '後日のタスク2',
          status: '完了',
        },
        {
          id: 'laterTask3',
          text: '後日のタスク3',
          status: '完了',
        },
      ],
    }
  },
  methods: {
    createTask() {
      console.log('作成');
    },
    updateTask(id) {
      console.log(`編集：${id}`);
    },
    deleteTask(id) {
      console.log(`削除：${id}`);
    }
  }
}
</script>

<style lang="scss">
.task__item {
  width: 100%;
}
</style>
