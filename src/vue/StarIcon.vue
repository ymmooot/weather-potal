<template>
  <svg
    version="1.2"
    baseProfile="tiny"
    xmlns="http://www.w3.org/2000/svg"
    viewBox="40 40 180 180"
    width="256"
    height="256"
    xml:space="preserve"
  >
    <switch>
      {{ mainColor }}
      <g>
        <path
          :fill="fillColor"
          :stroke="strokeColor"
          stroke-width="16"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-miterlimit="10"
          d="M123.574 52.994c2.434-4.932 6.417-4.932 8.852 0l18.164 36.807c2.434 4.932 8.879 9.613 14.322 10.404l40.617 5.902c5.443.791 6.674 4.578 2.735 8.418l-29.391 28.648c-3.938 3.84-6.4 11.416-5.47 16.836l6.938 40.453c.93 5.422-2.292 7.764-7.161 5.203l-36.329-19.1c-4.868-2.559-12.834-2.559-17.703 0l-36.329 19.1c-4.868 2.561-8.09.219-7.161-5.203l6.938-40.453c.93-5.42-1.532-12.996-5.47-16.836l-29.391-28.648c-3.938-3.84-2.708-7.627 2.735-8.418l40.617-5.902c5.443-.791 11.888-5.473 14.322-10.404l18.165-36.807z"
        />
      </g>
    </switch>
  </svg>
</template>

<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<{
  active: boolean;
  mainColor?: string;
}>();

const mainColor = computed(() => props.mainColor || "#F9B618");
const fillColor = computed(() => props.active ? mainColor.value : "none");
const strokeColor = computed(() => mainColor.value);
</script>
