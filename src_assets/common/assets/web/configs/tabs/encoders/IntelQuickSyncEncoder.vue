<script setup>
import { ref } from 'vue'
import Checkbox from "../../../Checkbox.vue";

const props = defineProps([
  'platform',
  'config',
])

const config = ref(props.config)
</script>

<template>
  <div id="intel-quicksync-encoder" class="config-page">
    <!-- QuickSync Preset -->
    <div class="mb-3">
      <label for="qsv_preset" class="form-label">{{ $t('config.qsv_preset') }}</label>
      <select id="qsv_preset" class="form-select" v-model="config.qsv_preset">
        <option value="veryfast">{{ $t('config.qsv_preset_veryfast') }}</option>
        <option value="faster">{{ $t('config.qsv_preset_faster') }}</option>
        <option value="fast">{{ $t('config.qsv_preset_fast') }}</option>
        <option value="medium">{{ $t('config.qsv_preset_medium') }}</option>
        <option value="slow">{{ $t('config.qsv_preset_slow') }}</option>
        <option value="slower">{{ $t('config.qsv_preset_slower') }}</option>
        <option value="slowest">{{ $t('config.qsv_preset_slowest') }}</option>
      </select>
    </div>

    <!-- QuickSync Coder (H264) -->
    <div class="mb-3">
      <label for="qsv_coder" class="form-label">{{ $t('config.qsv_coder') }}</label>
      <select id="qsv_coder" class="form-select" v-model="config.qsv_coder">
        <option value="auto">{{ $t('config.ffmpeg_auto') }}</option>
        <option value="cabac">{{ $t('config.coder_cabac') }}</option>
        <option value="cavlc">{{ $t('config.coder_cavlc') }}</option>
      </select>
    </div>

    <!-- Allow Slow HEVC Encoding -->
    <Checkbox class="mb-3"
              id="qsv_slow_hevc"
              locale-prefix="config"
              v-model="config.qsv_slow_hevc"
              default="false"
    ></Checkbox>
  </div>
</template>

<style scoped>

</style>
