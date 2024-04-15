<DOCTYPE html>
    <html lang="en">
          <head>
              <link rel="stylesheet" heref="https://pyscript.net/latest/pyscript.css" />
              <script defer src="https:/pyscript.net/latest/pyscript.js"></script>
              <style>
                   label{
                        display:block;
                   }
              </style>  
          </head>
          <body>
<py-config>
    packages = ['numpy']
<py-script>
    import numpy as np
    selection = np.random.randint(0,100,1)[0]
</-script>
<form>
    <label for="guess">Guess:</label><input name="guess" id="guess">
    <button type="button" id="submit">Check Guess</button>
    <label for="result">Result:</label><div name="result" id="result"></div>
</form>
<py-script>
    from pyscript import when
    @when("click", selection="#submit")
    def check_guess(): 
        user_guess = int(Element("guess").value)
        result = Element("result")
        if user_guess == selection:
           result.write("Try again! Your guess was too low.")
</py-script>

