<script setup lang="ts">
import { onMounted, onBeforeUnmount} from 'vue';


function drumPress(drum:string){
    let audio;
    switch(drum) {
        case 'kick':
            audio = new Audio('https://audio.jukehost.co.uk/zOjwMviukyheu1q6AMilmSO3xKvqjaSp');
            break;
        case 'snare':
            audio = new Audio('https://audio.jukehost.co.uk/CgDXWh7vgiHo0jpFwa59x5I5YONOqChF');
            break;
        case 'cHat':
            audio = new Audio('https://audio.jukehost.co.uk/5W2ihY2LTpzBwCPiEk2z1HftExZ84VuD');
            break;
        case 'oHat':
            audio = new Audio('https://audio.jukehost.co.uk/lVYBZ714Yh4s3tXqSGo3ruTBgxvMAeeB');
            break;
        case 'hiTom':
            audio = new Audio('https://audio.jukehost.co.uk/4GdQAmYkn15vUDgTewpoe3n3iEFCyrm4');
            break;
        case 'midTom':
            audio = new Audio('https://audio.jukehost.co.uk/6378XALUjrm3RKrykCi8cIqO79DiBih9');
            break;
        case 'lowTom':
            audio = new Audio('https://audio.jukehost.co.uk/XDLPKPL6m3WixAeqDRhDFicsWoDMA97R');
            break;
        default:
            console.log('Unknown drum type')
            return;
    }
    audio.play();
}


let handleKeyPress = (event:KeyboardEvent) => {
    switch(event.key) {
        case 'q':
            drumPress('kick');
            break;
        case 'w':
            drumPress('snare');
            break;
        case 'e':
            drumPress('cHat');
            break;
        case 'r':
            drumPress('oHat');
            break;
        case 't':
            drumPress('hiTom');
            break;
        case 'y':
            drumPress('midTom');
            break;
        case 'u':
            drumPress('lowTom');
            break;
        default:
            console.log('Unknown key')
    }
}

onMounted(() => {
    window.addEventListener('keydown', handleKeyPress);
});

onBeforeUnmount(() => {
    window.removeEventListener('keydown', handleKeyPress);
});

</script>

<template>

    <header>
        <nav>
            <a :href="'https://github.com/ThomasLam2142/vue-drumkit'" target="_blank">
                Github
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                </svg>
            </a>
        </nav>
    </header>
    <h1>    
        Drum Kit
    </h1>

    <h5>
        Press the buttons or the coresponding keys to play the drums
    </h5>

    <h6>
        Sounds will lag first time they are played due to loading
    </h6>    

    <div>
        <button @click="drumPress('kick')">Kick ('Q')</button> 
        <button @click="drumPress('snare')">Snare ('W')</button>
        <button @click="drumPress('cHat')">cHat ('E')</button>
        <button @click="drumPress('oHat')">oHat ('R')</button>
        <button @click="drumPress('hiTom')">hiTom ('T')</button>
        <button @click="drumPress('midTom')">midTom ('Y')</button>
        <button @click="drumPress('lowTom')">lowTom ('U')</button>
    </div>


</template>

<style scoped>

button{
    margin: 2em;
}

</style>
