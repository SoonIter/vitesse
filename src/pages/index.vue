<script setup lang="ts">
import { routes as _routes } from '~/main'

const routes = reactive(_routes.filter((i) => {
  return i.path.startsWith('/posts')
})).map((i) => {
  return {
    path: i.path,
    // name: import.meta.glob('./posts'),
  }
})
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}

const { t } = useI18n()
</script>

<template>
  <Avatar w-10 h-10 />
  <div v-for="item in routes" :key="item.path">
    <RouterLink :to="item.path">
      {{ item.path }}
    </RouterLink>
  </div>

  <input
    id="input" v-model="name" :placeholder="t('intro.whats-your-name')" :aria-label="t('intro.whats-your-name')"
    type="text" autocomplete="false" p="x4 y2" w="250px" text="center" bg="transparent"
    border="~ rounded gray-200 dark:gray-700" outline="none active:none" @keydown.enter="go"
  >
  <label class="hidden" for="input">{{ t('intro.whats-your-name') }}</label>

  <div>
    <button btn m-3 text-sm :disabled="!name" @click="go">
      {{ t('button.go') }}
    </button>
  </div>
</template>
