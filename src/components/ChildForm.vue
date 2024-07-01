<script>
export default {
  name: 'ChildForm',
  props: {
    value: {
      type: Object,
      default: () => {},
    },
    parentTerm: {
      type: String,
      default: "",
    }
  },
  created() {
    console.log(this.value);
    console.log("parent term", this.parentTerm);
  },
  watch: {
    parentTerm: function (val) {
      console.log("[watch ]parent term", val);
    }
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
