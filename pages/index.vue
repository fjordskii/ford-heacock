<template>
  <div class="container">
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.9.0/css/all.css"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Merriweather:wght@300;700&family=Source+Sans+Pro:wght@300&display=swap"
      rel="stylesheet"
    />
    <div>
      <h1 class="title">Ford Heacock</h1>
      <div class="aboutMe">
        <span
          >Hello! I'm Ford. I'm a software developer and engineering manager
          with a passion for teaching others and helping the next generation of
          web devs. <br /><br />
          Currently, I'm working with NASA through MRI 🚀

          <br /><br />I also love traveling,
          <u
            ><a href="https://fordheacock.myportfolio.com/" target="_blank"
              >photography</a
            ></u
          >, and all things outdoors!</span
        >
      </div>
      <div id="contact-info">
        <div class="links">
          <a
            href="https://www.linkedin.com/in/ford-heacock-22a78620/"
            target="_blank"
          >
            <div>
              <span></span>
              <span></span>
              <span></span>
              <span></span>
              <span>
                <i class="fab fa-linkedin-in"></i>
              </span>
            </div>
          </a>
          <a
            href="https://github.com/fjordski"
            target="_blank"
            class="orange-shadow"
          >
            <div>
              <span></span>
              <span></span>
              <span></span>
              <span></span>
              <span>
                <i class="fab fa-github"></i>
              </span>
            </div>
          </a>
          <a
            href="https://www.twitter.com/fjordskii"
            class="orange-border"
            target="_blank"
          >
            <div>
              <span></span>
              <span></span>
              <span></span>
              <span></span>
              <span>
                <i class="fab fa-twitter"></i>
              </span>
            </div>
          </a>
          <a
            href="https://www.instagram.com/fjordskii"
            class="orange-background"
            target="_blank"
          >
            <div>
              <span></span>
              <span></span>
              <span></span>
              <span></span>
              <span>
                <i class="fab fa-instagram"></i>
              </span>
            </div>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
a {
  color: inherit; /* blue colors for links too */
  text-decoration: inherit; /* no underline */
}

.aboutMe {
  font-family: 'Source Sans Pro', sans-serif;
  text-align: left;
  max-width: 325px;
  margin: 0 auto;
  color: lightgrey;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Merriweather', serif;
  display: block;
  font-weight: 300;
  font-size: 50px;
  color: #f0ead6;
  letter-spacing: 1px;
  margin-bottom: 30px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

body {
  --color-bright: #f2f1c6;
  --color-orange: #ff6138;
  --body-background-color: #2c3135;

  background: var(--body-background-color);
}

#intro {
  color: var(--color-bright);
  position: absolute;
  top: 30px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 1.5rem;
}

#contact-info {
  margin-top: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
}

#contact-info .links {
  display: flex;
  min-width: 300px;
  justify-content: space-between;
}

#contact-info a {
  text-decoration: none;
  color: var(--color-bright);
  font-size: 2rem;
}

/* ****************** */
/* PREVENTING FLICKERING ON HOVER BECAUSE OF ROTATING AND SKEW TRANSFORMATIONS*/
#contact-info .links a {
  display: block;
  position: relative;
}
#contact-info .links a::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 1px solid transparent;
  transition: all 0.3s;
}
#contact-info .links a:hover::after {
  /* transform: rotate(35deg) skew(-20deg); */
  --transformed-box-diagonal-length: 164%;
  width: var(--transformed-box-diagonal-length);
  left: calc((100% - var(--transformed-box-diagonal-length)) / 2);
}
/* ****************** */

#contact-info .links a div {
  position: relative;
  display: block;
  width: 55px;
  height: 55px;
  transition: transform 0.3s;
}

#contact-info .links a:hover div {
  transform: rotate(-35deg) skew(20deg);
}

.links a span {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transition: 0.5s;
  /* transition-property: opacity, transform;
  transition-duration: 0.5s; */
  border: 1px solid var(--color-bright);
  /* border-color: var(--color-bright); */
  border-radius: 5px;
}

.links a span:nth-child(5) {
  display: flex;
  justify-content: center;
  align-items: center;

  position: relative;
  /* border-color: var(--color-bright); */
}

.links a:hover span:nth-child(5) {
  transform: translate(20px, -20px);
  opacity: 1;
}
.links a:hover span:nth-child(4) {
  transform: translate(15px, -15px);
  opacity: 0.8;
}
.links a:hover span:nth-child(3) {
  transform: translate(10px, -10px);
  opacity: 0.6;
}
.links a:hover span:nth-child(2) {
  transform: translate(5px, -5px);
  opacity: 0.4;
}
.links a:hover span:nth-child(1) {
  opacity: 0.2;
}

/* orange background spans */
.links a.orange-background span {
  background: var(--color-orange);
  border-color: var(--color-bright);
}
.links a.orange-background span:nth-child(5) {
  background: var(--body-background-color);
}

/* orange shadow */
.links a.orange-shadow:hover span {
  box-shadow: -1px 1px 3px var(--color-orange);
}

/* orange border  */
.links a.orange-border span {
  border-color: var(--color-orange);
}
.links a.orange-border span:nth-child(5) {
  border-color: var(--color-bright);
}
</style>
