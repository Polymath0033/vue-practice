<script setup lang="ts">
import MarqueeComponent from "./components/marquee-component.vue";
import TestimonialCard from "./components/testimonial-card.vue";
interface TestimonialProps {
  name: string;
  title: string;
  avatar: string;
  content: string;
}
const testimonials: TestimonialProps[] = [
  {
    name: "Emily Johnson",
    title: "Senior Frontend Developer",
    avatar: "https://i.pravatar.cc/150?img=21",
    content:
      "Marquee Library has been a game-changer for our TypeScript projects. Its seamless integration and robust features have significantly improved our UI's dynamic capabilities.",
  },
  {
    name: "Raj Patel",
    title: "Tech Lead",
    avatar: "https://i.pravatar.cc/150?img=18",
    content:
      "I'm thoroughly impressed with Marquee's performance and ease of use. It made implementing complex scrolling texts a breeze, and the support for TypeScript is top-notch.",
  },
  {
    name: "Sofia Garcia",
    title: "UI/UX Designer",
    avatar: "https://i.pravatar.cc/150?img=45",
    content:
      "As a designer, I appreciate how Marquee enhances the visual appeal of our applications. The flexibility it offers in styling and animation is fantastic.",
  },
  {
    name: "John Mack",
    title: "Full Stack Developer",
    avatar: "https://i.pravatar.cc/150?img=60",
    content:
      "Integrating Marquee into our full-stack TypeScript projects has been incredibly efficient. Its compatibility and ease of customization are ideal for our diverse project needs.",
  },
  {
    name: "Isabella Smith",
    title: "Project Manager",
    avatar: "https://i.pravatar.cc/150?img=32",
    content:
      "Marquee Library has consistently delivered beyond our expectations. It's not just a tool; it's an asset that enhances productivity and creativity in our TypeScript applications.",
  },
];
</script>

<template>
  <h1 class="text-3xl font-bold underline">Hello world from App.vue</h1>
  <marquee-component className="py-2" :fade="true">
    <TestimonialCard
      v-for="testimonial in testimonials"
      :key="testimonial.name"
      :name="testimonial.name"
      :title="testimonial.title"
      :avatar="testimonial.avatar"
      :content="testimonial.content"
    />
  </marquee-component>
</template>

<style scoped></style>
