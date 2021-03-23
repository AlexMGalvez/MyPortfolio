<script>
export default {
  name: "App",
  mounted() {
    const script = function (p5) {
      let particles1 = [];
      let particles2 = [];

      p5.setup = () => {
        p5.createCanvas(window.innerWidth, window.innerHeight);

        for (let i = 0; i < p5.width / 14; i++) {
          particles1.push(new Particle("background"));
          particles2.push(new Particle("foreground"));
        }
      };

      class Particle {
        // setting the co-ordinates, radius and the
        // speed of a particle in both the co-ordinates axes.
        constructor(type) {
          this.x = p5.random(0, p5.width);
          this.y = p5.random(0, p5.height);
          this.r = p5.random(1, 8);

          if (type == "background") {
            this.colour = "rgba(10,0,50,0.5)";
            this.xSpeed = p5.random(-0.1, 0.1);
            this.ySpeed = p5.random(-0.1, 0.3);
          } else {
            this.colour = "rgba(53,0,211,0.5)";
            this.xSpeed = p5.random(-1, 1);
            this.ySpeed = p5.random(-0.5, 1);
          }
        }

        // creation of a particle.
        createParticle() {
          p5.noStroke();
          if (this.colour != "rgba(10,0,50,0.5)") {
            p5.fill(this.colour);
            p5.circle(this.x, this.y, this.r);
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
            let dis = Math.floor(p5.dist(this.x, this.y, element.x, element.y));
            let opacityValue = 1;

            if (dis < 120 && this.colour == "rgba(10,0,50,0.5)") {
              opacityValue = (1 - dis / 120) / 4;
              p5.strokeWeight(15);
              p5.stroke("rgba(10,0,50," + opacityValue + ")");
              p5.line(this.x, this.y, element.x, element.y);
            } else if (dis < 120) {
              opacityValue = 1 - dis / 120;
              p5.strokeWeight(1);
              p5.stroke("rgba(53,0,211," + opacityValue + ")");
              p5.line(this.x, this.y, element.x, element.y);
            }
          });
        }
      }

      p5.draw = () => {
        // let c1 = p5.color("black");
        // let c2 = p5.color(10,0,50);
        // setGradient(c1, c2);
        p5.background("black");

        for (let i = 0; i < particles1.length; i++) {
          particles1[i].createParticle();
          particles1[i].moveParticle();
          particles1[i].joinParticles(particles1.slice(i));
        }

        for (let i = 0; i < particles2.length; i++) {
          particles2[i].createParticle();
          particles2[i].moveParticle();
          particles2[i].joinParticles(particles2.slice(i));
        }
      };

      // function setGradient(c1, c2) {
      //   p5.noFill();
      //   for (var y = 0; y < p5.height; y++) {
      //     var inter = p5.map(y, 0, p5.height, 0, 1);
      //     var c = p5.lerpColor(c1, c2, inter);
      //     p5.stroke(c);
      //     p5.line(0, y, p5.width, y);
      //   }
      // }
    };
    const P5 = require("p5");
    new P5(script);
  },
};
</script>

