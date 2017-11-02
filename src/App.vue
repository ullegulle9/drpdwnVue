<template>
  <div id="app">
    <ul>
      <div v-for="c in cars">
        <div class="accordion" v-on:click="handleClick"> {{c.brand}}, {{ c.model }} </div>
        <div class="content">
          <p>{{c.vehicleType}}</p>
          <p>{{c.year}}</p>
          <p>{{c.gearbox}}</p>
          <p>{{c.status}}</p>
        </div>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      cars: [
        {
          "vehicleType": "personbil",
          "requiredDriversLicense": "B",
          "brand": "Mazda",
          "model": "323i",
          "year": 1991,
          "gearbox": "manuell",
          "dailyFee": 298,
          "imgLink": "https://upload.wikimedia.org/wikipedia/commons/7/72/Mazda_323f_green_front_20080301.jpg",
          "fuel": null,
          "status": "available"
        },
        {
          "vehicleType": "personbil",
          "requiredDriversLicense": "B",
          "brand": "Volvo",
          "model": "S50",
          "year": 2005,
          "gearbox": "manuell",
          "dailyFee": 498,
          "imgLink": "https://upload.wikimedia.org/wikipedia/commons/e/ea/Volvo_V50_--_04-20-2010.jpg",
          "fuel": null,
          "status": "available"
        },
        {
          "vehicleType": "motorcykel",
          "requiredDriversLicense": "A",
          "brand": "Yamaha",
          "model": "YCF R1",
          "year": 2001,
          "gearbox": null,
          "dailyFee": 498,
          "imgLink": '#',
          "fuel": null,
          "status": "available"
        },
        {
          "vehicleType": "personbil",
          "requiredDriversLicense": "B",
          "brand": "Toyota",
          "model": "Aygo",
          "year": null,
          "gearbox": "manuell",
          "dailyFee": 198,
          "imgLink": "https://upload.wikimedia.org/wikipedia/commons/e/e1/Toyota_Aygo_front_20071204.jpg",
          "fuel": null,
          "status": "available"
        },
        {
          "vehicleType": "ATV",
          "requiredDriversLicense": "A1",
          "brand": "Can-Am",
          "model": "Outlander 570",
          "year": 2008,
          "gearbox": "manuell",
          "dailyFee": 598,
          "imgLink": '#',
          "fuel": null,
          "status": "available"
        }
      ]
    }
  },
  methods: {
    handleClick: function(ev) {
      let content = ev.target.nextElementSibling;
      if (content.style.maxHeight){
        content.style.maxHeight = null;
      } else {
        content.style.maxHeight = content.scrollHeight + "px";
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: center;
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

a {
  color: #42b983;
}

.accordion {
  width: 300px;
  background-color: whitesmoke;
  border: none;
  outline: none;
  text-align: left;
  padding: 15px 20px;
  transition: background-color 0,2s linear;
}

.accordion:hover {
  background-color: #ddd;
}

.content {
  width: 258px;
  padding: 0 20px;
  max-height: 0;
  overflow: hidden;
  border-left: 1px solid whitesmoke;
  border-right: 1px solid whitesmoke;
  transition: max-height 0.5s ease-in-out;
}
</style>
