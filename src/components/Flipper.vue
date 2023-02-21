<template>
    <h2> <button @click='selectTab(0)' :class="{selected: isSelected(0)}">Sken rukopisov</button> /
        <button @click='selectTab(1)' :class="{selected: isSelected(1)}">Sken viazaných kníh</button> /
        <button @click='selectTab(2)' :class="{selected: isSelected(2)}">Sken viazaných fotoalbumov</button> /
        <button @click='selectTab(3)' :class="{selected: isSelected(3)}">Sken architektonických výkresov</button> /
        <button @click='selectTab(4)' :class="{selected: isSelected(4)}">Sken obrazov s rôznym nasvietením</button> /
        <button @click='selectTab(5)' :class="{selected: isSelected(5)}">Sken textílií</button> </h2>

    <div class="flip-container">

        <div class="flip-button-left">
            <svg slot="handle" width="57" height="36" viewBox="0 0 57 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21.4,32.3L7.2,18.1L21.4,4" stroke="#00FF00" stroke-width="10" />
            </svg>
        </div>

        <img class="page" src='https://images.unsplash.com/photo-1542216516-dc8bc35b0c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2804&q=80'>

        <div class="flip-button-right">
            <svg slot="handle" width="57" height="36" viewBox="0 0 57 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M35.4,4l14.1,14.1L35.4,32.3" stroke="#00FF00" stroke-width="10" />
            </svg>
        </div>

    </div>

    <div class="container">
        <div v-for="image in imagesLarge">
            <div class="mySlides">
                <div class="numbertext">{{ image.index+1 }} / 6</div>
                <img :class="{ showed: isSelectedImage(image.index) }" :src="image.src" style="width:100%">
            </div>
        </div>
            
        <a class="prev" @click="plusSlides(-1)">❮</a>
        <a class="next" @click="plusSlides(1)">❯</a>

        <div class="row">
            <div v-for="image in imagesSmall">
                <div class="column">
                    <img class="demo cursor" :class="{ active: isSelectedImage(image.index) }"
                        :src="image.src" style="width:100%" @click="currentSlide(image.index)" alt="The Woods">
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const selected = ref(0);

    function selectTab (index) {
        selected.value = index;
    }

    function isSelected (index) {
        if (selected.value === index) {
            return true;
        } else {
            return false;
        }
    }

    function isSelectedImage (index) {
        if (selectedSlide.value === index) {
            return true;
        } else {
            return false;
        }
    }

    //

    const imagesSmall = ref ([
        {index: 0, src: "https://www.w3schools.com/howto/img_woods.jpg"},
        {index: 1, src: "https://www.w3schools.com/howto/img_5terre.jpg"},
        {index: 2, src: "https://www.w3schools.com/howto/img_mountains.jpg"},
        {index: 3, src: "https://www.w3schools.com/howto/img_lights.jpg"},
        {index: 4, src: "https://www.w3schools.com/howto/img_nature.jpg"},
        {index: 5, src: "https://www.w3schools.com/howto/img_snow.jpg"}
    ]);
    const imagesLarge = ref ([
        {index: 0, src: "https://www.w3schools.com/howto/img_woods_wide.jpg"},
        {index: 1, src: "https://www.w3schools.com/howto/img_5terre_wide.jpg"},
        {index: 2, src: "https://www.w3schools.com/howto/img_mountains_wide.jpg"},
        {index: 3, src: "https://www.w3schools.com/howto/img_lights_wide.jpg"},
        {index: 4, src: "https://www.w3schools.com/howto/img_nature_wide.jpg"},
        {index: 5, src: "https://www.w3schools.com/howto/img_snow_wide.jpg"}
    ]);

    const selectedSlide = ref(0);

    let slideIndex = 1;
    showSlides(slideIndex);

    function plusSlides(n) {
        showSlides(slideIndex += n);
    }

    function currentSlide(n) {
        showSlides(slideIndex = n);
    }

    function showSlides(n) {
        let i;
        let slides = imagesLarge.value; //document.getElementsByClassName("mySlides");
        let dots = imagesSmall.value; //document.getElementsByClassName("demo");
        //let captionText = document.getElementById("caption");

        if (n > slides.length) {
            slideIndex = 1
        }
        if (n < 1) {
            slideIndex = slides.length
        }

        // for (i = 0; i < slides.length; i++) {
        //     slides[i].style.display = "none";
        // }
        // for (i = 0; i < dots.length; i++) {
        //     dots[i].className = dots[i].className.replace(" active", "");
        // }

        // slides[slideIndex-1].style.display = "block";
        //dots[slideIndex-1].className += " active";
        //captionText.innerHTML = dots[slideIndex-1].alt;
    }
</script>

<style>
.flip-container {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: center;

    width: 100%;
    height: fit-content;
}
.page {
    display: inline-block;
    box-sizing: border-box;
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    width: 50vw;
    max-width: 500px;
    height: auto;
    border-left: 10px dashed #00ff00;
    border-right: 10px dashed #00ff00;
}
.flip-button {
    display: inline-block;
    width: 5%;
    height: 100%;
}
.selected {
    color: #000000;
}



* {
  box-sizing: border-box;
}

img {
  vertical-align: middle;
}

/* Position the image container (needed to position the left and right arrows) */
.container {
  position: relative;
}

/* Hide the images by default */
.mySlides {
  display: none;
}

/* Add a pointer when hovering over the thumbnail images */
.cursor {
  cursor: pointer;
}

/* Next & previous buttons */
.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 40%;
  width: auto;
  padding: 16px;
  margin-top: -50px;
  color: white;
  font-weight: bold;
  font-size: 20px;
  border-radius: 0 3px 3px 0;
  user-select: none;
  -webkit-user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* Container for image text */
.caption-container {
  text-align: center;
  background-color: #222;
  padding: 2px 16px;
  color: white;
}

.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Six columns side by side */
.column {
  float: left;
  width: 16.66%;
}

/* Add a transparency effect for thumnbail images */
.demo {
  opacity: 0.6;
}

.active,
.demo:hover {
  opacity: 1;
}

.showed {
    display: block;
}
</style>