<script>
    export let data
</script>

<svelte:head>
	<title>Visitekaart</title>
</svelte:head>

<main>
    <section class="top-mobile">
        <h1>{data.title}</h1>
        <p>{data.intro}</p>
    </section>
   
    <section class="left-desktop">
        <picture class="image-container">
            <img src="{data.afbeelding.url}" alt="{data.title}" width="500" >
        </picture>
        <section class="intro-desktop">
            <h1>{data.title}</h1>
            <p>{data.intro}</p>
        </section>
    </section>

    <section class="bottom-mobile">
        <section class="buttons">
            <button class="popover-button" popovertarget="skills-popover">SHOW SKILLS</button>
                <div id="skills-popover" popover>
                    <div class="title-close-container">
                        <h2>Skills</h2>
                        <button class="popover-close" popovertarget="skills-popover" popovertargetaction="hide">
                            <span>Close &#10006;</span>
                        </button>
                    </div>
                    <div class="skills-container">
                        <ul class="skills">
                            {#each data.skillslist as skill}
                                {@html skill.text}
                            {/each}
                        </ul>
                        <ul class="skills">
                            {#each data.skillslist2 as skill}
                                {@html skill.text}
                            {/each}
                        </ul>
                    </div>
                </div>

            <button class="popover-button" popovertarget="projects-popover">SHOW PROJECTS</button>
            <div popover id="projects-popover">
                <div class="title-close-container">
                    <h2>Projects</h2>
                    <button class="popover-close" popovertarget="projects-popover" popovertargetaction="hide">
                        <span>Close &#10006;</span>
                    </button>
                </div>
                <ul class="project-list">
                    {#each data.projectlist as project}
                        <li>{@html project.text}</li>
                    {/each}
                </ul>
            </div>
        </section>

        <section class="image-socials">
            <picture class="image-container">
                <img src="{data.afbeelding.url}" alt="{data.title}" width="500" >
            </picture>

            <div class="social-links">
                <ul>
                    {#each data.sociallinks as link}
                        <li>{@html link.text}</li>
                    {/each}
                </ul>
            </div>
        </section>
    </section>

    <section class="middle-desktop">
        <div>
            <img src="{data.html.url}" alt="{data.html.alt}" title="{data.html.alt}" width="70">
        </div>
        <div>
            <img src="{data.css.url}" alt="{data.css.alt}" title="{data.css.alt}" width="70">
        </div>
        <div>
            <img src="{data.javascript.url}" alt="{data.javascript.alt}" title="{data.javascript.alt}" width="70">
        </div>
        <div>
            <img src="{data.node.url}" alt="{data.node.alt}" title="{data.node.alt}" width="70">
        </div>
        <div>
            <img src="{data.svelte.url}" alt="{data.svelte.alt}" title="{data.svelte.alt}" width="70">
        </div>
        <div>
            <img src="{data.figma.url}" alt="{data.figma.alt}" title="{data.figma.alt}" width="70">
        </div>
        <div>
            <img src="{data.openai.url}" alt="{data.openai.alt}" title="{data.openai.alt}" width="70">
        </div>
    </section>
    <section class="right-desktop">
        <div class="vertical-line"></div>
        <section class="projects-desktop">
            <section class="projects-desktop-container">
                <h2>Projects</h2>
                <ul class="project-list">
                    {#each data.projectlist as project}
                        <li>{@html project.text}</li>
                    {/each}
                </ul>
            </section>
            

            <ul class="socials-desktop">
                {#each data.sociallinks as link}
                    <li>{@html link.text}</li>
                {/each}
            </ul>
        </section>
        
    </section>
</main>


<style>
    main{
        height:100vh;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    .buttons{
      display: flex;
      flex-direction: column;
      max-width: 50vw;  
      gap:.5rem; 
    }
    button{
        background-color: #FB6CAA;
        border: 1px solid black;
    }
    button.popover-button{
        padding: .3rem 0;
    }
    .image-socials{
        display: flex;
    }
    .image-container{
        background: black;
        width: 50vw;
        height: 15rem;
        margin-top:1rem;
        overflow: hidden;
        display:flex;
        justify-content: center;
        border: black solid 1px;
    }
    .social-links{
        display: flex;
        flex-direction: column;
        justify-content: end;
        margin-left:1rem;
        margin-top:1rem;
        width:calc(50vw - 2rem);
    }
    ul{
        list-style: none;
        padding-left:0;
        margin: 0; /* makes the list align to bottom https://stackoverflow.com/questions/32454236/space-between-unordered-lists*/
    }
    #skills-popover, #projects-popover{
        width:92vw;
        height:83vh;
        background-color: #EFF7F6;
        overflow: hidden;
    }
    .title-close-container{
        display: flex;
        justify-content: space-between;
        margin-left:1rem;
    }
    .skills-container{
        display: flex;
        width:100%;
        justify-content: space-around;
        margin-top:3rem;
    }
    .skills{
        line-height:5rem;
    }
    .project-list{
        margin-top:3rem;
        /* line-height: 4rem; */
    }
    .project-list li{
        margin-bottom:3rem;
        margin-left:1rem;
        margin-right:1rem;
    }
    /* how to style @html elements: https://stackoverflow.com/questions/56607606/styling-a-html-tag-of-a-svelte-component-by-ising-the-in-component-style */
    :global(a){
        color:black;
    }
    :global(a:hover){
        color:rgb(72, 70, 70);
    }

    .left-desktop, .right-desktop, .middle-desktop{
        display: none;
    }

    /* desktop */
    @media screen and (min-width: 700px){
        main{
        height:100vh;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        }

        .bottom-mobile{
            display: none;
        }
        .top-mobile{
            display:none;
        }
        .left-desktop{
            display: block;
            display:flex;
            flex-direction: column;
            justify-content: space-between;
            height:100vh;
            width:65vw;
            margin-left:1rem;
        }
        .middle-desktop{
            width:5rem;
            height:90vh;
            margin-top:5vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .middle-desktop div{
            width:100%;
            aspect-ratio: 1/1;
            background-color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .right-desktop{
            display:flex;
            width:25vw;
        }


        .image-container{
            width: 20rem;
            height: auto;
        }
        .intro-desktop{
            max-width:40vw;
            padding-bottom:2rem;
        }
        .intro-desktop h1{
            font-size: 2rem;
        }
        .vertical-line{
            width:3px;
            margin-top:5vh;
            height:90vh;
            background-color: black;
        }
        .project-list{
            margin-top:3rem;   
        }
        .projects-desktop{
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .projects-desktop h2{
            margin-left:1rem;
            margin-top:2rem;
        }
        .socials-desktop{
            padding-bottom: 2rem;
            display:flex;
            margin-left:1rem;
            gap:2rem;
        }
    }
</style>
<!-- 
<pre>
    {JSON.stringify(data,null,2)}
</pre> -->