<script>
    let theme = localStorage.getItem("theme") || "dark";

    function saveTheme() {
        localStorage.setItem("theme", theme)
    }
</script>

<div id="theme-controls">
    <label for="theme-picker">Theme.</label>
    <form name="theme-picker" on:change={saveTheme}>
        <label for="dark" class="hidden">Dark theme</label>
        <input bind:group={theme} type="radio" name="theme" id="dark" value="dark">
        <label for="solarized" class="hidden">Solarized</label>
        <input bind:group={theme} type="radio" name="theme" id="solarized" value="solarized">
        <label for="light" class="hidden">Light theme</label>
        <input bind:group={theme} type="radio" name="theme" id="light" value="light">
    </form>
</div>