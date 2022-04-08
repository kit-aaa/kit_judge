<script>
    import { link } from "svelte-spa-router";

    let selected;
    let options = [
        { id: 1, text: `강의실 1` },
        { id: 2, text: `강의실 2` },
        { id: 3, text: `강의실 2` },
    ];

    // 로그인 여부 (임시)

    let user = {loggedIn:true};
    // let user = {loggedIn:false};
</script>

<header>
    <button type="button" class="btn btn-outline-secondary btn-light" onclick="location.href='/'">HOME</button>
    {#if user.loggedIn}
        <form>
            <select bind:value={selected}>
                {#each options as option}
                    <option value={option}>
                        {option.text}
                    </option>
                {/each}
            </select>
        </form>
    {/if}
</header>

<style>
    header {
        background-color: lightgray;
        margin: 0;
        display: flex;
    }

</style>
