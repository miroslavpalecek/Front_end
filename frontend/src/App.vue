<template>
  <div id="app">
     <h1>Show Contacts</h1>

    
    <table class="table table-sm table-dark">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">First Name</th>
          <th scope="col">Last Name</th>
          <th scope="col">email adress</th>
          <th scope="col">phone</th>
          <th scope="col">adress</th>
          <th scope="col">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="kontakt in this.contacts">
          <th scope="row">1</th>
          <td>{{kontakt["First Name"]}}</td>
          <td>{{kontakt["Last Name"]}}</td>
          <td>{{kontakt["email adress"]}}</td>
          <td>{{kontakt["Phone"]}}</td>
          <td>{{kontakt["Adress"]}}</td>
          <td><button type="button" class="btn btn-success">Delete</button></td>
          
        </tr>
      </tbody>
    </table>
    
    <button type="button" class="btn btn-success">Show Contacts</button>
   

    <form>
      <div class="form-row">
        <div class="col-md-6 mb-3">
          <label for="validationServer01">First name</label>
          <input type="text" class="form-control is-valid" id="validationServer01" value="Mark" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
        <div class="col-md-6 mb-3">
          <label for="validationServer02">Last name</label>
          <input type="text" class="form-control is-valid" id="validationServer02" value="Otto" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
      </div>
      <div class="form-row">
        <div class="col-md-6 mb-3">
          <label for="validationServer03">Email adress</label>
          <input type="text" class="form-control is-invalid" id="validationServer03" aria-describedby="validationServer03Feedback" required>
          <div id="validationServer03Feedback" class="invalid-feedback">
            Please provide a valid city.
          </div>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationServer04">Phone</label>
          <select class="custom-select is-invalid" id="validationServer04" aria-describedby="validationServer04Feedback" required>
            <option selected disabled value="">Choose...</option>
            <option>...</option>
          </select>
          <div id="validationServer04Feedback" class="invalid-feedback">
            Please select a valid state.
          </div>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationServer05">Adress</label>
          <input type="text" class="form-control is-invalid" id="validationServer05" aria-describedby="validationServer05Feedback" required>
          <div id="validationServer05Feedback" class="invalid-feedback">
          
          </div>
        </div>
      </div>
      
      <button class="btn btn-primary" type="submit">Submit form</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: ' !',
      contacts: [
    {
        "_id": "5fa8194d44d70453541ab65b",
        "First Name": "Jack",
        "Last Name": "Kerouac",
        "email adress": "JackKerouac@gmail.com",
        "Phone": "755 265 985",
        "Adress": "Rolnicka, Brno, 625 00"
    },
    {
        "_id": "5fa81a183d589f1754615d59",
        "First Name": "Mirek",
        "Last Name": "Palecek",
        "email adress": "MirekPalecek@gmail.com",
        "Phone": "755 532 852",
        "Adress": "Benesova, Ostrava, 622 00"
    },
    {
        "_id": "5fa81a4a3d589f1754615d5a",
        "First Name": "Petra",
        "Last Name": "Cvilinkova",
        "email adress": "PetraCvilinkova@gmail.com",
        "Phone": "756 232 235",
        "Adress": "U návsi, Kotehulky, 526 33"
    },
    {
        "_id": "5fa81a813d589f1754615d5b",
        "First Name": "Marek",
        "Last Name": "Ponocný",
        "email adress": "MarekPonocny@gmail.com",
        "Phone": "526 322 252",
        "Adress": "U mostu, Praha, 755 026"
    },
    {
        "_id": "5fa81ab43d589f1754615d5c",
        "First Name": "Lukáš",
        "Last Name": "Nimrod",
        "email adress": "LukasNimrod@gmail.com",
        "Phone": "755 589 254",
        "Adress": "Ukrajinska, Brno, 625 00"
    }
]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
