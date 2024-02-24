<script setup>
import {
  HomeIcon,
  HashtagIcon,
  BellIcon,
  InboxIcon,
  BookmarkIcon,
  DocumentTextIcon,
  EllipsisHorizontalCircleIcon,
  UserIcon,
  PencilIcon,
  ChevronDownIcon
} from "@heroicons/vue/16/solid/index.js";

import {
  HomeIcon as HomeIconOutline,
  HashtagIcon as HashtagIconOutline,
  BellIcon as BellIconOutline,
  InboxIcon as InboxIconOutline,
  BookmarkIcon as BookmarkIconOutline,
  DocumentTextIcon as DocumentTextIconOutline,
  EllipsisHorizontalCircleIcon as EllipsisHorizontalCircleIconOutline,
  UserIcon as UserIconOutline,
  PencilIcon as PencilIconOutline,
  ChevronDownIcon as ChevronDownIconOutline,
} from "@heroicons/vue/24/outline/index.js";

const { defaultTransition } = useTailwindConfig()
const route = useRoute()
</script>

<template>
  <div class="flex flex-col h-screen">

      <NuxtLink to="/">
        <div
            :class="defaultTransition"
            class="p-2 my-2 rounded-full hover:bg-blue-50 w-min dark:hover:bg-white/20"
        >
            <div class="w-8 h-8">
              <IconTwitter />
            </div>
        </div>
      </NuxtLink>

    <div class="mt-2 space-y-3">

      <SidebarLeftTab to="/" :active="$route.path === '/'" >
        <template v-slot:icon>
          <component :is="$route.path === '/' ? HomeIcon : HomeIconOutline " />
        </template>
        <template v-slot:name>
          Home
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab to="/tweet" >
        <template v-slot:icon>
          <HashtagIcon />
        </template>
        <template v-slot:name>
          Explore
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <BellIcon />
        </template>
        <template v-slot:name>
          Notifications
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <InboxIcon />
        </template>
        <template v-slot:name>
          Messages
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <BookmarkIcon />
        </template>
        <template v-slot:name>
          Bookmarks
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <DocumentTextIcon />
        </template>
        <template v-slot:name>
          Lists
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <UserIcon />
        </template>
        <template v-slot:name>
          Profile
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <EllipsisHorizontalCircleIcon />
        </template>
        <template v-slot:name>
          More
        </template>
      </SidebarLeftTab>

      <div class="hidden xl:block">
        <UIButton liquid size="lg">
                    <span class="font-bold">
                        Tweet
                    </span>
        </UIButton>
      </div>

      <div class="block xl:hidden">
        <UIButton>
          <div class="w-6 h-6 font-bold">
            <PencilIcon />
          </div>
        </UIButton>
      </div>

    </div>
  </div>
</template>