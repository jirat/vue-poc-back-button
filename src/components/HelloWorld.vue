<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  mounted() {
    webview()
  },
  data() {
    return {
      msg: "Hello"
    }
  }
}

export function webview() {
  window.webview = {
      getBackButtonClickEvent : (data) => {
        console.log(JSON.parse(data))
        const clicked = JSON.parse(data).clicked
        if (clicked) {     
          alert('BACK')
          console.log('Do some go back')
         //backPage()
        } else {
          console.log('Do noting', data)
        }
        return 'getBackButtonClickEvent data received'
      }
  }
}
</script>