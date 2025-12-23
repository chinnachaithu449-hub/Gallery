# Ex.08 Design of Interactive Image Gallery
# Date:
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
<div class="gallery-container">
    <div class="gallery-item">
        <img src="gallery1.avif" alt="Image 1">
    </div>
    <div class="gallery-item">
        <img src="gallery2.jpg" alt="Image 2">
    </div>
    <div class="gallery-item">
        <img src="gallery3.jpg" alt="Image 3">
    </div>
    <div class="gallery-item">
        <img src="gallery4.jpg" alt="Image 4">
    </div>
    <div class="gallery-item">
        <img src="gallery5.jpg" alt="Image 5">
    </div>
</div>

<div class="slider" id="slider">
    <button class="close-btn" id="close-btn">&#10006;</button>
    <span class="arrow left" id="prev">&#10094;</span>
    <img src="" alt="Slider Image" id="slider-img">
    <span class="arrow right" id="next">&#10095;</span>
</div>

<script>
    const images = document.querySelectorAll('.gallery-item img');
    const slider = document.getElementById('slider');
    const sliderImg = document.getElementById('slider-img');
    const prevBtn = document.getElementById('prev');
    const nextBtn = document.getElementById('next');
    const closeBtn = document.getElementById('close-btn');

    let currentIndex = 0;

    images.forEach((image, index) => {
        image.addEventListener('click', () => {
            slider.style.display = 'block';
            sliderImg.src = image.src;
            currentIndex = index;
            closeBtn.style.display = 'block';
            document.body.style.overflow = 'hidden';
        });
    });

    prevBtn.addEventListener('click', (e) => {
        e.stopPropagation();
        currentIndex = (currentIndex - 1 + images.length) % images.length;
        sliderImg.src = images[currentIndex].src;
    });

    nextBtn.addEventListener('click', (e) => {
        e.stopPropagation();
        currentIndex = (currentIndex + 1) % images.length;
        sliderImg.src = images[currentIndex].src;
    });

    closeBtn.addEventListener('click', () => {
        slider.style.display = 'none';
        closeBtn.style.display = 'none';
        document.body.style.overflow = 'auto';
    });

    slider.addEventListener('click', () => {
        slider.style.display = 'none';
        closeBtn.style.display = 'none';
        document.body.style.overflow = 'auto';
    });
</script>
# OUTPUT:
<img width="829" height="441" alt="image" src="https://github.com/user-attachments/assets/bd838059-913a-4e4c-9239-2e2ed056e128" />

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
