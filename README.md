# Ex.08 Design of Interactive Image Gallery
## Date:7/5/2025

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>HARRY POTTER</h1>
    </header>
    <div class="gallery">
        <div class="gallery-item" onclick="openModal(this)">
            <img src="hh.jpg" >
        </div>
        <div class="gallery-item" onclick="openModal(this)">
            <img src="malfoy.jpeg"  >
        </div>
        <div class="gallery-item" onclick="openModal(this)">
            <img src="goldentrio.jpeg" >
        </div>
        <div class="gallery-item" onclick="openModal(this)">
            <img src="severus.jpeg" >
        </div>
        <div class="gallery-item" onclick="openModal(this)">
            <img src="cedric.jpeg" >
        </div>
    </div>

    <div id="modal" class="modal">
        <span class="close" onclick="closeModal()">&times;</span>
        <img class="modal-content" id="modalImage">
        <div id="caption"></div>
    </div>

    <script src="style.js"></script>
</body>
</html>
```
```
CSS
body{
    background-color:lightslategray ;  
    font-family: Arial, sans-serif;  
    margin: 0; 
    padding: 20px;  
    text-align: center;
    color:cornsilk;
};
img{
    align-content: center;
}
.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 16px;
    padding: 16px;
}

.gallery-item img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    cursor: pointer;
    transition: transform 0.3s ease;
}

.gallery-item img:hover {
    transform: scale(1.1);
}
#modalImage {
    transition: transform 0.5s ease-in-out;
    transform: scale(1); /* Default scale */
}

#modalImage.zoomed {
    transform: scale(2.5); /* Zoomed-in scale */
}

```
```
JAVASCRIPT
function openModal(element) {
    var modal = document.getElementById("modal");
    var modalImg = document.getElementById("modalImage");
    modal.style.display = "block";
    modalImg.src = element.querySelector("img").src;

    // Accessibility: Add focus to modal
    modal.setAttribute("aria-hidden", "false");

    // Add zoom effect
    modalImg.classList.add("zoomed");
}

function closeModal() {
    var modal = document.getElementById("modal");
    var modalImg = document.getElementById("modalImage");
    modal.style.display = "none";

    // Accessibility: Hide modal from screen readers
    modal.setAttribute("aria-hidden", "true");

    // Remove zoom effect
    modalImg.classList.remove("zoomed");
}

// Close modal when clicking outside the image
document.getElementById("modal").addEventListener("click", function (event) {
    if (event.target === this) {
        closeModal();
    }
});
```

## OUTPUT:
![Screenshot 2025-05-07 114521](https://github.com/user-attachments/assets/4bf7ef05-7b35-4a0e-b5d3-b83a3718f2de)
![Screenshot 2025-05-07 114545](https://github.com/user-attachments/assets/e954394e-4739-4a40-8274-ad1a485655fd)


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
