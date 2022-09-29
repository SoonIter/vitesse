<script setup lang="ts">
const { t } = useI18n()
</script>

<template>
  <nav text-xl mt-6 gap-4 flex>
    <Home />

    <Dark />

    <Language />

    <RouterLink class="icon-btn" to="/about" :title="t('button.about')">
      <div i-carbon-dicom-overlay />
    </RouterLink>

    <Github />
  </nav>
</template>
