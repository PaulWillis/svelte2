<script>
  import { onMount } from "svelte";

  import Button from '../common/Button.svelte'
  import BookGrid from "./BookGrid.svelte"; 
  
  import { httpGet } from "../common/api.js"; 

 // export let onClick;

  // function onClick(id) {
  //     alert( id)
  //   }

  let books = [];
  onMount(async function() {
    const { data } = await httpGet("/?_sort=id&_order=desc");
    books = data[0].data;
    console.log(books);
  });

// const books = [
//     {id: 1,
//     title: 'Hello' , author: 'Paul'
// }
// ,    {id: 2,
//     title: 'Marcia', author: 'Paul2'
// },    
// {
//     id: 3,
//     title: 'How'
//     , author: 'Paul3'
// }
// ,    {id: 4,
//     title: 'are', author: 'Paul4'}
// ,    {id: 5,
//     title: 'you?', author: 'Paul5'
// }

// ];
</script>

<style>
    header {
      margin: var(--spacingMedium) 0 var(--spacingLarge) 0;
      text-transform: uppercase;
    }
    .preamble {
      display: block;
    }
    h1 {
      font-size: var(--typeSizeXXLarge);
      font-weight: var(--typeWeightBold);
      line-height: var(--typeLineHeightTight);
    }
  
    .greeting {
      font-size: var(--typeSizeSmall);
    }
  </style>
  
  <header>
    <span class="preamble">Welcome to the</span>
    <h1>Library</h1>
  </header>
 
 

<p class="greeting">
    This is a library for books.
  </p>


<Button>+ Add Book</Button>

<BookGrid {books} on:book-select  />
