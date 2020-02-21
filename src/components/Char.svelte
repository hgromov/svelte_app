<script>
    export let name;
    export let lvl;
</script>

<style>
	.char {
        width: 200px;
        padding: 10px;
        background: #ffffed;
        border: 1px solid #391a8f;
        border-radius: 3px;
        display: flex;
        flex-direction: column;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    .name {
        align-self: center;
        font-size: 18px;
        color: red;
    }
    .lvl {
        font-size: 12px;
        color: blue;
        align-self: left;
    }
    /* .controls {
        // ...
    } */
</style>

<div class="char">
    <span class="name">{name}</span>
    <div class="controls">
        <button>

        </button>
        <button>x</button>
    </div>
    <span class="lvl">lvl: {lvl}</span>
    <div class="controll-form">
        <button>+</button>
        <button>-</button>
        <input type="text">
    </div>
</div>
