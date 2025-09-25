<template>
  <div ref="container" class="brain-container"></div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";
import * as THREE from "three";

const container = ref<HTMLDivElement>();
let scene: THREE.Scene;
let camera: THREE.PerspectiveCamera;
let renderer: THREE.WebGLRenderer;
let brain: THREE.Mesh;
let animationId: number;

onMounted(() => {
  init();
  animate();
});

onUnmounted(() => {
  if (animationId) {
    cancelAnimationFrame(animationId);
  }
  if (renderer) {
    renderer.dispose();
  }
});

function init() {
  // Scene setup
  scene = new THREE.Scene();
  scene.background = null;

  // Camera setup
  camera = new THREE.PerspectiveCamera(75, 1, 0.1, 1000);
  camera.position.z = 5;

  // Renderer setup
  renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
  renderer.setSize(400, 400);
  renderer.setClearColor(0x000000, 0);
  container.value?.appendChild(renderer.domElement);

  // Create low poly brain geometry
  const geometry = new THREE.IcosahedronGeometry(2, 1);

  // Create simple white wireframe material
  const material = new THREE.MeshBasicMaterial({
    color: 0xffffff,
    wireframe: true,
    transparent: false,
  });

  brain = new THREE.Mesh(geometry, material);
  scene.add(brain);

  // Add some random vertices displacement for brain-like appearance
  const vertices = geometry.attributes.position.array;
  for (let i = 0; i < vertices.length; i += 3) {
    vertices[i] += (Math.random() - 0.5) * 0.3;
    vertices[i + 1] += (Math.random() - 0.5) * 0.3;
    vertices[i + 2] += (Math.random() - 0.5) * 0.3;
  }
  geometry.attributes.position.needsUpdate = true;
}

function animate() {
  animationId = requestAnimationFrame(animate);

  // Rotate the brain
  if (brain) {
    brain.rotation.x += 0.005;
    brain.rotation.y += 0.01;
    brain.rotation.z += 0.003;
  }

  // Pulsing effect
  const time = Date.now() * 0.001;
  const scale = 1 + Math.sin(time * 2) * 0.1;
  if (brain) {
    brain.scale.set(scale, scale, scale);
  }

  renderer.render(scene, camera);
}
</script>

<style scoped>
.brain-container {
  width: 400px;
  height: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}
</style>
