<script>
export default {
  name: 'ChildForm',
  props: {
    value: {
      type: Object,
      default: () => {},
    },
  },
  created() {
    console.log(this.value);
  },
  methods: {
    updateName(name) {
      console.log("updateName", name)
      const newValue = {
        ...this.value,
        name: name,
      }
      this.$emit('input', newValue)
    },
    updateAge(age) {
      const newValue = {
        ...this.value,
        age: age,
      }
      this.$emit('input', newValue)
    }
  }
}
</script>

<template>

  <div>
    <input type="text" :value="value.name" @input="updateName($event.target.value)" />
    <input type="number" :value="value.age"  @input="updateAge($event.target.value)" />
  </div>
</template>
