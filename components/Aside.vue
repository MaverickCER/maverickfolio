<template>
<aside :class="`project${$t(`${projectStore.project}`)}`" ref="asideRef">
  <div class="container">
    <section class="aside-section">
      <h2>{{ $t(`tAsideSectionTitle${projectStore.project}`) }}</h2>
      <div class="video" v-if="$t(`tAsideSectionVideo${projectStore.project}`) !== `tAsideSectionVideo${projectStore.project}`">
        <iframe width="560" height="315" :src="`${$t(`tAsideSectionVideo${projectStore.project}`)}?autoplay=1&mute=1`" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen />
      </div>
      <img :src="`/img/aside-section-img-${projectStore.project}.png`" alt="placeholder image until a video can be created" v-if="$t(`tAsideSectionVideo${projectStore.project}`) === `tAsideSectionVideo${projectStore.project}`" />
      <h3><a :href="`${$t(`tAsideSectionHref${projectStore.project}`)}`" target="_blank" rel="noopener">{{ $t(`tAsideSectionLinkLabel${projectStore.project}`) }}</a></h3>
      <details open>
        <summary><span role="term" aria-details="details">{{ $t(`tAsideSectionRoleLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="details">
        <article>
          {{ $t(`tAsideSectionRoleDescription${projectStore.project}`) }}
        </article>
      </div>
      <details open>
        <summary><span role="term" aria-details="challenge">{{ $t(`tAsideSectionTechnologyLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="challenge">
        <article>
          {{ $t(`tAsideSectionTechnologyDescription${projectStore.project}`) }}
        </article>
      </div>
      <details open>
        <summary><span role="term" aria-details="action">{{ $t(`tAsideSectionIntroductionLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="action">
        <article>
          {{ $t(`tAsideSectionIntroductionDescription${projectStore.project}`) }}
        </article>
      </div>
      <details open>
        <summary><span role="term" aria-details="solution">{{ $t(`tAsideSectionProblemLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="solution">
        <article>
          {{ $t(`tAsideSectionProblemDescription${projectStore.project}`) }}
        </article>
      </div>
      <details open>
        <summary><span role="term" aria-details="results">{{ $t(`tAsideSectionActionLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="results">
        <article>
          {{ $t(`tAsideSectionActionDescription${projectStore.project}`) }}
        </article>
      </div>
      <details open>
        <summary><span role="term" aria-details="results">{{ $t(`tAsideSectionResultsLabel${projectStore.project}`) }}</span></summary>
      </details>
      <div role="definition" id="results">
        <article>
          {{ $t(`tAsideSectionResultsDescription${projectStore.project}`) }}
        </article>
      </div>
    </section>
  </div>
</aside>
</template>

<style>
aside {
  width: 0%;
  position: fixed;
  z-index: 100;
  top: 0px;
  bottom: 8px;
  background-color: #f3f3f3;
  overflow-x: hidden;
  transition: width 0.5s ease;
  visibility: none;
  overflow-y: hidden;
  overscroll-behavior: none;
}

.project00 aside,
.project01 aside,
.project02 aside,
.project03 aside,
.project04 aside,
.project05 aside,
.project10 aside,
.project11 aside,
.project12 aside,
.project13 aside,
.project14 aside,
.project15 aside {
  right: 0;
  visibility: unset;
  overflow-y: auto;
  width: 100%;
  transition: width 0.5s ease;
}

aside > .container {
  box-sizing: border-box;
  width: 100vw;
  min-height: 100vh;
  transition: opacity 0.5s ease;
  overflow-x: hidden;
  padding: 50px 30px;
}

aside .aside-section {
  max-width: 800px;
  margin: auto;
}

.aside-section h2 {
  color: var(--accent-clr-xx);
  margin: 0 0 30px 0;
}

.aside-section h3 a {
  color: #222222;
  font-size: 16px;
  font-weight: 400;
  font-family: "Montserrat", sans-serif;
  margin: 0 0 30px 0;
  text-decoration: none;
  border-bottom: 1px solid transparent;
  transition: all .5s linear;
  position: relative;
  line-height: 1.5;
}

.aside-section h3 a::after {
  content: ">";
  display: inline-block;
  position: absolute;
  right: -10px;
  top: 50%;
  color: transparent;
  transform: translateY(-50%);
  transition: all .5s linear;
  font-weight: 600;
  font-family: "Montserrat", sans-serif;
}

.aside-section h3:hover a {
  color: #790101;
  border-bottom: 1px solid #790101;
  transition: all .5s linear;
}

.aside-section h3:hover a::after {
  color: #790101;
  transition: all .5s linear;
}

.aside-section .video {
  width: 100%;
  padding-bottom: 56.25%;
  position: relative;
  height: 0;
}

.aside-section .video iframe,
.aside-section .video video {
  position: absolute;
  width: 100%;
  height: 100%;  
}

.aside-section img {
  width: 100%;
  max-width: 800px;
}

.aside-section details {
  overflow: hidden;
}

.aside-section summary {
  display: block;
}

.aside-section summary::-webkit-details-marker {
  display: none;
}

.aside-section summary span {
  position: relative;
  display: block;
  padding: .5rem 0 .5rem 2rem;
  font-size: clamp(16px, 5.7vw, 24px);
  letter-spacing: 2px;
  text-align: left;
  font-weight: 300;
  font-family: "Montserrat", sans-serif;
  color: #444444;
  width: 100%;
}

.aside-section summary span:hover {
  cursor: pointer;
}

.aside-section summary span::before {
  content: "";
  font-size: 1rem;
  display: flex;
  align-items: center;
  transition: transform 0.5s linear;
  width: 1rem;
  height: 0.25rem;
  background-color: #444444;
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%) rotate(90deg);
  transform-origin: center;
  padding: 0;
  margin: 0;
  border-radius: 1rem;
}

.aside-section summary span::after {
  content: "";
  font-size: 1rem;
  display: flex;
  align-items: center;
  width: 1rem;
  height: 0.25rem;
  background-color: #444444;
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  padding: 0;
  margin: 0;
  border-radius: 1rem;
}

.aside-section details + div {
  box-sizing: border-box;
  max-height: 0;
  overflow: hidden;
  transition: max-height 400ms ease-out, border 0ms 400ms linear;
  color: #222222;
  font-size: 16px;
  font-weight: 400;
  font-family: "Montserrat", sans-serif;
}

.aside-section details + div > article {
  padding: .5rem 0;
  min-height: max-content;
}

.aside-section details + div > article p {
  margin: 0;
  padding: 0;
}

.aside-section details[open] + div {
  max-height: 800px;
  transition: max-height 0.5s linear;
}

.aside-section details[open] span::before {
  transform: translateY(-50%) rotate(0deg);
  transition: transform 0.5s linear;
}
</style>

<script setup>
const projectStore = useProjectStore();
const asideRef = ref(null);
import { onMounted, onUnmounted } from "vue";
function handleScroll() {
  const winScroll = asideRef.value.scrollTop;
  const height = asideRef.value.scrollHeight - asideRef.value.clientHeight;
  const scrolled = (winScroll / height) * 100;
  const element = document.getElementById('__nuxt');
  const sections = ['intro','skills','projects','about','contact'];
  const isAuto = sections.includes(element.className);
  if (isAuto) return;
  element.style.setProperty('--progress-width', `${scrolled}%`);
}

onMounted(() => {
  asideRef.value.addEventListener('scroll', handleScroll);
});
onUnmounted(() => {
  asideRef.value.removeEventListener('scroll', handleScroll);
});
</script>