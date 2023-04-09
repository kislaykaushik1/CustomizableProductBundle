# CustomizableProductBundle
Developed a Customizable Product Bundle for Chocolate brand

First, we define the maximum number of chocolates that can be selected and the price per chocolate.

We then select the relevant HTML elements and set up an empty array to keep track of the selected chocolates.

The updatePrice function calculates the total price of the selected chocolates and updates the price span element.

The handleCheckboxClick function is called whenever a checkbox is clicked. If the checkbox is checked and the maximum number of chocolates has not been reached, the chocolate is added to the selectedChocolates array and the price is updated. If the checkbox is unchecked, the chocolate is removed from the array and the price is updated again.

The handleFormSubmit function is called when the form is submitted. If no chocolates have been selected, an alert is displayed. Otherwise, an alert is displayed with the list of selected chocolates, and the form and selectedChocolates array are reset.

Finally, we add event listeners to the checkboxes and form submit button, calling the relevant functions as necessary. 




The CSS code is responsible for styling the HTML elements. Here's what each section of the code does:


.custom-pack - Defines the style for the custom pack container, which has a width of 80% and is centered using the margin property.

.chocolates - Defines the style for the chocolate options container, which uses flexbox and wraps the items to the next line when there's not enough space.

.chocolates input[type=checkbox] - Defines the style for the checkboxes, which are hidden using the display: none; property.

.chocolates label - Defines the style for the label associated with each checkbox, which has a width of 30%, a border, padding, and text alignment.

.chocolates label:hover - Defines the style for the labels when hovered by the user, which changes the background color to light gray.

.chocolates input[type=checkbox]:checked + label - Defines the style for the label associated with the checked checkboxes, which changes the background color to gray.

.total-price - Defines the style for the total price container, which adds margin to the top of the container.

button[type=submit] - Defines the style for the "Add to Cart" button, which has a green background color, white text, padding, and a border radius.

button[type=submit]:hover - Defines the style for the "Add to Cart" button when hovered by the user, which changes the background color to a darker green.




JS Code Explanation :


const checkboxes = document.querySelectorAll('input[type=checkbox]'); - Selects all checkboxes using the querySelectorAll() method and stores them in a constant named checkboxes.

const priceSpan = document.getElementById('price'); - Selects the price span using the getElementById() method and stores it in a constant named priceSpan.

const maxChocolates = 8; - Defines the maximum number of chocolates that can be selected and stores it in a constant named maxChocolates.

checkboxes.forEach((checkbox) => { - Loops through each checkbox using the forEach() method and adds an event listener that listens for a change in the checkbox status.

checkbox.addEventListener('change', () => { - Adds an event listener that listens for a change in the checkbox status.

let totalPrice = 0; - Initializes the total price of the selected chocolates to zero.

let selectedChocolates = 0; - Initializes the number of selected chocolates to zero.

checkboxes.forEach((checkbox) => { - Loops through each checkbox using the forEach() method and checks if the checkbox is selected or not.

if (checkbox.checked) { - Checks if the checkbox is selected or not.

selectedChocolates++; - Increments the number of selected chocolates.

totalPrice += 2.50; - Adds the price of the selected chocolate to the total price.

if (selectedChocolates > maxChocolates) { - Checks if the number of selected chocolates exceeds the maximum number allowed.

checkbox.checked = false; - Resets the checkbox to unchecked if the number of selected chocolates exceeds the maximum allowed.

alert('You can only select a maximum of 8 chocolates!'); - Displays an alert message to the user if the number of selected chocolates exceeds the maximum allowed.

priceSpan.innerText = totalPrice.toFixed(2); - Updates the price span with the total price of the selected chocolates, rounded to two decimal places.

const form = document.getElementById('form'); - Selects the form element using the getElementById() method and stores it in a constant named form.

form.addEventListener('submit', (event) => { - Adds an event listener that listens for the form submission event.

event.preventDefault(); - Prevents the form from submitting and reloading the page.

if (selectedChocolates === 0) { - Checks if the user has selected at least one chocolate.

alert('Please select at least one chocolate!'); - Displays an alert message to the user if they haven't selected any chocolates.


alert(You have added ${selectedChocolates} chocolates to your cart for a total of $${totalPrice.toFixed(2)}.); - Displays an alert message to the user showing the number of selected chocolates and the total price.

form.reset(); - Resets the form to its initial state.
