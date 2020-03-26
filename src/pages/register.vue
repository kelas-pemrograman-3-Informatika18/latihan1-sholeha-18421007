<template>

    <q-page>
      <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="ketikkan nama *"
        lazy-rules
        :rules="[va1 => va1 && va1.length > 0 || 'wajib di isi']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="ketikkan kata sandi *"
        lazy-rules
        :rules="[va1 => va1 && va1.length > 0 || 'wajib di isi']"
      />

       <q-input
        filled
        v-model="hoby"
        label="ketikkan hoby kamu *"
        lazy-rules
        :rules="[va1 => va1 && va1.length > 0 || 'wajib di isi']"
      />
      <div>
        <q-btn to="/" label="Submit" type="submit" color="green"/>
        <q-btn to="reset" label="Reset" type="Reset" color="green" flat class="q-ml-sm" />
        <q-toggle
      v-model="value"
      color="green"
      />
      </div>
      </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      nama: null,
      password: null,
      hoby: null,
      moto: null
    }
  },
  methods: {
    onSubmit () {
      console.log('fungsi submit')
    },
    onReset () {
      console.log('fungsi reset')
    }
  }
}
</script>
