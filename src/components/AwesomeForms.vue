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
      }
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
    <ChildForm :value="form" @input="handleUdateInput" />
    {{ form.name }}
    <p>{{  form.age  }}</p>
  </div>

</template>
