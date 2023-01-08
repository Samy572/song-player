<template>

    <div class="player">
        <i class='fa-regular fa-circle-play'></i>
        <input class="range" type="range" id="seek-bar" value="0" >
        <audio src="../song/clean-bandit-rather-be-ft-jess-glynne-official-video.mp3"></audio>
    </div>

</template>

<script lang ="ts">
import { products } from '@/interfaces/musiques';
export default {
    setup(){
        
        const audio = new Audio(products.song);
        function play (){
            audio.play();
        }

    }
}

</script>

<style scoped lang ="scss">

.player{
    position:fixed;
    left:50%;
    transform: translateX(-50%);
    width:80%;
    bottom: 3%;
    box-shadow: 3px 3px 5px black;
    background :linear-gradient(to bottom,#222,#666);
    opacity: 0.5;
    height: 70px;
    border-radius: 25px;
    display:flex;
    align-items: center;
}



i{
    margin-left: 2%;
    border-radius: 50%;
    align-items: center;
    font-size: 2.7em;
    cursor: pointer;
    box-shadow: 3px 3px 5px black;
    color:darkgrey;
}

.range{
    width:80%;
    height:3px;
    position:absolute;
    left:10%;
}

</style>