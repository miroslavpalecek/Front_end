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
   

    <form @submit="poslidata">
      <div class="form-row">
        <div class="col-md-6 mb-3">
          <label for="validationServer01">First name</label>
          <input type="text" class="form-control is-valid" id="validationServer01" value="Mark" v-model="objektsdaty.prvniklic" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
        <div class="col-md-6 mb-3">
          <label for="validationServer02">Last name</label>
          <input type="text" class="form-control is-valid" id="validationServer02" value="Otto" v-model="objektsdaty.druhyklic" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
      </div>
      <div class="form-row">
        <div class="col-md-6 mb-3">
          <label for="validationServer03">Email adress</label>
          <input type="text" class="form-control is-valid" id="validationServer03" value="Otto" v-model="objektsdaty.tretiklic" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationServer04">Phone</label>
          <input type="text" class="form-control is-valid" id="validationServer04" value="Otto" v-model="objektsdaty.ctvrtyklic" required>
          <div class="valid-feedback">
            Looks good!
          </div>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationServer05">Adress</label>
          <input type="text" class="form-control is-valid" id="validationServer05" value="Otto" v-model="objektsdaty.patyklic" required>
          <div class="valid-feedback">
            Looks good!
          
          </div>
        </div>
      </div>
      
      <button class="btn btn-primary" type="submit">Save Data</button>
    </form>
  </div>
</template>

<script>
const axios = require("axios");
export default {
  name: 'app',
  data () {
    return {
      msg: ' !',
      contacts: [],
      objektsdaty: {
        prvniklic: '',
        druhyklic: '',
        tretiklic: '',
        ctvrtyklic: '',
        patyklic: ''
        
    
      }
    }
  },
  methods: {
    databackend() {
      axios.get('http://localhost:3000/users/')
  .then(response => {
    console.log(response.data);

  this.contacts=response.data;
 
  })
  .catch(function (error) {
    console.log(error);
  });

    },
    poslidata(e) {
        e.preventDefault();
         console.log('rad bych odeslal');
       const axios = require('axios')
       
       axios.post('http://localhost:3000/users/', {
        "First Name":this.objektsdaty.prvniklic,
        "Last Name":this.objektsdaty.druhyklic,
        "email adress":this.objektsdaty.tretiklic,
        "Phone": this.objektsdaty.ctvrtyklic,
        "Adress":this.objektsdaty.patyklic

       })
    .then( function (response) {
      console.log(response);
   
    })
      .catch(function(error) {
      console.log(error);
    });
      
    }
  },
  mounted() {
    this.databackend();
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
