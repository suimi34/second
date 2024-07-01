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
  data() {
    return {
      isActive: true,
    };
  },
  created() {
    console.log(this.value);
    console.log("parent term", this.parentTerm);
  },
  watch: {
    parentTerm: function (val) {
      console.log("[watch ]parent term", val);
      if (val.length > 4) {
        this.isActive = false;
      } else {
        this.isActive = true;
      }
    }
  },
  computed: {
    searchText() {
      return this.isActive ? "Active" : "Inactive";
    },
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
    <div>
      <input type="text" :value="value.name" @input="updateName($event.target.value)" />
      <input type="number" :value="value.age"  @input="updateAge($event.target.value)" />
    </div>
    <button :class="{ appear: isActive, disa: !isActive }">{{  searchText }}</button>
  </div>
</template>

<style scoped>

.disa {
  opacity: .3;
  animation: disa 1s;
}

@keyframes disa {
  from {
    opacity: .7;
  }
  to {
    opacity: .3;
  }
}

.appear {
  opacity: 1;
  animation: appear 1s;
}

@keyframes appear{
  from {
    opacity: .5;
  }
  to {
    opacity: 1;
  }
}
</style>
