<template>
  <div id="secondary">
    <div id="trailer-desc" class="section-container">
      <div class="container-desc container-box">
        <h2 id="title-desc">Project Overview</h2>

        <p class="desc">
          We are a group of 11 IT students from the University of Strasbourg, France.
          We are currently in the third year of our Bachelor degree. For one of our classes, we had to form a team and remake a retro video game by adding multiplayer to it.
          We hope you will enjoy our new version of this famous game !
        </p>
      </div>

      <div class="container-video container-box">
        <iframe
          src="https://www.youtube.com/embed/hpnxa0nNNpw"
          title="Astrocket trailer"
          width="560"
          height="315"
          frameborder="0"
          class="video-frame"
          allowfullscreen
          >
        </iframe>
      </div>
    </div>
    <div id="tag-container" class="section-container">
      <div
        v-for="tag in tags"
        :key="tag.title"
        class="tag"
        >
        <styled-section
          :title="tag.title"
          :description="tag.desc"
        />
      </div>
    </div>
    <div id="social-list" class="section-container">
      <a
        v-for="link in links"
        :key="link.ref"
        :href="link.ref"
        target="_blank"
        class="social-link"
        >
        <img
          class="img"
          :src="link.icon"
          :alt="link.platform + ' icon'"
        />
        {{ link.name }}
      </a>
    </div>
  </div>
</template>

<script>
import StyledSection from './StyledSection.vue'

export default {
  components: { StyledSection },
  name: "TheSecondary",
  data() {
    return {
      tags: [
        {
          title: "Asteroids - The original game",
          desc: "The game Asteroids is a spaceshooter. It is fairly simple : you're controlling a spaceship and you must survive at all cost. "
          + "This is no easy task, as a load of asteroids will try to destroy your spaceship, in order to survive, you have to either destroy them or dodge them. "
          + "The longer you can stay alive, the better your score will be."
        },
        {
          title: "Astrocket - Our remake",
          desc: "In Astrocket, the goal is not only to survive the asteroids, but also to survive the attacks from the other players. "
          + "We chose to implement a power-up system to make the game a little more challenging and fun. "
          + "When a player destroys an asteroid, there is a chance that a random item will spawn. This item is what we call a \"power-up\", and it will give the player an advantage over a limited amount of time. "
          + "Your can earn points by destroying the ennemies' spaceships. The player with the highest score at the end of the game wins. "
        }
      ],
      links: [
        {
          platform: "Reddit",
          name: "Astrocket-devs",
          icon: require("@/assets/images/reddit_item.svg"),
          ref: "https://www.reddit.com/user/Astrocket-devs"
        },
        {
          platform: "Twitter",
          name: "AstrocketG",
          icon: require("@/assets/images/twitter_item.svg"),
          ref: "https://twitter.com/AstrocketG"
        },
        {
          platform: "Discord",
          name: "Astrocket",
          icon: require("@/assets/images/discord_item.svg"),
          ref: "https://discord.gg/m3aBuZxjMp"
        }
      ]
    }
  }
}
</script>

<style>
.container-box {
  @apply flex flex-col;
}

.container-video {
  /* @apply flex justify-center; */
  position: relative;
  padding-bottom: 50%;
  width: 50%;
  height: 0;
  @apply w-full;
  @apply md:pb-96;
}

#secondary {
  @apply flex flex-col justify-center;
  @apply md:max-w-7xl mx-auto;
}

.container-desc {
  @apply divide-y divide-gray-300 m-4;
  @apply md:w-1/2
}

.img {
  @apply w-11 m-2;
}

#social-list{
  @apply inline-flex flex-col justify-center mx-auto p-2;
  @apply md:flex-row md:p-1;
}

.social-link{
  @apply flex items-center text-lg font-medium p-2;
}

.social-link:not(:last-child) {
  @apply border-solid border-b border-gray-300;
  @apply md:border-none
}

.desc{
  @apply p-3;
}

#title-desc{
  @apply text-xl font-semibold capitalize p-2;
}

.section-container {
  @apply flex flex-col bg-gray-100 shadow-sm p-4 m-4 rounded;
  @apply md:flex-row md:m-4 md:shadow-md;
}

#trailer-desc{
  @apply flex flex-col p-0 overflow-hidden;
  @apply md:flex-row;
}

#tag-container{
  @apply flex flex-col;
  @apply md:flex-row;
}

.tag:not(:last-child) {
  @apply mb-4;
  @apply md:mb-0 md:mr-4;
}

.video-frame {
  /*@apply w-full h-auto;*/
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  max-height: 400px;
}

</style>
