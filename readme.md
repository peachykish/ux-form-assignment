# Kenzie UI Engineering Program - Practice assignment for forms

Recreate the website as shown in the screenshots.

Do not modify base.css.
But go look inside base.css, and take note of what that css is doing.  

![alt text](https://github.com/KenzieAcademy/ux-form-assignment-rubric/blob/master/screenshots/MainLayout.png?raw=true)

![alt text](https://github.com/KenzieAcademy/ux-form-assignment-rubric/blob/master/screenshots/SelectList.png?raw=true)

![alt text](https://github.com/KenzieAcademy/ux-form-assignment-rubric/blob/master/screenshots/DatePicker.png?raw=true)

![alt text](https://github.com/KenzieAcademy/ux-form-assignment-rubric/blob/master/screenshots/FormValidation.png?raw=true)

![alt text](https://github.com/KenzieAcademy/ux-form-assignment-rubric/blob/master/screenshots/MobileView.png?raw=true)

# Design Specification

* The crossover point between mobile and web should be 767px.
* The font color is #fff
* The box shadow applied to the card is as follows:
```
-webkit-box-shadow: 0px 8px 20px 0px rgba(0, 0, 0, 0.15);
-moz-box-shadow: 0px 8px 20px 0px rgba(0, 0, 0, 0.15);
box-shadow: 0px 8px 20px 0px rgba(0, 0, 0, 0.15);
```




## A Hint about custom select lists.

To recreate the select list, we need to style it and remove the borders.
That is done by adding 
```
select {
  appearance: none;
  -webkit-appearance: none;
}
```

However, that removes the down arrow!  
So we need to add our own down arrow.

One trick to doing this is to create an :after element.
It can look like this:

```
<div class="selectWrapper">
    <select> options... </select>
</div>

.selectWrapper {
    position: relative;
} 
.selectWrapper:after {
    content: '>';
    font: 17px "Consolas", monospace;
    -webkit-transform: rotate(90deg);
    -moz-transform: rotate(90deg);
    -ms-transform: rotate(90deg);
    transform: rotate(90deg);
    position: absolute;
    pointer-events: none;

    right: some spacing...
    bottom: some spacing...
    color: your font color...
}
```

This creates an absolutely positioned element, filled with the > character rotated 90 degrees 
to make an arrow.
Use this on your select list to recreate an arrow.



## A Hint on the background

We haven't covered creating gradients in CSS yet, so you can use the following code
```
background: -webkit-gradient(linear, left bottom, left top, from(#fbc2eb), to(#a18cd1));
background: -webkit-linear-gradient(bottom, #fbc2eb 0%, #a18cd1 100%);
background: -moz-linear-gradient(bottom, #fbc2eb 0%, #a18cd1 100%);
background: -o-linear-gradient(bottom, #fbc2eb 0%, #a18cd1 100%);
background: linear-gradient(to top, #fbc2eb 0%, #a18cd1 100%);
```



## A Hint on placeholder text

To modify the color of the placeholder text for input elements, you need to use the following
selectors:
```
Chrome and Other Modern 
The opacity is for firefox
input::placeholder {
  color: #ccc;
  opacity: 1; 
}

For Internet Explorer 10-11 
input:-ms-input-placeholder {
   
   color: #ccc;
}

For Internet Explorer 10-11 
input:-ms-input-placeholder {  
  color: #ccc;
}
```
