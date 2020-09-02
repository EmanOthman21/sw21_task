<template>
  <div class="content">
    <nav>
      <img src="../assets/stp_logo.png" alt="" class="logo" />
      <ul>
        <li>Home</li>
        <li>About</li>
        <li>Projects</li>
      </ul>
    </nav>
    <div class="inputs">
      <input type="text" placeholder="ex: red or #ff0000" v-model="color" />
      <button @click="changeColor">Change</button>
    </div>
    <section>
      <div class="container">
        <h2>Vission</h2>
        <p>
          STP's Vision is "Being a leading organization working on developing
          youth who will lead the positive change."
        </p>
        <p>
          STP attempts to deliver values and achieve its vision through 3
          different projects:
        </p>
        <ul>
          <li>Conference (Engineering - Management)</li>
          <li>Juniors</li>
          <li>Events</li>
        </ul>
      </div>
    </section>
    <section id="section2" data-nav="Section 2">
      <div class="container">
        <h2>Misson</h2>
        <p>
          To develop youth in various fields personally and technically through
          academic programs, projects, and events in a values oriented system,
          to take our part in providing a generation capable of playing its
          roles effictively towards itself, community and country.
        </p>
      </div>
    </section>
    <section id="section3" data-nav="Section 3">
      <div class="container">
        <h2>Overview</h2>
        <p>
          STP "Steps Towards Progress" is a student activity which was held for
          the first time in the academic year 2005/2006; It is completely
          managed and organized by students under the supervision of The
          Association of Friends of the National Cancer-free Intiative (AFNCI),
          the idea was raised to provide students with the skills needed by the
          supplementary skills needed in the labor market.
        </p>
      </div>
    </section>
    <section>
      <h2>Teams</h2>
      <div class="images">
        <img class="mySlides" src="../assets/SoftwareDevelopment.jpg" style="display:block;"/>
        <img class="mySlides" src="../assets/engineering.jpg" />
        <img class="mySlides" src="../assets/juniors.jpg" />
        <img class="mySlides" src="../assets/media.jpg" />
        <img class="mySlides" src="../assets/pr.jpg" />
        <img class="mySlides" src="../assets/dcr.jpg" />
        <img class="mySlides" src="../assets/fundraising.jpg" />
        <img class="mySlides" src="../assets/hr.jpg" />
        <img class="mySlides" src="../assets/logistics.jpg" />
        <img class="mySlides" src="../assets/management.jpg" />
        <img class="mySlides" src="../assets/qd.jpg" />
        <img class="mySlides" src="../assets/socialMedia.jpg" />
        <button
          class="w3-button w3-black w3-display-left"
          @click="plusDivs(-1)"
        >
          &#10094;
        </button>
        <button
          class="w3-button w3-black w3-display-right"
          @click="plusDivs(1)"
        >
          &#10095;
        </button>
      </div>
    </section>
    <footer class="page__footer"></footer>
  </div>
</template>

<script>
export default {
  created: function() {
    this.showDivs((this.slideIndex += 1));
  },
  data: function() {
    return {
      color: "",
      slideIndex: 0
    };
  },
  methods: {
    changeColor: function() {
      let paragraphs = document.querySelectorAll("p");
      let headings = document.querySelectorAll("h2");
      let list = document.querySelectorAll("li");
      for (let i = 0; i < paragraphs.length; i++)
        paragraphs[i].style.color = this.color;
      for (let i = 0; i < headings.length; i++)
        headings[i].style.color = this.color;
      for (let i = 0; i < list.length; i++) list[i].style.color = this.color;
    },
    plusDivs: function(n) {
      this.showDivs((this.slideIndex += n));
    },

    showDivs: function(n) {
      var i;
      var x = document.getElementsByClassName("mySlides");
      if (n > x.length) {
        this.slideIndex = 1;
      }
      if (n < 1) {
        this.slideIndex = x.length;
      }
      for (i = 0; i < x.length; i++) {
        x[i].style.display = "none";
      }
      x[this.slideIndex - 1].style.display = "block";
    }
  }
};
</script>

<style scoped>
/**Nav Bar
********************/
nav {
  background-color: brown;
  height: 70px;
  margin: 0;
}

nav ul {
  list-style-type: none;
  color: white;
  float: right;
  margin-right: 15vw;
}

nav li {
  display: inline;
  font-size: 20px;
  margin: 35px;
  cursor: pointer;
  font-weight: bold;
}

.logo {
  width: 60px;
  height: 60px;
  margin-left: 15vw;
  padding: 5px;
}
/*User Input
*****************/
.inputs {
  display: flex;
  justify-content: center;
  margin: 20px 0 0 0;
}

input {
  padding: 10px 20px;
  border-radius: 10px;
  border-color: brown;
  margin-right: 10px;
  outline: none;
}

button {
  background-color: brown;
  color: white;
  border: 0;
  border-radius: 20px;
  padding: 10px 30px;
  outline: none;
  font-weight: bold;
  font-size: 16px;
}
/*Sections
******************/
section {
  padding: 0px 40px;
}

.container li {
  list-style-type: circle;
}

.container p {
  max-width: 1000px;
}
/*Images
*******************/
.mySlides {
  display: none;
}

img {
  width: 40%;
}

.images {
  margin-left: 35vw;
}

.images button {
  margin: 0 250px 20px 0px;
}
/*Footer
******************/
footer {
  background-color: brown;
  margin-bottom: 0;
  height: 50px;
}
</style>
