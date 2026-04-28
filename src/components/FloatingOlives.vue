<template>
  <!-- Floating olive decorative elements -->
  <div aria-hidden="true" class="floating-olives-layer">
    <span v-for="el in floatingEls" :key="el.id" :ref="el => setRef(el, el_id = el?.dataset?.id)" class="floating-el"
      :data-id="el.id"
      :style="`
        position: fixed;
        top: ${el.top}%;
        left: ${el.left}%;
        font-size: ${el.size}px;
        opacity: 0;
        pointer-events: none;
        z-index: 1;
        user-select: none;
        will-change: transform;
      `"
    >{{ el.char }}</span>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import gsap from 'gsap';

const floatingEls = [
  { id:1,  char:'🫒', size:18, top:12,  left:5   },
  { id:2,  char:'🌿', size:16, top:28,  left:92  },
  { id:3,  char:'🫒', size:14, top:45,  left:8   },
  { id:4,  char:'🌿', size:20, top:18,  left:88  },
  { id:5,  char:'🫒', size:12, top:62,  left:95  },
  { id:6,  char:'🌿', size:15, top:75,  left:4   },
  { id:7,  char:'🫒', size:16, top:85,  left:80  },
  { id:8,  char:'🌿', size:13, top:55,  left:85  },
  { id:9,  char:'🫒', size:11, top:35,  left:2   },
  { id:10, char:'🌿', size:18, top:90,  left:15  },
  { id:11, char:'🫒', size:14, top:5,   left:70  },
  { id:12, char:'🌿', size:12, top:70,  left:50  },
];

const elRefs = {};
const setRef = (el, id) => { if (el) elRefs[id] = el; };

onMounted(() => {
  const allEls = document.querySelectorAll('.floating-el');
  allEls.forEach((el) => {
    const duration  = gsap.utils.random(12, 22);
    const amplitude = gsap.utils.random(25, 55);
    const delay     = gsap.utils.random(0, 6);
    const xDir      = Math.random() > 0.5 ? 1 : -1;

    // Fade in
    gsap.to(el, {
      opacity: gsap.utils.random(0.06, 0.14),
      duration: 2,
      delay,
      ease: 'sine.in'
    });

    // Floating loop
    gsap.to(el, {
      y: `-=${amplitude}`,
      x: `+=${xDir * gsap.utils.random(15, 35)}`,
      rotation: gsap.utils.random(-20, 20),
      duration,
      delay,
      ease: 'sine.inOut',
      repeat: -1,
      yoyo: true,
    });
  });
});
</script>
