<script>
    import { link } from "svelte-spa-router";

    let selected;
    let options = [
        { id: 1, text: `강의실 1` },
        { id: 2, text: `강의실 2` },
        { id: 3, text: `강의실 3` },
    ];

    // 로그인 여부 (임시)

    let user = {loggedIn:true};
    // let user = {loggedIn:false};
</script>

<header>
    <button type="button" class="btn btn-outline-secondary btn-light" onclick="location.href='/'">HOME</button>

    {#if user.loggedIn}
        <div class="dropdown">
            <button class="btn btn-outline-secondary btn-light dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
            강의실 선택
            </button>

            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                {#each options as option}
                    <li><a class="dropdown-item" href="#">{option.text}</a></li>
                {/each}
            </ul>
        </div>
    {/if}
</header>

<style>
    header {
        background-color: lightgray;
        margin: 0;
        display: flex;
    }

    #dropdownMenuButton1 {
        background-color: F8F9FA;
    }
</style>
