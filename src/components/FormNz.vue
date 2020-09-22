<template>
  <div class="needsFields">
    <div v-for="field in formData.needsFields" :key="field.code">
      <b-field :label="field.code" :message="field.disclaimerText">
          <b-input :type="field.dataType" ></b-input>
      </b-field>
      <div>
        <b-checkbox v-if="field.isDisclaimerRequired">I have read the disclaimers</b-checkbox>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FormNz',
  props: {
    formData: Object
  }
}
</script>
