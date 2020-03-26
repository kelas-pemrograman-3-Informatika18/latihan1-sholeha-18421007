<template>
  <q-page class="bg-yellow-3">
    <div class="row">
      <q-card class="fixed-center col-md-4 col-xs-12 bg-green" flat>
        <q-card-section>
          <div class="text h-6 q-pb-md">
            Halaman login
          </div>
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="Username *"
        lazy-rules
        :rules="[va1 => va1 && va1.length > 0 || 'wajib di isi']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Your Password *"
        lazy-rules
        :rules="[
        va1 => va1 && va1.length > 0 || 'wajib di isi'
        ]"
      />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="register" type="register" color="primary" flat class="q-m1-sm" />
        <q-btn to="register" label="register" type="register" color="green" />
      </div>
    </q-form>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      name: null,
      password: null

    }
  },
  methods: {
    onSubmit () {
      if (this.name === 'sholeha' && this.password === '12345678') {
        this.$q.notify({
          type: 'positive',
          message: 'selamat anda berhasil login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'maaf anda gagal login, username/password salah'
        })
      }
    },
    onReset () {
      console.log('fungsi reset')
    },
    onRegister () {
      console.log('fungsi register')
    }
  }
}
</script>
