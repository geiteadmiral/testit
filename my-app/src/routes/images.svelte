<script>
    import {fade} from 'svelte/transition'
	
	const imageSlider = [
		'anarchy.png',
		'robot.png',
        'placeholder4.png'
	]

    const title = [
        'Anarchism and Totalitarianism',
        'Transhumanism and Primitivism',
        'Communism and Capitalism'
    ]

    const content = [
        'To create a totalitarian government, as well as an anarchist lack of, we plan on combining them both. The best way to do this is by creating a strong and totalitarian state, whose only purpose is to stop the creation of hierarchies or any other forms of governing power. While this is definitely doable, us in ROMP have some concerns regarding the high level of totalitarianism in this solution, something that goes against the anarchy we wish to create. Therefore, we want the government to consist purely of Artificial Intelligence, resulting in no human hierarchies. ',
        'Using our Anarcho-Totalitarianism solution, we also kill two birds with one stone. AI controlling the state is radical and transhumanist, but not omnist. Transhumanism is, simplified, as much technology as possible. Our vision requires a society based on primitivism too, but we can do that. If we make the AI-controlled government force everyone to stay away from modern technology, we make a transhumanist-totalitarian state enforcing anarcho-primitivism, easily combining ideologies that should be polar opposites.', 
        'This is a tricky one, but purely economically speaking, it is doable. Very simplified, communism is when the means of production are owned by the community, and capitalism is when it is privately owned via corporations. To combine them both, we wish to separate the world into many private corporations instead of countries. Each of these corporations work as little societies, and they are all communist. They are fully controlled by the community, and people do what they can and get what they need, if it is available. However, these corporations all have different resources and must trade and sell to each other to survive. Their starting points are unequal, but all corporations have a lot of freedom because the market is completely free and are not required to lessen the comfort of their inhabitants to give to anyone else. While each corporate society is communistic, if they fail at capitalism, they starve. If they succeed, all their inhabitants are secured a quality of life no other economic system can give them.  '
    ]
	
	let index = 0
	
	const next = () => {
		index = (index + 1) % imageSlider.length
	}

    const back = () => {
		index = (index + imageSlider.length - 1) % imageSlider.length
	}
</script>

<h2>Logistics</h2>
<div class = "rituals">
    <div class="slides">
        {#each [imageSlider[index]] as src (index) }
            <img transition:fade {src} alt="" />	
        {/each}
        </div>
    <div class="box">
        <h4>We have a solution for everything</h4>
        <p>Some might see a party whose ideology involves both sides of every political axis rather silly.
             Maybe even a little unrealistic. But we don’t give up. We believe that there is always a way to include both sides, and it’s our mission to find it.
              We have already found solutions to the most obvious “contradictory” political ideologies.</p>

        <p>Of course, we have solutions to more problems than written below, but you are welcome to click through some of them below.</p>
        <div class = "text">
            <div>
                <button on:click={back}><i class="fa-solid fa-chevron-left"></i></button>
            </div>
            <div>
                {#each [title[index]] as src (index)}
                <h4>{src}</h4>	
                {/each}
                {#each [content[index]] as src (index)}
                <p>{src}</p>	
                {/each}
            </div>
            <div>
                <button on:click={next}><i class="fa-solid fa-chevron-right"></i></button>
            </div>
        </div>
        <div class = "information">{index + 1} of {imageSlider.length}</div>
    </div>
</div>

<style>

h2 {
    margin-top: 7vh;
    text-align: center;
}

h4 {
    text-align: center;
}


    .rituals {
    display: grid;
    grid-template-columns: 1fr 5fr 1fr 5fr;
    padding: 3vw;
}

.rituals button {
    margin: auto;
    font-size: 4vh;
    color: rgb(98, 157, 141);
    background: none;
    border: none;
}


:global(.box){
    background-color: #fafafa;
    border-radius: 10px;
    border: 2px rgb(98, 157, 141) solid;
}

:global(.box):not(.faq .box){
    margin-bottom: 20vh;
}

:global(.dark-mode .box){
    background-color: rgb(24, 24, 24);
}

.box {
    padding: 3vh;
    position: relative;
    margin-left: 45vw;
    height: 80vh;
    width: 35vw;
}

.text {
    display: flex;
}




img {
    position: absolute;
    height: 86.5vh;
    margin-left: 5vw;

}

.information {
    bottom: 1vh;
    position: absolute;
    text-align: center;
    padding-left: 16vw;
}





</style>