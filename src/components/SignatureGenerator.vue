<template>
  <div>
    <br><br><br>

    <div style="font-family:Arial, Calibri, Helvetica, sans-serif; text-decoration: none; font-size: 9pt; color:#202D3A;">
      <p>Met vriendelijke groet,</p>
    </div>
    <p><span><a href="https://foryard.nl/"><img width="170" style="text-decoration: none; color:#202D3A; width: 100%; max-width: 170px;" src="https://foryard.nl/foryard-email-signature.png" alt="Logo Foryard"/></a></span>
    </p>
    <div style="font-family:Arial, Calibri, Helvetica, sans-serif; text-decoration: none; font-size: 9pt; color:#202D3A; margin-left:38px;">
      <p>
        <span style="color: #00263a; letter-spacing:1px;"><strong>{{ formattedName }}<br></strong></span><span style="color:#9EAFC4"><em>{{ formattedRole }}</em></span>
      </p>
      <p>
        <span><a style="text-decoration: none; color: #202D3A;" :href="'tel:00316' + phoneNumber">{{ '+31(0)6 ' + formattedPhoneNumber }}<br></a></span>
      </p>
    </div>

    <br><br>
  </div>
</template>

<script>
export default {
  name: 'SignatureGenerator',

  props: {
    name: String,
    role: String,
    phoneNumber: String
  },

  computed: {
    formattedName () {
      return this.name.toUpperCase()
    },

    formattedRole () {
      return this.role.charAt(0).toUpperCase() + this.role.slice(1);
    },

    formattedPhoneNumber () {
      let formattedNumber = []

      this.phoneNumber.split('').forEach((element, key) => {
        if (key % 2 === 0 && key !== 0) {
          formattedNumber.push(' ')
        }
        formattedNumber.push(element)
      })

      return formattedNumber.join('')
    }
  },
}
</script>
