<template>
  <div>
    <div v-for="field in formData.needsFields" :key="field.code">
      <b-field :label="field.code">
          <b-input :type="field.dataType" ></b-input>
      </b-field>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FormAu',
  props: {
    formData: Object
  }
}
</script>
