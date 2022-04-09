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

<div class="container">
    <header class="d-flex justify-content-center py-3">
        <ul class="nav nav-pills">
            <li class="nav-item"><button type="button" class="btn btn-outline-secondary btn-light" onclick="location.href='/'">HOME</button></li>
            <li class="nav-item">
                {#if user.loggedIn}
                    <div class="dropdown">
                        <button type="button" class="btn btn-outline-secondary btn-light dropdown-toggle" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                        강의실 선택
                        </button>
                
                        <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                            {#each options as option}
                                <li><a class="dropdown-item" href="/">{option.text}</a></li>
                            {/each}
                        </ul>
                    </div>
                {/if}
            </li>
        </ul>
    </header>
</div>

<!-- <header>
    <div class="home-btn">
        <button type="button" class="btn btn-outline-secondary btn-light" onclick="location.href='/'">HOME</button>
    </div>

    {#if user.loggedIn}
        <div class="dropdown">
            <button type="button" class="btn btn-outline-secondary btn-light dropdown-toggle" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
            강의실 선택
            </button>
    
            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                {#each options as option}
                    <li><a class="dropdown-item" href="/">{option.text}</a></li>
                {/each}
            </ul>
        </div>
    {/if}
</header> -->

<style>
    header {
        background-color: rgb(155, 155, 155);
        margin: 0;
        display: flex;
    }

    .container {
        max-width: 1980px;
        padding: 0;
    }

    .nav-item {
        margin: 0rem 1rem;
    }

    .dropdown-item {
        color: rgb(123, 131, 138);
    }

    .dropdown-item:hover, .dropdown-item:focus {
        color: #1e2125;
        background-color: #e9ecef;
        text-decoration: none;
    }

    .dropdown-item:active {
        color: rgb(255, 255, 255);
        background-color: rgb(123, 131, 138);
        text-decoration: none;
    }
</style>
