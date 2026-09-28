<script>
    import './MainMenu.css'
    import './Utils.css'
    import { useGameContext } from '$lib/__index__.svelte';
    const game = useGameContext();

    /**
     * Opens the SaveMenu in Load mode, remembering that Back should
     * return here rather than to the in-game screen.
     */
    function openLoadMenu() {
        game.saveMenuMode = 'LOAD';
        game.saveMenuReturnTo = 'MENU';
        game.currentScreen = 'SAVES';
    }
</script>

<main class="container menu-container mainmenu-bg">
    <div class="menu-screen container-bg-and-shadow">
        <h1>Студ. Жизнь</h1>
        <button onclick={() => game.startGame()} class="menu-btn">Новая игра</button>
        <button onclick={openLoadMenu} class="menu-btn">Загрузить</button>
        <button onclick={() => game.currentScreen = 'SETTINGS'} class="menu-btn settings-trigger">Настройки</button>
    </div>
</main>