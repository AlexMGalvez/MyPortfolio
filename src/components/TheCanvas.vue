<script>
export default {
  name: "App",
  mounted() {
    const script = function (p5) {
      let particles = [];

      p5.setup = () => {
        p5.createCanvas(window.innerWidth, window.innerHeight);

        for (let i = 0; i < p5.width / 10; i++) {
          particles.push(new Particle());
        }
      };

      class Particle {
        // setting the co-ordinates, radius and the
        // speed of a particle in both the co-ordinates axes.
        constructor() {
          this.x = p5.random(0, p5.width);
          this.y = p5.random(0, p5.height);
          this.r = p5.random(1, 8);
          this.xSpeed = p5.random(-2, 2);
          this.ySpeed = p5.random(-1, 1.5);
          this.colour = this.chooseColour();
        }

        // creation of a particle.
        createParticle() {
          p5.noStroke();
          p5.fill(this.colour);
          p5.circle(this.x, this.y, this.r);
        }

        chooseColour() {
          let rand = p5.random(0, 1);
          if (rand < 0.8) {
            //white
            return "rgba(240,239,254,0.5)";
          } else {
            //red
            return "rgba(175,28,28,0.5)";
          }
        }

        // setting the particle in motion.
        moveParticle() {
          if (this.x < 0 || this.x > p5.width) this.xSpeed *= -1;
          if (this.y < 0 || this.y > p5.height) this.ySpeed *= -1;
          this.x += this.xSpeed;
          this.y += this.ySpeed;
        }

        // this function creates the connections(lines)
        // between particles which are less than a certain distance apart
        joinParticles(particles) {
          particles.forEach((element) => {
            let dis = p5.dist(this.x, this.y, element.x, element.y);
            
            if (dis < 100) {
              if (this.colour == "rgba(240,239,254,0.5)") {
                p5.stroke("rgba(240,239,254,0.15)");
                p5.line(this.x, this.y, element.x, element.y);
              } else {
                p5.stroke("rgba(175,28,28,0.15)");
                p5.line(this.x, this.y, element.x, element.y);
              }
            }
          });
        }
      }

      p5.draw = () => {
        p5.background("#31A2AC");
        for (let i = 0; i < particles.length; i++) {
          particles[i].createParticle();
          particles[i].moveParticle();
          particles[i].joinParticles(particles.slice(i));
        }
      };
    };
    const P5 = require("p5");
    new P5(script);
  },
};
</script>

