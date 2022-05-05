<div>
    {#each tab as tabItem, index (tabItem)}
        <Buttons
                buttonText={tabItem.buttonText}
                selection={currentButton}
                index={index}
                on:selection={e => onSelection(e.detail)}
        />
    {/each}
    <p>{currentButton >= 0 ? tab[currentButton].description : 'No tab selected yet' }</p>
</div>


<script lang="ts">
    import Buttons from './buttons.svelte'

    let currentButton: number ;
    const tab = [
        {
            description: 'Texto do primeiro tab',
            buttonText: 'Tab 1'
        },
        {
            description: 'Texto do segundo tab',
            buttonText: 'Tab 2'
        },
        {
            description: 'Texto do terceiro tab',
            buttonText: 'Tab 3'
        },
        {
            description: 'Texto do quarto tab',
            buttonText: 'Tab 4'
        }
    ]

    function onSelection(option: number) {
        currentButton = option ;
    }
</script>
