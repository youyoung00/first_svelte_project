<script>
    import {onMount, onDestroy, beforeUpdate, afterUpdate} from 'svelte'

    // const h1 = document.querySelector('h1')
    // console.log(h1.innerText)
    let name = 'Something..'
    let h1

    function moreDot(){
        name += '.'
    }

    beforeUpdate(() => {
        console.log('Before update!')
        console.log(h1 && h1.innerText)
    })

    afterUpdate(() => {
        console.log('After update!')
        console.log(h1.innerText)
    })

    onMount(() => {
        console.log('Mounted!')
        h1 = document.querySelector('h1')
        // const h1 = document.querySelector('h1')
        // console.log(h1.innerText)
        // return () => {
        //     console.log('Destory in mount')
        // }
    })
    onDestroy(() => {
        console.log('Before destroy~')
        // const h1 = document.querySelector('h1')
        // console.log(h1.innerText)
    })
</script>
<h1 on:click={moreDot}>{name}</h1>