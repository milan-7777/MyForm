<template>
  <div id="main">
    <form action="" name="myform">
      <label for="name">Name and lastname</label>
      <input type="text" name="name_lastname" id="name">

      <label for="age">Age</label>
      <input type="number" name="age" id="age">

      <label for="product1">Product 1</label>
      <input type="radio" name="product" id="product">
      
      <label for="product1">Product 2</label>
      <input type="radio" name="product" id="product">

      <label for="check">Agree to terms and conditions</label>
      <input type="checkbox" name="check" id="check">

      <button @click="checkInputs" type="submit">Submit</button>
    </form>
  </div>
</template>

<script setup>

  function checkName() {
    var regEx = /^[a-zA-Z\s]+$/;
    let name = document.getElementById('name')
    if(name.value.match(regEx)) {
      return true
    }
    else {
      document.getElementById("name").style.border = '3px solid red';
      alert('Letters only.')
      return false
    }
  }

  function checkNum() {
    let age = document.getElementById("age").value;
    if (age >= 17) {
      return true
    }
    else {
      document.getElementById("age").style.border = '3px solid red';
      alert ('You must be 17 or older!')
      return false
    }
  }

  function checkRadio() {
    let radioBtn = document.getElementById('product').required = true;
  }

  function checkTerms() {
    let checkbox = document.getElementById('check').required = true;
  }

  function checkInputs(e) {
    checkRadio()
    checkTerms()
    if(!checkName() || !checkNum()) {
      e.preventDefault()
    }
  }

</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-image: url('https://images.pexels.com/photos/956999/milky-way-starry-sky-night-sky-star-956999.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
  background-size: cover;
  color: rgb(224, 62, 224);
  letter-spacing: 2px;
}

form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  max-width: 800px;
  margin: 0 auto;
  margin-top: 50px;
}
label {
  font-size: 18px;
}
input {
  height: 25px;
  background-color: rgb(182, 230, 104);
}

button {
  background-color: rgb(91, 231, 91);
  height: 35px;
  border-radius: 10px;
  border: 2px solid black;
  letter-spacing: 2px;
  font-size: 16px;
  color: rgb(100, 8, 100);;
}

button:hover {
 background-color: rgb(65, 199, 65);
 transform: scale(1.03);
}

</style>