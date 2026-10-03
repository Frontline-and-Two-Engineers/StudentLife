<script>
    import './MainMenu.css'
    import './Utils.css'
    import '/static/assets/styles/div_center.css'
    import '/static/assets/styles/img_center.css'
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

<main class="mainmenu-bg">
    <img src="/assets/bg/mainmenu.png" alt="Main Menu BG" class="img_center" />
    <div class="div_center">
        <div class="menu-screen container-bg-and-shadow">
            <h1>Студ. Жизнь</h1>
            <button onclick={() => game.startGame()} class="menu-btn">Новая игра</button>
            <button onclick={openLoadMenu} class="menu-btn">Загрузить</button>
            <button onclick={() => game.currentScreen = 'SETTINGS'} class="menu-btn settings-trigger">Настройки</button>
        </div>
    </div>
</main>
