<script lang="ts">
  interface Link {
    id: string
    owner: string
    shortLink: string
    link: string
    createdAt: Date
    updatedAt: Date
    endAt: Date
  }

  export let id = '',
      shortLink = '',
      link = '',
      createdAt = null,
      updatedAt = null,
      endAt = null,
      qrcode = '';

  const url = `http://api.${window.location.host}/${shortLink}`
</script>

<article {id}
         class="backdrop-blur-2xl group duration-200 text-lg grid shadow-xl py-6 px-8 gap-3 bg-white/40 dark:bg-neutral-700/40 border hover:border-amber-400 border-neutral-50 dark:border-neutral-600 rounded-xl">
  <button
      on:click={(event) => {
        navigator.clipboard.writeText(url).then(() => {
          alert('Скопировано')
        });
      }}
      class="outline-none duration-200 invisible opacity-0 group-hover:opacity-100 group-hover:visible text-neutral-900 px-4 py-2 group-hover:bg-amber-400/80 group-hover:shadow-md group-hover:hover:shadow-amber-400 focus:ring focus:ring-amber-400/40 border border-transparent group-hover:border-amber-300 rounded-xl">
    Copy
  </button>
  <p>
    <a href={url} title="Сокращенная ссылка">{url}</a>
    <span class="block text-sm text-neutral-400 dark:text-neutral-500">shortLink</span>
  </p>
  <p>
    <a href={link} title="Оригинальная ссылка">{link}</a>
    <span class="block text-sm text-neutral-400 dark:text-neutral-500">link</span>
  </p>
  <p>
    <time title="Создан от">{createdAt.toLocaleString()}</time>
    <span class="block text-sm text-neutral-400 dark:text-neutral-500">createdAt</span>
  </p>
  <p>
    <time title="Обновлён от">{updatedAt.toLocaleString()}</time>
    <span class="block text-sm text-neutral-400 dark:text-neutral-500">updatedAt</span>
  </p>
  <p>
    <time title="Закончится">{endAt.toLocaleString()}</time>
    <span class="block text-sm text-neutral-400 dark:text-neutral-500">endAt</span>
  </p>
  <img src={qrcode} alt="qrcode" class="rounded-xl bg-white w-full border border-neutral-50">
</article>