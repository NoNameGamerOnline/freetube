<template>
  <div>
    <template v-if="unlocked">
      <div class="switchColumnGrid">
        <div class="switchColumn">
          <ft-toggle-switch
            class="settingsToggle"
            :label="$t('Settings.Expand All Settings Sections')"
            :default-value="allSettingsSectionsExpandedByDefault"
            :compact="false"
            @change="updateAllSettingsSectionsExpandedByDefault"
          />
        </div>
      </div>
      <general-settings />
      <hr>
      <theme-settings />
      <hr>
      <player-settings />
      <hr>
      <external-player-settings v-if="usingElectron" />
      <hr v-if="usingElectron">
      <subscription-settings />
      <hr>
      <distraction-settings />
      <hr>
      <privacy-settings />
      <hr>
      <data-settings />
      <hr>
      <proxy-settings v-if="usingElectron" />
      <hr v-if="usingElectron">
      <download-settings v-if="usingElectron" />
      <hr v-if="usingElectron">
      <parental-control-settings />
      <hr>
      <sponsor-block-settings />
      <hr v-if="usingElectron">
      <experimental-settings v-if="usingElectron" />
      <hr>
      <password-settings />
    </template>
    <password-dialog
      v-else
      @unlocked="unlocked = true"
    />
  </div>
</template>

<script src="./Settings.js" />
<style scoped src="./Settings.css" />
