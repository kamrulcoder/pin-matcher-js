# Pin Mathcer javascript Practice Project 

![stack Overflow](https://i.ibb.co/YjZP3p5/Screenshot-1.png)

> ## Our project is very simple and straightforward. I will be able to learn a lot of new things through this project.

### At the beginning we need to generate the pin on the left side of the project. The codes to be written are given below -

### Html Code ... 
```HTML
    <div class="col-md-6">
        <div class="pin-generator half-width">
            <input id="display-pin" class="form-control" type="text">
            <button  class="generate-btn"  id="generate-btn">Generate Pin</button>
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



