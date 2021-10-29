<template>
  <div>
    <h1>Register your account</h1>
    <div>
      <form action="" method="post">
        <h3>Email</h3>
        <input type="text" name="email" id="email" />

        <h3>Password</h3>
        <input type="text" name="pass" id="pass" />

        <h3>Confirm Password</h3>
        <input type="text" name="confPass" id="confPass" />

        <input type="button" value="Register" />
      </form>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  setup() {}
});
</script>
