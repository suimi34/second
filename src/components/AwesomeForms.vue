<script>
import ChildForm from './ChildForm.vue'

export default {
  name: "AwesomeForms",
  components: {
    ChildForm
  },
  data() {
    return {
      form: {
        name: "",
        age: 20
      },
      term: "",
    };
  },
  methods: {
    handleUdateInput(value) {
      this.form = { ...this.form, ...value };
    }
  },
}

</script>

<template>

  <div>
    <p>some text</p>
    <input text="text" v-model="term" placeholder="term" />
    <ChildForm :value="form" :parent-term="term" @input="handleUdateInput" />
    {{ form.name }}
    <p>{{  form.age  }}</p>
    <p>ターム</p>
    {{  term }}
  </div>

</template>
