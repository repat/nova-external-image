<template>
    <panel-item :field="field">
        <div slot="value">

            <img class="external-image-thumbnail" :style="{ width, height, borderRadius }" v-if="url" :src="url">

            <span v-else>&mdash;</span>
        </div>
    </panel-item>
</template>

<script>

  export default {
    props: ['resource', 'resourceName', 'resourceId', 'field'],

    computed: {
      url () {
        if (this.field.prefix) {
          return `${this.field.prefix}${this.field.value}`
        }

        return this.field.value
      },
      width () {
        return this.field.width + 'px' || 'auto'
      },

      height () {
        return this.field.height + 'px' || 'auto'
      },

      borderRadius () {
        return this.field.borderRadius + 'px' || '0'
      },
    },
  }
</script>
