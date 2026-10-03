<script>
    import './SettingsMenu.css';
    import './Utils.css'
    import { useGameContext } from '$lib/__index__.svelte';
    const game = useGameContext();
</script>

<main class="container settings-container mainmenu-bg">
    <img src="/assets/bg/mainmenu.png" alt="Main Menu BG" class="img_center" />

    <div class="div_center">
        <div class="settings-card container-bg-and-shadow">
            <div class="settings-header">
                <h1>Настройки игры</h1>
            </div>

            <div class="settings-body">
                <div class="setting-row">
                    <label for="speed-range" class="label">Скорость текста:</label>
                    <div class="slider-container">
                        <input
                            id="speed-range"
                            type="range"
                            min="1"
                            max="11"
                            step="0.5"
                            bind:value={game.textSpeed}
                        />
                        <span class="speed-value">
                            {#if game.textSpeed === 11}
                                Моментально
                            {:else}
                                Скорость: {game.textSpeed}
                            {/if}
                        </span>
                    </div>
                </div>

                <div class="setting-row">
                    <label for="volume-range" class="label">Общая громкость:</label>
                    <div class="slider-container">
                        <input
                            id="volume-range"
                            type="range"
                            min="0"
                            max="1"
                            step="0.05"
                            bind:value={game.masterVolume}
                        />
                        <span class="speed-value">
                            {Math.round(game.masterVolume * 100)}%
                        </span>
                    </div>
                </div>
            </div>

            <div class="settings-footer">
                <button onclick={() => game.currentScreen = 'MENU'} class="back-btn">Назад</button>
            </div>
        </div>
    </div>
</main>
