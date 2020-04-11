<template>
<div class="chat">
  <section>
    <div class="my_chat">
      <input v-model="my_name" type="text" placeholder="Your Name">
      <input v-model="my_nationality" type="text" placeholder="Your Nationality">
      <input v-model="my_pray" type="text" placeholder="Your Pray">
      <button @click="mySend">送信する</button>
    </div>
  </section>
  <section>
    <div class="chat_list">
      <div v-for="m in form" :key="m.key">
        <div :class="m.style">{{m.name}}</div>
      </div>
      <div v-for="m in form" :key="m.key">
        <div :class="m.style"> {{m.nationality}}</div>
      </div>
      <div v-for="m in form" :key="m.key">
        <div :class="m.style">{{m.pray}}</div>
      </div>
    </div>
  </section>
</div>
</template>

<script>
export default {
  data () {
    return {
      form: [
        { name: '' },
        { nationality: '' },
        { pray: '' }
      ],
      my_name: '',
      my_nationality: '',
      my_pray: '',
      name: '',
      nationality: '',
      pray: ''
    }
  },
  methods: {
    mySend () {
      this.form.push({
        id: 1,
        style: 'my',
        name: this.my_name,
        nationality: this.my_nationality,
        pray: this.my_pray
      })
      this.my_name = ''
      this.my_nationality = ''
      this.my_pray = ''
    }
  }
}
</script>

<style scoped>
.my{
    color: #888888;
}
</style>

<!-- /* <style scoped>
h2 {
  text-align: center;
  padding-top: 50px;
  padding-bottom: 20px;
  font-size: 35px;
  font-weight: 100;
}

.button {
  font-weight: bold;
  margin-top: 80px;
  width: 70%;
}

#input-group-1 {
  font-weight: bold;
  text-align: left;
  padding: 10px;
  width: 30%;
  display: inline-block;
}

#input-group-2 {
  display: inline-block;
  font-weight: bold;
  padding: 10px;
  text-align: left;
  width: 30%;
}

#input-group-3 {
  font-weight: bold;
  text-align: left;
  padding-top: 10px;
  margin: 0 auto;
  width: 60%;
}
</style> */ -->
