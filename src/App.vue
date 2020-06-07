<template>
  <div id="app">
    <div style="background:pink">
      <span>文本</span>
      <br />
      <input v-model="message" placeholder="edit me" />
      <br />
      message: {{message}}
    </div>
    <div style="background:yellow">
      <span>多行文本</span>
      <br />
      <p style="white-space: pre-line;">message: {{ message }}</p>
      <br />
      <textarea v-model="message" placeholder="add multiple lines"></textarea>
    </div>
    <div style="background:orange">
      <span>单个复选框</span>
      <br />
      <label>
        <input type="checkbox" v-model="check" />
        {{check}}
      </label>
      <br />
      check: {{check}}
    </div>
    <div style="background:grey">
      <span>多个复选框</span>
      <br />
      <span>名字为value的集合：{{names}}</span>
      <br />
      <label>
        <input type="checkbox" v-model="names" value="1" />Jack
      </label>
      <label>
        <input type="checkbox" v-model="names" value="2" />Tom
      </label>
      <label>
        <input type="checkbox" v-model="names" value="3" />Steve
      </label>
    </div>
    <div style="background:#cccccc">
      <span>单选按钮</span>
      <br />
      <span>目前选择（默认2）pick: {{pick}}</span>
      <br />
      <label>
        <input type="radio" v-model="pick" value="1" />Yes
      </label>
      <label>
        <input type="radio" v-model="pick" value="2" />No
      </label>
    </div>
    <div style="background:#dddddd">
      <span>单选框</span>
      <br />
      <span>目前选择 select: {{select}}</span>
      <br />
      <select v-model="select">
        <option value disabled>请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
    </div>
    <div style="background:#eeeeee">
      <span>多选框</span>
      <br>
      <select v-model="selected" multiple style="width:100px">
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <br />
      <span>Selected: {{ selected }}</span>
    </div>
    <div style="background:#ffffff">
      <span>form 表单</span>
      <br>
      <form action="" @submit.prevent="onSubmit">
        <label>
          <span>用户名</span>
          <input type="text" v-model="user.name">
        </label>
        <label>
          <span>密码</span>
          <input type="password" v-model="user.password">
        </label>
        <br>
        <button type="submit">submit</button>
      </form>
      <span>您的用户信息为：</span>
      <br>
      <span>用户名：{{user.name}}</span>
      <br>
      <span>密码：{{user.password}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "hello",
      check: false,
      names: [],
      pick: "2",
      select: "",
      selected:[],
      user:{
        name:'',
        password:''
      }
    };
  },
  methods:{
    onSubmit(){
      console.log(this.user)
    }
  }
};
</script>

<style>
</style>
