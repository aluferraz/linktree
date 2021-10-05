<template>
   <div class="q-pa-md linktree">
    <div class="doc-container">
        <div class="row justify-center">
            <div class="column items-center" style="height: 9.375rem">
              <q-avatar size="8.125rem">
                <img class="center" src="../assets/alu-avatar.webp" width="130px" height="130px" alt="AluSoft">
              </q-avatar>
            </div>
          </div>
           <div class="row items-center justify-center">
            <div class="column items-center">
              <div class="text-h6">
                <a href="https://www.instagram.com/alu.soft/" target="_blank" style="text-decoration: none;"><p
                  class="linktree">@alu.soft</p></a>
              </div>
            </div>
          </div>
    </div>
     <div class="doc-container">
        <div class="column items-center">
          <div class="text-h6">
            <a href="https://www.youtube.com/channel/UCgF1sIfI6KBXVWvfRIHAcvw" target="_blank"
               style="text-decoration: none;">
              <p class="linktree">Conheça meu canal no YouTube &#128071;</p>
            </a>
          </div>
        </div>
      </div>
    <div class="doc-container">
      <div class="row items-center justify-center qa-pt-md">
          <div class="column items-center">
            <q-btn v-for="(link) in links" :key="link.id"
                   color="accent"
                   :icon="link.icon"
                   :label="link.desc"
                   :class="[link.shake ? 'shake' : '','q-ma-sm']"
                   v-on:click="linkClick(link)"
                   :aria-label="link.desc"
            >
              <q-badge v-if="link.badge" rounded floating>novo</q-badge>
            </q-btn>
          </div>
        </div>
    </div>
     <div class="row items-center justify-center">
          <div class="q-pa-md q-gutter-sm">
            <div class="q-pa-md q-gutter-sm">
              <q-btn v-for="btn in buttons" :key="btn.icon" round color="accent" :icon="btn.icon"
                     :aria-label="btn.desc"
                     @click="linkClick(btn)"/>
            </div>
          </div>
        </div>
   </div>
</template>
<style lang="scss">
.linktree{
    color: #fafafa;
}

.shake {
  animation: shake-animation 4.72s ease infinite;
  transform-origin: 50% 50%;
}

@keyframes shake-animation {
  10%, 90% {
    transform: translate3d(-1px, 0, 0);
  }

  20%, 80% {
    transform: translate3d(2px, 0, 0);
  }

  30%, 50%, 70% {
    transform: translate3d(-4px, 0, 0);
  }

  40%, 60% {
    transform: translate3d(4px, 0, 0);
  }
  //60%, 100% { transform:translate3d(0,0,0) }
}
</style>
<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  data(){
    return {
      links: [
        {
          // img: 'https://cdn.quasar.dev/img/boy-avatar.png',
          icon: 'fab fa-youtube',
          desc: 'Youtube AluSoft',
          dest: 'https://www.youtube.com/channel/UCgF1sIfI6KBXVWvfRIHAcvw',
          caption: false,
          badge: 'vídeo novo!',
          shake: true,
          id: 'youtube',
        },
        {
          icon: 'fab fa-github',
          desc: 'Github Gist\'s',
          dest: 'https://gist.github.com/aluferraz',
          id: 'github_gists',
        },
      ],
        buttons: [
        {
          icon: 'mail',
          dest: 'mailto:lucas@alusoft.com.br',
        },
        {
          icon: 'fab fa-instagram',
          dest: 'https://www.instagram.com/alu.soft/',
        },
        {
          icon: 'home',
          dest: 'https://alusoft.com.br',
        },
      ],
    }
  },
  methods:{
    linkClick(link){
        window.open(link.dest, '_blank', 'noopener');
    },
  }
})
</script>
