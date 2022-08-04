<script>
    import "../app.css";
    import {locale} from "../store/locale";
</script>

<div class="flex justify-between p-4">
    <div class="p-4 space-x-2">
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/imprint">Imprint</a>
    </div>

    <select bind:value={$locale}>
        <option>en</option>
        <option>de</option>
    </select>
</div>
<div class="p-4">
    <slot />
</div>
