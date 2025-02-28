<script lang="ts">
  import { WebsiteName, primaryLink, primaryLinkText, blogLink, blogText, pricingLink, pricingText, accountLink, accountText, searchLink, searchLabel, searchLinkText, footerTitle, aboutText, net30PricingText, contactUsLink, contactUsText, sponsorLink, sponsorLinkText, sponsorName, sponsorDesc } from "../../config";
  import "../../app.css";

  interface Props {
    children?: import("svelte").Snippet;
  }

  let { children }: Props = $props();
</script>

<div class="navbar bg-base-100 container mx-auto">
  <div class="flex-1">
    <a class="btn btn-ghost normal-case text-xl" href="/">{WebsiteName}</a>
  </div>
  <div class="flex-none">
    <ul class="menu menu-horizontal px-1 hidden sm:flex font-bold text-lg">
      <li class="md:mx-4">
        <a href={primaryLink} class="border border-primary">{primaryLinkText}</a>
      </li>
      <li class="md:mx-2"><a href={blogLink}>{blogText}</a></li>
      <li class="md:mx-2"><a href={pricingLink}>{pricingText}</a></li>
      <li class="md:mx-2"><a href={accountLink}>{accountText}</a></li>
      <li class="md:mx-0">
        <a href={searchLink} aria-label={searchLabel}>
          <svg fill="#000000" class="w-6 h-6" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.545 15.467l-3.779-3.779a6.15 6.15 0 0 0 .898-3.21c0-3.417-2.961-6.377-6.378-6.377A6.185 6.185 0 0 0 2.1 8.287c0 3.416 2.961 6.377 6.377 6.377a6.15 6.15 0 0 0 3.115-.844l3.799 3.801a.953.953 0 0 0 1.346 0l.943-.943c.371-.371.236-.84-.135-1.211zM4.004 8.287a4.282 4.282 0 0 1 4.282-4.283c2.366 0 4.474 2.107 4.474 4.474a4.284 4.284 0 0 1-4.283 4.283c-2.366-.001-4.473-2.109-4.473-4.474z" fill="currentColor"/>
          </svg>
        </a>
      </li>
    </ul>
    <div class="dropdown dropdown-end sm:hidden">
      <button tabindex="0" class="btn btn-ghost btn-circle" aria-haspopup="true">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7"/>
        </svg>
      </button>
      <ul tabindex="0" class="menu menu-lg dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52 font-bold">
        <li><a href={blogLink}>{blogText}</a></li>
        <li><a href={pricingLink}>{pricingText}</a></li>
        <li><a href={accountLink}>{accountText}</a></li>
        <li><a href={searchLink}>{searchLinkText}</a></li>
        <li><a href={primaryLink} class="border border-primary">{primaryLinkText}</a></li>
      </ul>
    </div>
  </div>
</div>

<div class="">
  {@render children?.()}
</div>

<!-- Spacer grows so the footer can be at bottom on short pages -->
<div class="flex-grow"></div>
<div class="">
  <div class="border-t max-w-[1000px] mx-auto"></div>
  <footer class="footer p-10 gap-x-48 lg:gap-x-64 xl:gap-x-96 place-content-center text-base">
    <nav>
      <span class="footer-title opacity-80">{footerTitle}</span>
      <a class="link link-hover mb-1" href="/">{aboutText}</a>
      <a class="link link-hover my-1" href={pricingLink}>{net30PricingText}</a>
      <a class="link link-hover my-1" href={blogLink}>{blogText}</a>
      <a class="link link-hover my-1" href={contactUsLink}>{contactUsText}</a>
      <a class="link link-hover my-1" href={sponsorLink}>{sponsorLinkText}</a>
    </nav>
    <aside>
      <span class="footer-title opacity-80">{sponsorName}</span>
      <a class="max-w-[260px]" href={sponsorLink} target="_blank">
        <div class="font-bold text-3xl mb-1">{sponsorName}</div>
        <div class="font-medium mb-3">{sponsorDesc}</div>
        <div class="link text-sm font-bold mt-2">{sponsorLinkText}</div>
      </a>
    </aside>
  </footer>
</div>
