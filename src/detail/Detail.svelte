<script>
    import {onMount } from 'svelte';

    import { httpGet } from '../common/api.js';

    export let id;

    let book = {}
    onMount(async() =>{
        const {data} = await httpGet('/' + id)
        book = data[0].data[0]; 
    } )

</script>

<div>Detail page - {book.title}</div>