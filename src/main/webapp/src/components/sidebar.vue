<template>
  <div id="sidebar-view">
    <div class="user">
      <img src="../../build/images/avatar.png">
      <span>{{user.nick_name}}</span>
    </div>
    <div class="project-list">
      <ul>
        <li :class="{active: show === 'all'}" >
          <a @click="filterTask('all')">
            <i class="fa fa-tasks list-icon" aria-hidden="true"></i>
            <span>所有任务</span>
          </a>
        </li>
        <li :class="{active: show === 'plane'}">
          <a @click="filterTask('plane')">
            <i class="fa fa-plane list-icon" aria-hidden="true"></i>
            <span>行程管理</span>
          </a>
        </li>
        <li :class="{active: show === 'todos'}">
          <a @click="filterTask('todos')">
            <i class="fa fa-list-alt list-icon" aria-hidden="true"></i>
            <span>工作安排</span>
          </a>
        </li>
        <li :class="{active: show === 'purchase'}">
          <a @click="filterTask('purchase')">
            <i class="fa fa-list-ul list-icon" aria-hidden="true"></i>
            <span>生活事务</span>
          </a>
        </li>
        <li>
          <a v-link="'stat'">
            <i class="fa fa-area-chart list-icon" aria-hidden="true"></i>
            <span>统计</span>
          </a>
        </li>
      </ul>
    </div>
    <div class="sign-out">
      <i class="fa fa-sign-out sign-out-icon" aria-hidden="true"></i>
      <a v-link="'login'">退出</a>
    </div>
  </div>
</template>

<script>
export default {

  props: ['user', 'show', 'count', 'doneCount'],

  methods: {
    filterTask (num) {
      this.show = num
    }
  }

}
</script>
