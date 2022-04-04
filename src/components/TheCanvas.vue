<script>
export default {
  name: "App",
  mounted() {
    const script = function(p5) {
      const rows = 10;
      const columns = 10;
      // const fadeSpeed = 1;
      let cells = [];

      p5.setup = () => {
        p5.createCanvas(window.innerWidth, window.innerHeight);

        for (let r = 0; r < rows; r++) {
          cells[r] = [];
          for (let c = 0; c < columns; c++) {
            //cells[r][c] = p5.random(255);
            cells[r][c] = "#99DDFF";
          }
        }
      };

      p5.draw = () => {
        //   p5.background("#99DDFF");

        //   for (let i = 0; i < particles.length; i++) {
        //     particles[i].createParticle();
        //     particles[i].moveParticle();
        //     particles[i].joinParticles(particles.slice(i));
        //   }

        const cellWidth = p5.width / columns;
        const cellHeight = p5.height / rows;

        // if (p5.mouseX > 0 && p5.mouseX < p5.width && p5.mouseY > 0 && p5.mouseY < p5.height) {
        //   const mouseR = p5.floor(rows * (p5.mouseY / p5.height));
        //   const mouseC = p5.floor(columns * (p5.mouseX / p5.width));
        //   cells[mouseR][mouseC] = 255;
        // }

        for (let r = 0; r < rows; r++) {
          for (let c = 0; c < columns; c++) {
            // cells[r][c] -= fadeSpeed;
            // cells[r][c] = p5.constrain(cells[r][c], 255, 0);

            const y = p5.height * (r / rows);
            const x = p5.width * (c / columns);

            p5.fill(cells[r][c]);
            p5.noStroke();
            p5.rect(x, y, cellWidth, cellHeight);
          }
        }
      };
    };
    const P5 = require("p5");
    new P5(script);
  },
};
</script>
