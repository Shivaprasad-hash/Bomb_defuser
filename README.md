<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous" />
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
    <style>
        @import url("https://fonts.googleapis.com/css2?family=Bree+Serif&family=Monoton&family=Open+Sans:wght@400;700&family=Playfair+Display+SC:wght@400;700&family=Playfair+Display:wght@400;700&family=Roboto:wght@400;700&family=Source+Sans+Pro:wght@400;700&family=Work+Sans:wght@400;700&display=swap");
  
  .timer-container {
      text-align: center;
      background-color: #00bafc;
      height: 100vh;
      padding: 20px;
  }
  
  .timer-display {
      color: white;
      font-size: 50px;
  }
  
  .user-input {
      text-align: center;
      border-width: 0px;
      border-radius: 4px;
      padding: 6px;
  }
  
  .bomb-image {
      width: 150px;
      margin-top: 40px;
  }
    </style>
    <script>
  let defuser = document.getElementById("defuser");
let timer = document.getElementById("timer");

let counter = parseInt(timer.textContent);

let intervalId = setInterval(function() {
    timer.textContent = counter;
    counter -= 1;
    if (counter < 0) {
        clearInterval(intervalId);
        timer.textContent = "BOOM";
    }
}, 1000);

defuser.addEventListener("keydown", function(event) {
    if (event.key === "Enter" && defuser.value === "defuse" && intervalId > 0) {
        timer.textContent = "You did it!!";
        clearInterval(intervalId);
    }
})
</script>
</head>

<body>
    <div class="timer-container">
        <input type="text" class="user-input" id="defuser" />
        <br />
        <img src="https://d1tgh8fmlzexmh.cloudfront.net/ccbp-dynamic-webapps/time-bomb-img.png" class="bomb-image" />
        <p class="timer-display" id="timer">10</p>
    </div>
</body>

</html>
