<template>
  <div class="container mx-auto about-page" @wheel="handleWheel">
    <div class="grid grid-cols-2 gap-4">
      <div
        class="image-container flex items-center sticky top-0 h-screen"
        ref="imageContainer"
      >
        <img
          data-speed="0.5"
          :src="currentImage"
          :alt="altText"
          class="mx-auto w-64 cursor-pointer"
          @click="backToHome"
        />
      </div>
      <div class="content">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellendus,
          ut. Esse rem voluptas impedit, hic dolores atque accusamus delectus,
          provident placeat modi illum facilis reprehenderit eius ratione
          officia laborum cupiditate!
        </p>
        <br />
        <p>
          Deserunt cillum ea officia aliquip ad ad ut consectetur mollit
          deserunt ut anim. Culpa cillum laboris et do consectetur commodo
          mollit sunt deserunt elit quis exercitation ad minim. Ad excepteur
          reprehenderit ipsum commodo tempor ad quis do dolore aliqua
          exercitation.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
        <br />
        <p>
          Quis amet quis laboris eu amet. Ad culpa duis magna ex enim culpa
          adipisicing ipsum Lorem fugiat occaecat duis id cupidatat. Ex qui
          tempor adipisicing officia nostrud aliquip do fugiat laborum. Sit non
          duis dolore aliqua magna officia quis aute pariatur mollit
          reprehenderit labore sunt. Id qui voluptate duis sint sint est irure.
          Sint fugiat tempor culpa culpa ea minim minim fugiat nostrud nostrud
          fugiat.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import profImage from "@/assets/prof.jpg";
import profImage2 from "@/assets/prof2.jpg";

gsap.registerPlugin(ScrollTrigger);

export default {
  data() {
    return {
      images: [
        {
          src: profImage,
          alt: "Alt text for image 1",
          threshold: 1, // adjust as needed
        },
        {
          src: profImage2,
          alt: "Alt text for image 2",
          threshold: 0.6, // adjust as needed
        },
        // add more images as needed
      ],
      currentImage: profImage, // set initial image
      altText: "Alt text for image 1",
    };
  },
  mounted() {
    let tl = gsap.timeline();
    tl.from(".about-page", { opacity: 0, y: 100, duration: 1 });

    // ScrollTrigger.create({
    //   trigger: ".image-container",
    //   pin: true,
    //   start: 0,
    //   end: 100,
    // });
  },
  methods: {
    handleWheel(e) {
      if (e.deltaY < 0) {
        this.currentImage = this.images[0].src;
        this.altText = this.images[0].alt;
      } else {
        this.currentImage = this.images[1].src;
        this.altText = this.images[1].alt;
      }
    },
    backToHome() {
      this.$router.push({ name: "home" });
    },
  },
};
</script>
