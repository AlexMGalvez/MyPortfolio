<script>
export default {
  name: "App",
  mounted() {
    const script = function (p5) {
      var symbolSize = 26;
      var streams = [];

      p5.setup = () => {
        p5.createCanvas(window.innerWidth, window.innerHeight);
        p5.background(0);
        var x = 0;
        for (var i = 0; i <= p5.width / symbolSize; i++) {
          var stream = new Stream();
          stream.generateSymbols(x, p5.random(-1000, 0));
          streams.push(stream);
          x += symbolSize;
        }
        p5.textSize(symbolSize);
      };

      p5.draw = () => {
        p5.background(0, 150);
        streams.forEach(function (stream) {
          stream.render();
        });
      };

      function Symbol(x, y, speed, first) {
        this.x = x;
        this.y = y;
        this.value;
        this.speed = speed;
        this.switchInterval = p5.round(p5.random(2, 200));
        this.first = first;

        this.setToRandomSymbol = function () {
          if (p5.frameCount % this.switchInterval == 0) {
            this.value = String.fromCharCode(
              0x0030  + p5.round(p5.random(0, 1))
            );
          }
        };

        this.rain = function () {
          this.y = this.y >= p5.height ? 0 : (this.y += this.speed);
        };
      }

      function Stream() {
        this.symbols = [];
        this.totalSymbols = p5.round(p5.random(5, 30));
        this.speed = p5.random(5, 20);

        this.generateSymbols = function (x, y) {
          var first = p5.round(p5.random(0,1)) == 1;
          for (var i = 0; i <= this.totalSymbols; i++) {
            var symbol = new Symbol(x, y, this.speed, first);
            symbol.setToRandomSymbol();
            this.symbols.push(symbol);
            y -= symbolSize;
            first = false;
          }
        };

        this.render = function () {
          this.symbols.forEach(function (symbol) {
            if (symbol.first) {
                p5.fill(180, 255, 180);
            } else {
                p5.fill(158, 161, 142);
            }
            p5.text(symbol.value, symbol.x, symbol.y);
            symbol.rain();
            symbol.setToRandomSymbol();
          });
        };
      }
    };
    const P5 = require("p5");
    new P5(script);
  },
};
</script>

