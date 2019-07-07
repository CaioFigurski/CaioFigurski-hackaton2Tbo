<template>
  <div id="component">
    <v-text-field
      v-validate="'required'"
      :error-messages="errors.collect('example')"
      box=""
      label="Usuario"
      required=""
      data-vv-name="example"
      data-vv-as="Example"
    />

    <v-text-field
      v-validate="'required'"
      :error-messages="errors.collect('example')"
      type="password"
      box=""
      label="Senha"
      required=""
      data-vv-name="example"
      data-vv-as="Example"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      example: null
    };
  }
};
</script>
