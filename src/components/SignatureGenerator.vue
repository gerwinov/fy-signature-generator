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

    <div style="font-family:Arial, Calibri, Helvetica, sans-serif; text-decoration: none; font-size: 9pt; color:#9EAFC4;">
      <br>
      <p><span><a style="text-decoration: none; color: #9EAFC4;" href="https://foryard.nl/">Foryard.nl</a>  ●  <a style="text-decoration: none; color: #9EAFC4;" href="tel:0031880040600">+31 (0)88 004 0600</a>  ●  <a style="text-decoration: none; color: #9EAFC4;" href="https://www.google.nl/maps/place/Kuipersstraat+35,+1074+EE+Amsterdam/@52.3541686,4.9029117,17z/data=!3m1!4b1!4m5!3m4!1s0x47c6098f8c959307:0xdaab052fb0fe66e7!8m2!3d52.3541686!4d4.9051004">Kuipersstraat 35, Amsterdam (NIEUW!)</a></span></p>
    </div>
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
