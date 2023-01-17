<template>
  <nav>
    <div class="flex justify-between items-center pt-6 px-10">
      <div class="w-32 px-6">
        <img src="../assets/images/bau-logo.png" alt="">
      </div>
      <div ref="menu" class="hidden md:flex justify-between space-x-4 pr-6">
        <NavbarDropdown :title=" navbaritems.researchField.title " :menus="navbaritems.researchField.menus" /> <!-- Research field -->
        <NavbarDropdown :title=" navbaritems.researchTeam.title " :menus="navbaritems.researchTeam.menus" /> <!-- Research team -->
        <NavbarDropdown :title=" navbaritems.labfacilities.title " :menus="navbaritems.labfacilities.menus" /> <!-- lab facilities -->
        <NavbarDropdown :title=" navbaritems.publications.title " :menus="navbaritems.publications.menus" /> <!-- publications -->
        <a href="" class="nav-item">Youth network</a>
        <a href="" class="nav-item">Contact us</a>
      </div>

      <div class="flex md:hidden button">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6 transition-all"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </div>
    </div>
    <!--mobile menu-->
    <div class="mobile-menu hidden md:hidden mr-2 bg-white">
      <div class="flex flex-col gap-2">
        <NavbarDropdown :title=" navbaritems.researchField.title " :menus="navbaritems.researchField.menus" /> <!-- Research field -->
        <NavbarDropdown :title=" navbaritems.researchTeam.title " :menus="navbaritems.researchTeam.menus" /> <!-- Research team -->
        <NavbarDropdown :title=" navbaritems.labfacilities.title " :menus="navbaritems.labfacilities.menus" /> <!-- lab facilities -->
        <NavbarDropdown :title=" navbaritems.publications.title " :menus="navbaritems.publications.menus" /> <!-- publications -->
        <a href="" class="nav-item">Youth network</a>
        <a href="" class="nav-item " id="contact">Contact us</a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      navbaritems: {
        researchField: {
          title: 'Research field',
          menus: [
            { id: 1, menuTitle: 'Technology', link: '' },
            { id: 2, menuTitle: 'Ongoing project', link: '' },
            { id: 3, menuTitle: 'Completed project', link: '' }
          ]
        },
        researchTeam: {
          title: 'Research team',
          menus: [
            { id: 1, menuTitle: 'Research supervisor', link: '' },
            { id: 2, menuTitle: 'PhD researcher', link: '' },
            { id: 3, menuTitle: 'Graduate student', link: '' },
            { id: 4, menuTitle: 'Undergraduate student', link: '' }
          ]
        },
        labfacilities: {
          title: 'Lab facilities',
          menus: [
            { id: 1, menuTitle: 'Advanced drying lab', link: '' },
            { id: 2, menuTitle: 'Advanced storage lab', link: '' },
            { id: 3, menuTitle: 'Advanced biogas lab', link: '' },
            { id: 4, menuTitle: 'Advanced engineering lab', link: '' }
          ]
        },
        publications: {
          title: 'Publications',
          menus: [
            { id: 1, menuTitle: 'Scientific papers', link: '' },
            { id: 2, menuTitle: 'Academic writing', link: '' },
            { id: 3, menuTitle: 'Technology profile', link: '' },
            { id: 4, menuTitle: 'Presentation', link: '' },
            { id: 5, menuTitle: 'Seminar', link: '' },
            { id: 6, menuTitle: 'Technical report', link: '' }
          ]
        }
      }
    }
  },
  mounted () {
    const button = document.querySelector('div.button')
    const menu = document.querySelector('div.mobile-menu')
    button.addEventListener('click', () => {
      menu.classList.toggle('hidden')
    })
  }
}
</script>

<style>
.nav-item {
  @apply px-6 py-2 hover:cursor-pointer hover:bg-green-700 hover:text-white rounded-xl font-bold transition duration-500;
}
.mobile-nav {
  @apply px-6 py-2 bg-white;
}
a.nuxt-link-active {
  @apply text-white font-bold;
}
.group:hover .group-hover\:block {
  display: block !important;
}
li{
  @apply list-none;
}
</style>
