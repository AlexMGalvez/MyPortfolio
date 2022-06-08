<script>
export default {
  name: "App",
  mounted() {
    const script = function(p5) {
      // colours:
      // --color1: #00458B; = 0, 69, 139
      // --color2: #2FD2C7; = 47, 210, 199
      // --color3: #99DDFF; = 153, 221, 255

      const rows = p5.floor(window.innerWidth / 180);
      const columns = p5.floor(window.innerHeight / 50);
      const fadeSpeed = 1;
      let cells = [];

      p5.setup = () => {
        p5.createCanvas(window.innerWidth, window.innerHeight);

        for (let r = 0; r < rows; r++) {
          cells[r] = [];
          for (let c = 0; c < columns; c++) {
            cells[r][c] = [p5.random(0, 255), 221, 255];
            if (p5.random() <= 0.5) {
              // animated cell
              if (p5.random() <= 0.5) {
                cells[r][c].push(0);
              } else {
                cells[r][c].push(1);
              }
            } else {
              // not animated cell
              cells[r][c].push(2);
            }
          }
        }
      };

      p5.draw = () => {
        const cellWidth = p5.width / columns;
        const cellHeight = p5.height / rows;

        //p5.background("black");

        // if (p5.mouseX > 0 && p5.mouseX < p5.width && p5.mouseY > 0 && p5.mouseY < p5.height) {
        //   const mouseR = p5.floor(rows * (p5.mouseY / p5.height));
        //   const mouseC = p5.floor(columns * (p5.mouseX / p5.width));
        //   cells[mouseR][mouseC] = [255,255,255];
        // }

        for (let r = 0; r < rows; r++) {
          for (let c = 0; c < columns; c++) {
            
            // if cell is animated, color and change direction if necessairy
            if (cells[r][c][3] == 1 || cells[r][c][3] == 0) {
              if (cells[r][c][0] > 1 && cells[r][c][3] == 0) {
                cells[r][c][0] -= fadeSpeed;
              } else if (cells[r][c][0] < 254 && cells[r][c][3] == 1) {
                cells[r][c][0] += fadeSpeed;
              } else if (p5.floor(cells[r][c][0]) == 0) {
                cells[r][c][3] = 1;
                cells[r][c][0] += fadeSpeed;
              } else if (p5.ceil(cells[r][c][0]) == 255) {
                cells[r][c][3] = 0;
                cells[r][c][0] -= fadeSpeed;
              }
            }

            const y = p5.height * (r / rows);
            const x = p5.width * (c / columns);

            p5.fill(cells[r][c][0], cells[r][c][1], cells[r][c][2]);
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
