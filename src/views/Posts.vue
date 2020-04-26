<template>
<div>
  <h2>Pray Posts</h2>
  <b-form>
    <b-form-group id="name">
      <b-form-input
        id="input-name"
        v-model="my_name"
        type="text"
        maxlength='20'
        required
        placeholder="Your Name"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="nationality">
      <b-form-input
        id="input-nationality"
        v-model="my_nationality"
        type="text"
        maxlength='15'
        required
        placeholder="Your Nationality"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="pray">
      <b-form-textarea
        id="input-pray"
        v-model="my_pray"
        type="text"
        cols="20"
        wrap="hard"
        rows="2"
        max-rows="3"
        required
        placeholder="Your Pray"
      ></b-form-textarea>
    </b-form-group>

    <b-button @click="mySend" type="submit" variant="primary">Submit</b-button>

  </b-form>
    <section class="chatroom">
      <div class="chat-list">
        <div class="posts" v-for="m in form" :key="m.key">
          <div class="post"> {{ m.name }} <br> {{ m.nationality }} </div>
          <div class="post"> {{ m.pray }} </div>
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
h2 {
  text-align: center;
  padding-top: 50px;
  padding-bottom: 20px;
  font-size: 35px;
  font-weight: 100;
}

form {
  margin: 0 auto;
  padding-top: 10px;
}

button {
  font-weight: bold;
  margin-top: 30px;
  width: 70%;
}

#name {
  font-weight: bold;
  text-align: left;
  padding: 10px;
  width: 40%;
  display: inline-block;
}

#nationality {
  display: inline-block;
  font-weight: bold;
  padding: 10px;
  text-align: left;
  width: 40%;
}

#pray {
  font-weight: bold;
  text-align: left;
  padding-top: 10px;
  margin: 0 auto;
  width: 75%
}

.chatroom {
  background-color: rgb(226, 226, 226);
  margin: 0 auto;
  width: 80%;
  height: 1000px;
}

.chat-list {
  margin-top: 100px;
  text-align: left;
  width: 100%;
}

.posts {
  padding: 20px;
  margin-top: -40px;
}

.post {
  color: #888888;
}
</style>
