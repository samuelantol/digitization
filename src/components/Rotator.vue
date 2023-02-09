<template>
    <h2>3D sken</h2>
    <div class="sketchfab-container">
        <div class="sketchfab-embed-wrapper">
            <span class="circle"></span>
            <!-- <iframe class="embeded-frame" title="Shod egg (1911) / Vajíčko zdobené okúvaním"
                frameborder="0" allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered web-share
                src="https://sketchfab.com/models/ce77b41d39b344749ae6277480d5401a/embed?autostart=1&camera=0&transparent=1&ui_animations=0&ui_infos=0&ui_stop=0&ui_inspector=0&ui_ar=0&ui_help=0&ui_settings=0&ui_vr=0&ui_fullscreen=0&ui_annotations=0&scrollwheel=0">
            </iframe> -->
            <iframe class="embeded-frame" title="Plastika-Svätý Matúš."
                frameborder="0" allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered web-share
                src="https://sketchfab.com/models/9984d4d7bb284bda8a12268ab90d42ea/embed?autostart=1&transparent=1&scrollwheel=0">
            </iframe>
        </div>
    </div>
</template>

<script>

</script>

<style>
.sketchfab-container {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: center;
    position: absolute;

    width: 95vw;
    max-width: 1280px;
    height: fit-content;
}
.sketchfab-embed-wrapper {
    width: 80vw;
    height: 80vw;
    max-width: 700px;
    max-height: 700px;
    
    display: inline-block;
    /* justify-content: center; */
}
.embeded-frame{
    width: 100%;
    height: 100%;
    
}
.circle {
    height: 60vw;
    width: 60vw;
    max-height: 500px;
    max-width: 500px;

    position: absolute;
    left:0;
    right:0;
    top:0;
    bottom: 0;
    margin: auto;
    z-index: -10;

    background-color: none;
    border: 10px dashed #00ff00;
    border-radius: 50%;
}
</style>