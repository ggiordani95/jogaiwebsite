<script lang="ts">
import Logo from "$lib/assets/jogailogo.png"
import mockup from "$lib/assets/mockup2.png"
import google from "$lib/assets/googleplay.png"
import apple from "$lib/assets/appstore.png"
import { onMount } from 'svelte';
import { fade, fly } from 'svelte/transition';


  let loaded = false;

  onMount(() => loaded = true);
</script>

<div class="bg-primary-bg flex flex-col justify-center items-center select-none">

    {#if loaded}
    <div class="w-full my-12 flex flex-col justify-center items-center gap-32">
        <div class="w-[900px] flex flex-row justify-between items-center">
            <img src={Logo} alt="jogai logo" in:fade={{delay: 150, duration: 2500}} class="hover:scale-110 transition-all"/>
            <ul class="text-zinc-500 font-semibold flex flex-row gap-8 text-lg cursor-pointer">
                <li class="hover:scale-110 hover:text-white">
                    Home
                </li>
                <li class="hover:scale-110 hover:text-white">
                    Serviços
                </li >
                <li class="hover:scale-110 hover:text-white">
                    Contato
                </li>
                <li class="text-yellow-300 underline underline-offset-4 hover:scale-110">
                    Entrar
                </li>
            </ul>
        </div>
        
        <div class="w-[900px] flex flex-row justify-between items-center" in:fade={{delay: 150, duration: 2000}}>
            
            <div class="flex flex-col flex-1 mb-24 " in:fly={{x: -300, delay: 150, duration: 1200}}>
                <h1 class="text-zinc-600 text-6xl max-w-xl font-semibold transition-all hover:scale-110">
                    Sistema que <span class="text-zinc-400">aproxima</span> arenas
                    e jogadores
                </h1>
                <p class="text-zinc-800 mt-8 font-medium">
                    Disponibilize sua quadra para agendamento, ou caso queira jogar agende um horário na quadra de sua preferência.
                </p>
                <div class="flex flex-row gap-1 mt-8 items-center">
                    <img src={google} alt="google logo" />
                    <img src={apple} alt="google logo" />
                    <h4 class="text-white text-lg underline underline-offset-4 ml-4 cursor-pointer hover:text-yellow-400 hover:scale-110 transition-all">Saiba mais</h4>
                </div>  
            </div>
            
            <div class="flex flex-col flex-1 justify-center items-end" in:fly={{x: 300, delay: 50, duration: 1300}}>
                <img src={mockup} alt="jogai logo" width="240px"  />
                
            </div>
            
        </div>
        
    </div>
    {/if}
 
</div>

<style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
</style>