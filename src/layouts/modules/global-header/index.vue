<script setup lang="ts">
import { GLOBAL_HEADER_MENU_ID } from '@/constants/app';
import { useAppStore } from '@/store/modules/app';
import { useThemeStore } from '@/store/modules/theme';
import GlobalLogo from '../global-logo/index.vue';
import GlobalBreadcrumb from '../global-breadcrumb/index.vue';
import GlobalSearch from '../global-search/index.vue';
import ThemeButton from './components/theme-button.vue';
import UserAvatar from './components/user-avatar.vue';
import { useRouter } from 'vue-router';

defineOptions({
  name: 'GlobalHeader'
});

interface Props {
  /** Whether to show the logo */
  showLogo?: App.Global.HeaderProps['showLogo'];
  /** Whether to show the menu toggler */
  showMenuToggler?: App.Global.HeaderProps['showMenuToggler'];
  /** Whether to show the menu */
  showMenu?: App.Global.HeaderProps['showMenu'];
}

defineProps<Props>();

const appStore = useAppStore();
const themeStore = useThemeStore();
const router = useRouter();

const menuItems = [
  { path: '/home', title: '首页' }
];

const handleMenuClick = (path: string) => {
  router.push(path);
};
</script>

<template>
  <DarkModeContainer class="h-full flex-y-center px-12px shadow-header">
    <div class="flex items-center">
      <GlobalLogo v-if="showLogo" class="h-full" :show-title="true" />
    </div>
    <div v-if="showMenu" class="h-full flex-y-center flex-1-hidden justify-center">
      <div class="flex items-center space-x-4">
        <button
          v-for="item in menuItems"
          :key="item.path"
          class="px-4 py-2 text-gray-700 hover:text-primary transition-colors duration-200"
          :class="{ 'text-primary': $route.path === item.path }"
          @click="handleMenuClick(item.path)"
        >
          {{ item.title }}
        </button>
      </div>
    </div>
    <div v-else class="h-full flex-y-center flex-1-hidden">
      <GlobalBreadcrumb v-if="!appStore.isMobile" class="ml-12px" />
    </div>
    <div class="h-full flex-y-center justify-end">
      <GlobalSearch />
      <LangSwitch
        v-if="themeStore.header.multilingual.visible"
        :lang="appStore.locale"
        :lang-options="appStore.localeOptions"
        @change-lang="appStore.changeLocale"
      />
      <UserAvatar />
    </div>
  </DarkModeContainer>
</template>

<style scoped>
.shadow-header {
  box-shadow: 0 1px 4px rgba(0, 21, 41, 0.08);
}

button {
  position: relative;
}

button::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: var(--primary-color);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

button:hover::after,
button.text-primary::after {
  transform: scaleX(1);
}
</style>
