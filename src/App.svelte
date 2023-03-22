<script lang="ts">
  import ShortLinkCard from './lib/ShortLinkCard.svelte';
  import { onMount } from 'svelte';

  export let links = [];

  // onMount(async () => {
  //   const res = await fetch('http://api.localhost/links');
  //   links = await res.json();
  //   links = links.map(link => {
  //     return {
  //       id: link.id,
  //       shortLink: link.short_link,
  //       link: link.link,
  //       createdAt: new Date(link.created_at).toLocaleDateString(),
  //       updatedAt: new Date(link.updated_at).toLocaleDateString(),
  //       endAt:  new Date(link.end_at).toLocaleDateString(),
  //       qrcode: link.qrcode
  //     }
  //   });
  // });

  links = [{
    id: 1,
    shortLink: 'F3Awd4',
    link: 'https://ya.ru',
    createdAt: new Date().toLocaleDateString(),
    updatedAt: new Date().toLocaleDateString(),
    endAt: new Date().toLocaleDateString(),
    qrcode: ''
  }];
</script>

<div class="bg-grid-slate-400 mask-image absolute top-0 left-0 w-full h-screen"></div>

<main class="min-h-screen p-6 relative">
  <div class="z-0 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 blur-3xl">
    <div class="flex">
      <div class="w-48 h-48 rounded-full bg-yellow-300/40 right-0 top-0"></div>
      <div
          class="w-96 h-96 rounded-full bg-gradient-to-r from-yellow-300/40 to-red-600/40"></div>
      <div class="w-48 h-48 rounded-full bg-red-600/40 bottom-0 left-0"></div>
    </div>
  </div>

  <h1 class="text-center mb-2 text-5xl font-extrabold">
    <span
        class="text-transparent bg-clip-text bg-gradient-to-r from-yellow-300 to-red-600">41t</span>
  </h1>
  <h2 class="text-center mb-6 text-4xl font-extrabold">Shorten links</h2>

  <section class="grid grid-cols-[repeat(auto-fill,_minmax(300px,_1fr))] gap-6">
    {#each links as { id, shortLink, link, createdAt, updatedAt, endAt, qrcode }}
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
      <ShortLinkCard {id} {shortLink} {link} {createdAt} {updatedAt} {endAt} {qrcode}/>
    {/each}
  </section>
</main>

<!--<main class="flex flex-col justify-center items-center min-h-screen">-->
<!--  <h1 class="text-center text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-yellow-300 to-red-600">-->
<!--    41t</h1>-->
<!--  <form on:submit={submit} name="auth"-->
<!--           class="text-lg grid shadow-xl m-6 py-6 px-8 gap-6 bg-white/40 dark:bg-neutral-700/40 border border-neutral-50 dark:border-neutral-600 rounded-xl">-->
<!--    <header>-->
<!--      <h2 class="text-center text-3xl">Вход</h2>-->
<!--    </header>-->
<!--    <label for="login" class="space-y-2">-->
<!--      <span class="block">Логин</span>-->
<!--      <input id="login" name="login" placeholder="" required-->
<!--             class="outline-none duration-100 focus:ring focus:ring-amber-400/40 bg-neutral-100 dark:bg-neutral-800 px-4 py-2 border border-neutral-50 dark:border-neutral-600 focus:shadow-md focus:border-amber-300 hover:border-amber-300 rounded-xl">-->
<!--    </label>-->

<!--    <label for="password" class="space-y-2">-->
<!--      <span class="block">Пароль</span>-->
<!--      <input type="password" id="password" name="password" placeholder="" required-->
<!--             class="outline-none duration-100 focus:ring focus:ring-amber-400/40 bg-neutral-100 dark:bg-neutral-800 px-4 py-2 border border-neutral-50 dark:border-neutral-600 focus:shadow-md focus:border-amber-300 hover:border-amber-300 rounded-xl">-->
<!--    </label>-->

<!--    <button-->
<!--        class="outline-none duration-100 text-neutral-900 justify-self-end px-4 py-2 bg-amber-400/80 shadow-md hover:shadow-amber-400 focus:ring focus:ring-amber-400/40 border border-amber-300 rounded-xl">-->
<!--      Войти-->
<!--    </button>-->
<!--  </form>-->
<!--</main>-->

<style>
    .bg-grid-slate-400 {
        background-image: url("./lib/angle.svg");
    }

    .mask-image {
        mask-image: linear-gradient(black, transparent);
    }
</style>