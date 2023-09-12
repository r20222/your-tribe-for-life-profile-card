<script>
    export let data
</script>

<main>
    <section class="top-mobile">
        <h1>{data.title}</h1>
        <p>{data.intro}</p>
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
    }
    img{
        max-height:100%;
        /* max-width:auto; */
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
        padding-left:3rem;
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
    }
    /* how to style @html elements: https://stackoverflow.com/questions/56607606/styling-a-html-tag-of-a-svelte-component-by-ising-the-in-component-style */
    :global(a){
        color:black;
    }
    :global(a:hover){
        color:rgb(72, 70, 70);
    }
</style>

<!-- <pre>
    {JSON.stringify(data,null,2)}
</pre> -->