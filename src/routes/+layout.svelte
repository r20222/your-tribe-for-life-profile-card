<main>
    <slot />
</main>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Cinzel+Decorative&display=swap');
    :global(html){
        background-color: #F7F6C5;
        font-family: 'Cinzel Decorative', cursive;
    }
    main{
        height:100vh;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    @media screen and (min-width: 700px){
        main{
        height:100vh;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        }
    }
</style>