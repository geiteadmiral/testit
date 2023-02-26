<script>
    import Gibby from "./gibby.svelte";
    import Aboutus from "./aboutus.svelte";
    import Images from "./images.svelte";
    import Boxes from "./boxes.svelte";
    import Faq from "./FAQ.svelte";


    //overganger
    import Typewriter from 'svelte-typewriter';     //npm i -D svelte-typewriter
    import { concurrent } from 'svelte-typewriter'
    import { onMount } from "svelte";
    import { fly } from 'svelte/transition';
    import { fade } from "svelte/transition";
    import { slide } from "svelte/transition";


    let loadTransition = false
    onMount(() => loadTransition = true);

    
</script>

<div class = "mainpage" id ="home">
    <div class = "front">
        <div>
            {#if loadTransition}
            <h1 use:concurrent={{ interval: 30 }}>Insert a very cool title</h1>
            <h3 in:fly="{{ y: 200, duration: 2000, delay: 1000 }}">
                Radical Omnist Party
            </h3> 
            <p in:fade="{{duration: 2000, delay: 2000 }}">Wouldn’t it be great to create a world where everyone gets their opinion heard (while also being completely silenced)? Where all political ideologies , no matter how extreme or absurd, can combine into a perfect utopia (or dystopia)? Radical Omnist Party, or ROMP for short, offers the perfect solution to all silly world conflicts (and creates new and larger ones), by believing in and enforcing everything. </p>
            <button in:slide="{{delay: 3000}}">
                <a href="/learnmore">Learn more</a>
            </button>
            {/if}

        </div>
        {#if loadTransition}
        <div in:fade="{{duration: 2000, delay: 2000 }}">
            <Gibby></Gibby>
        </div>
        {/if}
    </div>
    <div id = "aboutus">
        <Aboutus></Aboutus>
    </div>
    <div id = "values">
        <Boxes></Boxes>
    </div>
    <div id = "logistics">
        <Images></Images>
    </div>
    <div id = "faq">
        <Faq></Faq>
    </div>


</div>

<style>


.mainpage {
    margin-left: 10vw;
}

.front {
    padding-left: 7vw;
    padding-right: 5vw;
    padding-top: 20vh;
    display: grid;
    grid-template-columns: 5fr 2fr;
    height: 100vh;
}

.front p {
    font-size: 2vh;
}

.front button {
    margin-top: 3vh;
    border: 0.2vw rgb(98, 157, 141) solid;

    box-shadow: none;
    background: none;
    font-size: 4vh;
    padding: 1.5vh;
}

.front a {
    color: rgb(98, 157, 141);
    text-decoration: none;
}






</style>