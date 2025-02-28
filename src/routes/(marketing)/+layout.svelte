<script lang="ts">
  import { WebsiteName } from "./../../config";
  import "../../app.css";

  interface Props {
    children?: import("svelte").Snippet;
  }

  let { children }: Props = $props();

  // Self-healing mechanism
  function validateProps() {
    if (!children) {
      console.warn("Warning: children prop is missing or undefined.");
      children = () => ""; // Provide a fallback rendering function
    }
  }
  validateProps();
</script>

<div class="navbar bg-base-100 container mx-auto">
  <div class="flex-1">
    <a class="btn btn-ghost normal-case text-xl" href="/">{WebsiteName}</a>
  </div>
  <div class="flex-none">
    <ul class="menu menu-horizontal px-1 hidden sm:flex font-bold text-lg">
      <li class="md:mx-4">
        <a href="https://mynet30.com/" class="border border-primary">Business, Credit, Simple</a>
      </li>
      <li class="md:mx-2"><a href="/blog">Business Credit Education</a></li>
      <li class="md:mx-2"><a href="/pricing">Pricing & Plans</a></li>
      <li class="md:mx-2"><a href="/account">Your Account</a></li>
      <li class="md:mx-0">
        <a href="/search" aria-label="Search">
          <svg fill="#000000" class="w-6 h-6" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.545 15.467l-3.779-3.779a6.15 6.15 0 0 0 .898-3.21c0-3.417-2.961-6.377-6.378-6.377A6.185 6.185 0 0 0 2.1 8.287c0 3.416 2.961 6.377 6.377 6.377a6.15 6.15 0 0 0 3.115-.844l3.799 [...]" fill="currentColor"/>
          </svg>
        </a>
      </li>
    </ul>
    <div class="dropdown dropdown-end sm:hidden">
      <label tabindex="0" class="btn btn-ghost btn-circle">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7"/>
        </svg>
      </label>
      <ul tabindex="0" class="menu menu-lg dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52 font-bold">
        <li><a href="/blog">Business Credit Education</a></li>
        <li><a href="/pricing">Pricing Plans</a></li>
        <li><a href="/account">Your Account</a></li>
        <li><a href="/search">Search</a></li>
        <li>
          <a href="https://mynet30.com" class="border border-primary">Business, Credit, Simple!</a>
        </li>
      </ul>
    </div>
  </div>
</div>

<div class="">
  {@render children?.()}
</div>

<div class="flex-grow"></div>
<div class="">
  <div class="border-t max-w-[1000px] mx-auto"></div>
  <footer class="footer p-10 gap-x-48 lg:gap-x-64 xl:gap-x-96 place-content-center text-base">
    <nav>
      <span class="footer-title opacity-80">Explore MYNET30</span>
      <a class="link link-hover mb-1" href="/">About MYNET30</a>
      <a class="link link-hover my-1" href="/pricing">Net30 Pricing Plans</a>
      <a class="link link-hover my-1" href="/blog">Business Credit Education</a>
      <a class="link link-hover my-1" href="/contact_us">Contact Us</a>
      <a class="link link-hover my-1" href="https://preciouspairs.org">Sponsor</a>
    </nav>
    <aside>
      <span class="footer-title opacity-80">Sponsor</span>
      <a class="max-w-[260px]" href="https://www.preciouspairs.org" target="_blank">
        <div class="font-bold text-3xl mb-1">Precious Pairs Inc 501c3</div>
        <div class="font-medium mb-3">Empowering Communities Through Education</div>
        <div class="font-light">A nonprofit organization committed to supporting business credit education and growth initiatives.</div>
        <div class="link text-sm font-bold mt-2">Learn More</div>
      </a>
    </aside>
  </footer>
</div>
