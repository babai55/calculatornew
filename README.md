<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css"
    />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css"
    />

    <link rel="stylesheet" href="css/css.css" />
    <title>Calculator UI -Neumorphism</title>
  </head>
  <body>
    <div class="container">
      <div class="iphone-x">
        <div class="screen">
          <div class="notch">
            <div class="sound"></div>
            <div class="camera"></div>
          </div>
          <div class="time" id="time">
            <script>
              var timer = document.getElementById("time").innerHTML;
              var today = new Date();
              var time = today.getHours() + ":" + today.getMinutes();
              timer = document.write(time);
            </script>
          </div>
          <div class="battery">
            <i class="fa fa-battery-full"></i>
          </div>
          <div class="wifi">
            <i class="fa fa-wifi"></i>
          </div>

          <div class="top-nav"></div>

          <form class="calculator container">
            <input
              type="text"
              placeholder="0"
              name="displayResult"
              class="area"
            />

            <div class="key container" id="keyBoard">
              <div class="first-col"></div>

              <div class="second-col">
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="AC"
                    class="btn-work"
                    onclick="displayResult.value=' '"
                  >
                    AC
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="7"
                    onclick="calcNumbers(this.value)"
                  >
                    7
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="4"
                    onclick="calcNumbers(this.value)"
                  >
                    4
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="1"
                    onclick="calcNumbers(this.value)"
                  >
                    1
                  </button>
                </div>

                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="0"
                    onclick="calcNumbers(this.value)"
                  >
                    0
                  </button>
                </div>
              </div>

              <div class="third-col">
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="+/-"
                    onclick="makeNegative(displayResult.value)"
                    class="btn-work"
                  >
                    +/-
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="8"
                    onclick="calcNumbers(this.value)"
                  >
                    8
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="5"
                    onclick="calcNumbers(this.value)"
                  >
                    5
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="2"
                    onclick="calcNumbers(this.value)"
                  >
                    2
                  </button>
                </div>

                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="."
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    .
                  </button>
                </div>
              </div>

              <div class="fourth-col">
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="%"
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    <i class="fa fa-percent"></i>
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="9"
                    onclick="calcNumbers(this.value)"
                  >
                    9
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="6"
                    onclick="calcNumbers(this.value)"
                  >
                    6
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="3"
                    onclick="calcNumbers(this.value)"
                  >
                    3
                  </button>
                </div>

                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="+"
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    <i class="fas fa-plus"></i>
                  </button>
                </div>
              </div>

              <div class="fifth-col">
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="/"
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    <i class="fas fa-divide"></i>
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="*"
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    <i class="fas fa-times"></i>
                  </button>
                </div>
                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="-"
                    onclick="calcNumbers(this.value)"
                    class="btn-work"
                  >
                    <i class="fas fa-minus"></i>
                  </button>
                </div>

                <div class="button">
                  <button
                    type="button"
                    name=""
                    value="="
                    onclick="(displayResult.value.includes('%'))?percentage(displayResult.value):displayResult.value=eval(displayResult.value);"
                    class="btn-equal"
                  >
                    =
                  </button>
                </div>
              </div>

              <div class="menu"><i class="fa fa-bars"></i></div>
              <div class="home"><i class="fas fa-home"></i></div>
              <div class="back"><i class="fa fa-step-backward"></i></div>
            </div>
          </form>
        </div>
      </div>
    </div>

    <script>
      function calcNumbers(result) {
        document.querySelector(".area").value += result;
      }
      function percentage(result) {
        var result1 = String(result);
        if (result1.includes("%")) {
          var a, b, percent;
          var splitWord = [];
          splitWord = result1.split("%");
          a = Number(splitWord[0]);
          b = Number(splitWord[1]);
          percent = (a / 100) * b;
          document.querySelector(".area").value = percent;
        }
      }
      function makeNegative(result) {
        if (result.charAt(0) === "-") {
          document.querySelector(".area").value = result.replace("-", "");
        } else {
          document.querySelector(".area").value = "-" + result;
        }
      }
    </script>
  </body>
</html>
