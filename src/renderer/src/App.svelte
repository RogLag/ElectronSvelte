<script lang="ts">
  import Versions from './components/Versions.svelte'
  import electronLogo from './assets/electron.svg'

  const ipcHandle = (): void => window.electron.ipcRenderer.send('ping')
</script>

<img alt="logo" class="w-32 h-32 mb-5 transition-filter duration-300 hover:drop-shadow-[0_0_1.2em_rgba(105,136,230,0.67)]" src={electronLogo} />
<div class="text-sm leading-4 text-opacity-60 font-semibold mb-2.5 text-white">Powered by electron-vite</div>
<div class="text-2xl leading-8 font-bold text-center mx-2.5 py-4 text-white">
  Build an Electron app with
  <span class="font-bold bg-gradient-to-br from-[#ff3e00] to-[#647eff] bg-clip-text text-transparent">Svelte</span>
  and
  <span class="font-bold bg-gradient-to-br from-[#3178c6] to-[#f0dc4e] bg-clip-text text-transparent">TypeScript</span>
</div>
<p class="text-base leading-6 text-opacity-60 font-semibold text-white">Please try pressing <code class="font-semibold p-[3px_5px] rounded-sm bg-[#282828] font-mono text-[85%]">F12</code> to open the devTool</p>
<div class="flex flex-wrap justify-start pt-8 m-[-6px]">
  <div class="flex-shrink-0 p-1.5">
    <a href="https://electron-vite.org/" target="_blank" rel="noreferrer" class="cursor-pointer no-underline inline-block border border-transparent text-center font-semibold whitespace-nowrap rounded-[20px] px-5 leading-[38px] text-sm bg-[#32363f] text-white hover:bg-[#414853]">Documentation</a>
  </div>
  <div class="flex-shrink-0 p-1.5">
    <!-- svelte-ignore a11y-click-events-have-key-events a11y-no-static-element-interactions a11y-missing-attribute-->
    <a target="_blank" rel="noreferrer" on:click={ipcHandle} class="cursor-pointer no-underline inline-block border border-transparent text-center font-semibold whitespace-nowrap rounded-[20px] px-5 leading-[38px] text-sm bg-[#32363f] text-white hover:bg-[#414853]">Send IPC</a>
  </div>
</div>
<Versions />
