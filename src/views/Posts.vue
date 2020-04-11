<template>
<div>
  <h2>Pray Posts</h2>
  <b-form>
    <b-form-group id="name">
      <b-form-input
        id="input-name"
        v-model="my_name"
        type="text"
        required
        placeholder="Your Name"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="nationality">
      <b-form-input
        id="input-nationality"
        v-model="my_nationality"
        type="text"
        required
        placeholder="Your Nationality"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="pray">
      <b-form-input
        id="input-pray"
        v-model="my_pray"
        type="text"
        required
        placeholder="Your Pray"
      ></b-form-input>
    </b-form-group>

    <b-button @click="mySend" type="submit" variant="primary">Submit</b-button>

  </b-form>
    <section>
      <div class="chat-list">
        <div v-for="m in form" :key="m.key">
          <div class="color"> {{ m.name }} {{ m.nationality }} {{ m.pray }} </div>
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
.color{
    color: #888888;
}

h2 {
  text-align: center;
  padding-top: 50px;
  padding-bottom: 20px;
  font-size: 35px;
  font-weight: 100;
}

form {
  width: 80%;
  margin: 0 auto;
  padding-top: 10px;
}

.button {
  font-weight: bold;
  margin-top: 80px;
  width: 70%;
}

.name {
  font-weight: bold;
  text-align: left;
  padding: 10px;
  width: 30%;
  display: inline-block;
}

.nationality {
  display: inline-block;
  font-weight: bold;
  padding: 10px;
  text-align: left;
  width: 30%;
}

.pray {
  font-weight: bold;
  text-align: left;
  padding-top: 10px;
  margin: 0 auto;
  width: 60%;
}

.chat-list {
  margin-top: 100px;

}
</style>
