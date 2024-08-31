let count = 5
count = count + 1
console.log(count)


//----------------------------------------------------------------------------------------
// Create a function that increments the lapsCompleted variable with one
// Run it three times
let lapsCompleted = 0
function incrementLap() {
    lapsCompleted = lapsCompleted + 1
}
incrementLap()
incrementLap()
incrementLap()
console.log(lapsCompleted)


//--------------------------------------------------------------------------------------------------
// intialize the count as 0
// listen for clicks on the increment button
<button id="increment-btn" onclick="increment()">INCREMENT</button>
// increment the count variable when the button is clicked
// change the count-el in the HTML to reflect the new count

let countEl = document.getElementById("count-el")//pass in arguments
let count = 0

function increment() {
    count = count + 1
    countEl.innerText = count
}

//DOCUMENT OBJECT MODEL: how to use js to modify a website. The word document is of object datatype in js. taking html document turning it into js object. Model is representation. Js has a representaion or model of real objects in html doc through document keyword.
Document Object Model (DOM)
A programming interface for web documents that represents their structure and content as nodes and objects. The DOM is cross-platform and language-independent, and it allows programs to change the document's structure, style, and content. For example, the DOM can represent an HTML table as a tree structure, with each node containing an object that represents a part of the document. The DOM is essential for JavaScript, which without it would not have a model for web pages, HTML documents, and SVG documents.
//----------------------------------------------------------------------------------------------------------


// + in stings perpform concatenation
welcomeEl.innerText += "👋"

//-------------------------------------------------------------------------------------------------------------
// 1. Grab the save-el paragrah and store it in a variable called saveEl
let saveEl = document.getElementById("save-el")
function save() {
    let countStr = count + " - "
    // 2. Create a variable that contains both the count and the dash separator, i.e. "12 - "
    // 3. Render the variable in the saveEl using innerText
    saveEl.innerText += countStr
    // NB: Make sure to not delete the existing content of the paragraph
    console.log(count)
}


//--------------------------------------------------------------------------------------------------------------------------
//innerText fails to return hidden elements or shows only human readable elements 
Node. web text 


// Js saves info until refresh


//-------------------------------------------2nd-----------------------------------------------------------------------------------
== is less strict than =

let sumEl = document.querySelector("#sum-el")
'#' used here getting element by its collector


//---------------------------------------------------------------------------------------------
------ARRAYS--------------------------------
let featuredPosts = [
    "Check out my Netflix clone",        // 0 
    "Here's the code for my project",    // 1
    "I've just relaunched my portfolio"  // 2
]

console.log( featuredPosts.length )
messages.push("Yes")
messages.pop 

//------- for LOOP:------------------------------------------------------------------------------
//    START      FINISH(last not counted)  STEP SIZE
for ( let count = 1;  count < 11;  count += 1 )  {
    
    console.log(count)

}

//--------------------------------------------------------------------------------------
function getFastestRaceTime() {
    if (player1Time < player2Time) {
        console.log(player1Time)
    } else if (player2Time < player1Time) {
        console.log(player2Time)
    } else {
        console.log(player1Time)
    }
}

let fastestRace = getFastestRaceTime()

console.log(fastestRace)

O/P=> 102
      undefined (as now fastestRace has a function taht dosen't return anything)

//---------------------------------------------------------------------------------------------------
let randomNumber = Math.random()

What does Math.random() do?
It generates a random number between 0 and 1 (not inclusive of 1)
return Math.random()*13 // 0.000 - 12.999


let flooredNumber = Math.floor(12.999999999999)

What does Math.floor() do to positive numbers?
It removes the decimals


//-----------------------------------------------------------------------------------------------
let player = {
    name: "Per",
    chips: 200,
    sayHello: function() {
        console.log("Heisann!")
    }
}
playerEl.textContent = player.name + ": $" + player.chips
player.sayHello()


//------------------------------------------------------------------------
<input> is self closing tag 

box-sizing: border-box; (width includes padding)

//------------------------------------------------------------------------------------
inputBtn.addEventListener("click", function() {
    console.log("Button clicked from addEventListener")
})

//-----------------------------------------------------------------------------------
Both let and const are used to initialise elements but const can't be reassigned.
If possible, use const. If not, use let.

//--------------------------------------------------------------------------------------------
myLeads.push(inputEl.value)

ulEl.innerHTML += "<li>" + myLeads[i] + "</li>"
                
                OR

for (let i = 0; i < myLeads.length; i++) {
    // ulEl.innerHTML += "<li>" + myLeads[i] + "</li>"
    // create element
    // set text content
    // append to ul
    const li = document.createElement("li")
    li.textContent = myLeads[i]
    ulEl.append(li)
}
                OR

// 1. Create a variable, listItems, to hold all the HTML for the list items
// Assign it to an empty string to begin with
let listItems = ""
for (let i = 0; i < myLeads.length; i++) {
    // 2. Add the item to the listItems variable instead of the ulEl.innerHTML
    listItems += "<li>" + myLeads[i] + "</li>"
}
// 3. Render the listItems inside the unordered list using ulEl.innerHTML
ulEl.innerHTML = listItems


//-------------------------------------------------------------------------------------------------------------
myLeads.push(inputEl.value)
    // Clear out the input field
    inputEl.value = ""  (clears the value here the input box)


//---------template strings/literals------------------------------------------------------------------------------

    const recipient = "James"
    // Refactor the email string to use template strings
    const email = `Hey ${recipient}! How is it going? Cheers Per`
    console.log(email)


//-------------JSON-------------------------------------------------------------------------------------
JavaScript Object Notation 
Used for storing and accessing objects from server to client
manifest,js - used for telling chrome

Local Storage - used for resisiting data after refresh

//localStorage.setItem(key, value)
// localStorage.getItem(key)
// localStorage.clear()


localStorage only supports strings. Use JSON.stringify() and JSON.parse().

//....
var names = [];
names[0] = prompt("New member name?");
localStorage.setItem("names", JSON.stringify(names));

var storedNames = JSON.parse(localStorage.getItem("names"));

//...
let myLeads = `["www.awesomelead.com"]`

myLeads = JSON.parse(myLeads)

//.......
let myLeads = `["www.awesomelead.com"]`

// 1. Turn the myLeads string into an array
myLeads = JSON.parse(myLeads)
// 2. Push a new value to the array
myLeads.push("www.lead2.com")
// 3. Turn the array into a string again
myLeads = JSON.stringify(myLeads)
// 4. Console.log the string using typeof to verify that it's a string
console.log(typeof myLeads)

//......
let leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )

//......
let currentViewers = {}
console.log(currentViewers.randomKey) ==> undefined

//...........
// 1. Check if leadsFromLocalStorage is truthy
// 2. If so, set myLeads to its value and call renderLeads()

if (leadsFromLocalStorage) {
    myLeads = leadsFromLocalStorage
    renderLeads()
}

//.......
deleteBtn.addEventListener("dblclick", function() {
    console.log("double clicked!")
    localStorage.clear()
    myLeads = []
    renderLeads()
})

//........
const totalPrice = 420.69235632455
btn.textContent = `Buy €${ Number(totalPrice).toFixed(2) }` (changing string to number)



