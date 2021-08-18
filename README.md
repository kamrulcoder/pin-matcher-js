# Pin Mathcer javascript Practice Project 

![stack Overflow](https://i.ibb.co/YjZP3p5/Screenshot-1.png)

> ## Our project is very simple and straightforward. I will be able to learn a lot of new things through this project.

### At the beginning we need to generate the pin on the left side of the project. The codes to be written are given below -

### Html Code ... 
```HTML
    <div class="col-md-6">
        <div class="pin-generator half-width">
            <input id="display-pin" class="form-control" type="text">
            <button onclick="generatePin()"  class="generate-btn"  id="generate-btn">Generate Pin</button>
        </div>
    </div>
```
### Get Pin Generator  Function Create 
```javascript
function getPin() {
    // create reandom pin method 
    const pin = Math.round(Math.random() * 10000);

    // Convert PIN number to string
    const pinString = pin + '';

    // Here to find the length of the string through the condition
    if (pinString.length == 4) {
        // If the conditions here are true then it will return
        return pin;
    }
    else {
       // If the conditions here are false  then it will return  recursive function 
        return getPin();
    }
}

// The function of this function is to generate a pin at the input value
function generatePin() {

    // Here that getPin() has been called
    const pin = getPin();

     // Here that display-pin input  has been pass value 
    document.getElementById('display-pin').value = pin;
}

```
### Now the result will come


![stack Overflow](https://i.ibb.co/YTs7JxL/Screenshot-2.png)

> # Now our second step.

### Html Code ... 
```HTML
<div class="col-md-6">
    <div class="input-section half-width">
        <input id="typed-numbers" class="form-control" type="text">
        <div class="numbers">
            <div id="key-pad" class="calc-body">
                <div class="calc-button-row">
                    <div class="button">7</div>
                    <div class="button">8</div>
                    <div class="button">9</div>
                </div>
                <div class="calc-button-row">
                    <div class="button">4</div>
                    <div class="button">5</div>
                    <div class="button">6</div>
                </div>
                <div class="calc-button-row">
                    <div class="button">1</div>
                    <div class="button">2</div>
                    <div class="button">3</div>
                </div>
                <div class="calc-button-row">
                    <div class="button">&lt;</div>
                    <div class="button">0</div>
                    <div class="button">C</div>
                </div>
                <div>
                    <button onclick="verifyPin()" type="submit" class="submit-btn">Submit</button>
                    <p class="action-left">3 try left</p>
                </div>
            </div>
        </div>
    </div>
</div>
<div class="notify-section">
    <p id="notify-fail" class="notify">❌ Pin Didn't Match, Please try again</p>
    <p id="notify-success" class="notify">✅ Pin Matched... Secret door is opening for you</p>
</div>
```

## javascript Code Here ...


```javascript 
document.getElementById('key-pad').addEventListener('click', function (event) {

    // get input by target keypad text 
    const number = event.target.innerText;

    // declaire by type numbers 
    const calcInput = document.getElementById('typed-numbers');

    //  if here value not a number the check  condtion 
    if (isNaN(number)) {
        if (number == 'C') {
            calcInput.value = '';
        }
    }
    else {
        const previousNumber = calcInput.value;
        const newNumber = previousNumber + number;
        calcInput.value = newNumber;
    }
});


// Here verify pin  function create 

function verifyPin() {
    const pin = document.getElementById('display-pin').value;
    const typedNumbers = document.getElementById('typed-numbers').value;
    const successMessage = document.getElementById('notify-success');
    const failError = document.getElementById('notify-fail');
    if (pin == typedNumbers) {
        successMessage.style.display = 'block';
        failError.style.display = 'none';
    }
    else {
        successMessage.style.display = 'none';
        failError.style.display = 'block';
    }
}

```

> ###  At the end of the function, if the PIN generator and type input do not match here, we will see the wrong output and if true, the true output


![stack Overflow](https://i.ibb.co/K0tj6nX/Screenshot-4.png)
