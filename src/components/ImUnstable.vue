<template>
  <div v-for="user in users" :key="user.id">
    <p>
      {{ user.name }}
      {{ makeLarge(user.surname) }}
      {{ user.age }}
    </p>
  </div>
</template>

<script>
export default {
  errorCaptured() {
    console.log("let me see");
  },
  data() {
    return {
      users: [
        { id: 1, name: "Luke", surname: "Skywalker", age: "22" },
        { id: 2, name: "Han", surname: {}, age: "35" },
      ],
    };
  },
  methods: {
    makeLarge(data) {
      return data.toUpperCase();
    },
  },
};
</script>