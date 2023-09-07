<main>
    <section class="top-mobile">
        <h1>Roelie Jansen</h1>
        <p>
            Roelie is a motivated frontend design & development student at HVA in Amsterdam. 
            She likes to play around with CSS and make cool and funny animations as well as 
            serious informative websites about the universe.
        </p>
    </section>
   

    <section class="bottom-mobile">
        <section class="buttons">
            <button popovertarget="skills-popover">SHOW SKILLS</button>
                <div id="skills-popover" popover>
                    <button class="popover-close" popovertarget="skills-popover" popovertargetaction="hide">
                        <span>Close &#10006;</span>
                    </button>
                    <h2>Skills</h2>
                    <ul>
                        <li>HTML</li>
                        <li>CSS</li>
                        <li>JavaScript</li>
                        <li>Node.JS</li>
                        <li>EJS</li>
                        <li>Svelte</li>
                        <li>OpenAI</li>
                        <li>Figma</li>
                    </ul>
                </div>
            <button popovertarget="projects-popover">SHOW PROJECTS</button>
            <div popover id="projects-popover">
                <button class="popover-close" popovertarget="projects-popover" popovertargetaction="hide">
                    <span>Close &#10006;</span>
                </button>
                <h2>Projects</h2>
                <ul>
                    <li><a href="https://r20222.github.io/FDND-First-Year-Portfolio/" title="First Year Portfolio" target="_blank">FDND First Year Portfolio &#8599</a></li>
                    <li><a href="https://mars-rover-photos.onrender.com/" title="Mars Rover Photos" target="_blank">Mars Rover Photos &#8599</a></li>
                    <li><a href="https://nasa-astronomy-picture-of-the-day.onrender.com/" title="NASA Astronomy Picture Of The Day" target="_blank">NASA Astronomy Picture Of The Day &#8599</a></li>
                    <li><a href="https://fuzzy-yak-life-jacket.cyclic.app/" title="iOdigital CV Tool" target="_blank">iOdigital CV Tool &#8599</a></li>
                    <li><a href="https://r20222.github.io/The-Verve-Agency-Careers/" title="The Verve Agency Careers" target="_blank">The Verve Agency Careers &#8599</a></li>
                    <li><a href="https://zany-pear-dugong-tux.cyclic.app/" title="Countries" target="_blank">Countries &#8599</a></li>
                </ul>
            </div>
        </section>

        <section class="image-socials">
            <div class="image-container">
                <img src="astronaut.jpg" alt="astronaut">
            </div>

            <div class="social-links">
                <ul>
                    <li><a href="https://www.linkedin.com/in/roelie-jansen/" title="LinkedIn" target="_blank">LinkedIn &#8599</a></li>
                    <li><a href="https://github.com/r20222" title="GitHub" target="_blank">GitHub &#8599</a></li>
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
    .image-socials{
        display: flex;
    }
    .image-container{
        background: black;
        width: 50vw;
        height: 15rem;
        margin-top:1rem;
    }
    .social-links{
        display: flex;
        flex-direction: column;
        justify-content: end;
        margin-left:1rem;
        margin-top:1rem;
        background-color: white;
        width:calc(50vw - 2rem);
    }
    ul{
        list-style: none;
        padding-left:0;
        margin: 0; /* makes the list align to bottom https://stackoverflow.com/questions/32454236/space-between-unordered-lists*/
    }
    li a{
        color:black;
    }
    li a:hover{
        color:rgb(72, 70, 70);
    }
    #skills-popover, #projects-popover{
        width:90vw;
        height:83vh;
        background-color: #EFF7F6;
    }
</style>