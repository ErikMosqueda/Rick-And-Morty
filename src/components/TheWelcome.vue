<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <div class="flex">
    <div class="w-2/5 ">
      <img class="rounded-lg mb-3 md:animate-bounce" src='../assets/flotando.png' alt="">
    </div>
    
    <div class="about ml-5  w-3/5">
      <h1 class=" text-black text-3xl font-bold">¡Infórmate!</h1><br>
        <p class="font-serif ml-5 mr-6 mb-5 text-3xl">Rick y Morty (en inglés: Rick and Morty) es una serie de televisión americana de animación para adultos 
          creada por Justin Roiland y Dan Harmon en 2013 para Adult Swim, también se emitió en Cartoon Network. 
          La serie sigue las desventuras de un científico, Rick Sanchez, y su fácilmente influenciable nieto, Morty, 
          quienes pasan el tiempo entre la vida doméstica y los viajes espaciales, temporales e intergalácticos. 
          Dan Harmon, el co-creador de la serie y Justin Roiland son los encargados de las voces principales de Morty y Rick, 
          la serie también incluye las voces de Chris Parnell, Spencer Grammer y Sarah Chalke. <br>
          <br>La serie se originó por un cortometraje rudimentario animado por Roiland para el festival de cine Channel 101 
          llamado Doc and Mharti, una parodia de los principales protagonistas de Back to the Future. 
          Cuando la cadena NBC despidió a Harmon en 2013 por discusiones entre él y los ejecutivos de la serie que había 
          creado, Community, él y Roiland desarrollaron una serie basada en los personajes ya creados por Roiland.
        </p>
    </div>
  </div>
  
  
</template>
