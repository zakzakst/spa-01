<template>
  <div>
    <h1 class="title">ユーザー一覧</h1>
    <div class="mb-4">
      <button class="button is-primary" @click="createUser">
        <span class="icon">
          <fa :icon="['fas', 'plus']" />
        </span>
        <span>新規ユーザー登録</span>
      </button>
    </div>
    <table class="table is-striped is-fullwidth">
      <thead>
        <tr>
          <th v-for="heading in tableData.headings" :key="heading.id">{{ heading.label }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in tableData.users" :key="user.uid">
          <th>{{ user.num }}</th>
          <td>{{ user.lastName }}</td>
          <td>{{ user.firstName }}</td>
          <td>{{ user.handleName }}</td>
          <td>
            <div class="buttons are-small">
              <button class="button is-primary" @click="updateUser(user.uid)">編集</button>
              <button class="button is-danger" @click="deleteUser(user.uid)">削除</button>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
    <nav class="pagination">
      <ul class="pagination-list">
        <li><a class="pagination-link">1</a></li>
        <li><span class="pagination-ellipsis">&hellip;</span></li>
        <li><a class="pagination-link">45</a></li>
        <li><a class="pagination-link is-current">46</a></li>
        <li><a class="pagination-link">47</a></li>
        <li><span class="pagination-ellipsis">&hellip;</span></li>
        <li><a class="pagination-link">86</a></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: {
        headings: [
          {
            id: 'num',
            label: 'No.'
          },
          {
            id: 'lastName',
            label: '苗字'
          },
          {
            id: 'firstName',
            label: '名前'
          },
          {
            id: 'handleName',
            label: 'ハンドルネーム'
          },
          {
            id: 'controls',
            label: '操作'
          },
        ],
        users: [
          {
            num: '1',
            lastName: '山田',
            firstName: '太郎',
            handleName: 'yamatoro',
            uid: 'user1',
          },
          {
            num: '2',
            lastName: '佐藤',
            firstName: '次郎',
            handleName: 'satojiro',
            uid: 'user2',
          },
          {
            num: '3',
            lastName: '吉田',
            firstName: '三郎',
            handleName: 'yoshisaburo',
            uid: 'user3',
          },
          {
            num: '4',
            lastName: '伊藤',
            firstName: '四郎',
            handleName: 'itoshiro',
            uid: 'user4',
          },
        ]
      }
    }
  },
  methods: {
    createUser() {
      console.log('作成');
    },
    readUser() {
      console.log('読込');
    },
    updateUser(uid) {
      console.log(`編集：${uid}`);
    },
    deleteUser(uid) {
      console.log(`削除：${uid}`);
    },
  }
}
</script>
