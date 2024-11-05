<template>

    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>

    <!-- <ThePromoCodeModal  
      v-if="promoCodeModal.show" 
      :promoCode="affiliatePromoCode" 
      :loggedIn="promoCodeModal.loggedIn"
      @closeModal="(promoCodeModal.show = false)" 
    />

    <TheConfirmModal
      v-if="appVersionWarnModal.show" 
      :title="appVersionWarnModal.title" 
      :message="appVersionWarnModal.message"
      :confirmLabel="appVersionWarnModal.confirmLabel" 
      :confirmAction="appVersionWarnModal.confirmAction" 
      :data="appVersionWarnModal.data"
      @closeModal="ignoreRefreshWarning" 
      :ignoreLabel="appVersionWarnModal.ignoreLabel"
    /> -->

</template>