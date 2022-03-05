<script>
    import Button from "./Button.svelte"
    let someText = `Student Frontend Developer in platzi`;
    let count = 0;

    let style = {
        darkMode: false
    }

    function handleClick(){
        count += 1;
    }

    function toggle(){
        style.darkMode = !style.darkMode;
        window.document.body.classList.toggle("dark-mode");
    }

</script>

<style>
    p{
        color: var(--theme-color);
    }

</style>

<div class="About">
    {#if !style.darkMode}
        <p>{someText}</p>
    {:else}
        <p>
            <span>Hello DarkMode</span>
        </p>
    {/if}
    <p>{someText}</p>

    <Button 
        text="Click"
        {count}
        on:click={handleClick}
    />

    <Button
        text="DarkMode"
        on:click={toggle}
    />

    <!-- <button on:click={handleClick}>Click {count === 0 ? '' : count}</button> -->
    <!-- <button on:click={toggle}>DarkMode</button> -->
</div>