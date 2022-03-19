<template>
  <div class="container">
    <BaseModal>
      <template>
        <div class="p-2">
          <div class="flex justify-center font-bold text-xl py-2">
            ユーザ登録
          </div>
          <div class="py-6">
            <InputForm
              label="ユーザ名"
              placeholder="name"
              :required="true"
              class="mb-2"
            />
            <InputForm
              label="Ethereumアドレス"
              placeholder="0xaaaaaaaa..."
              :required="true"
              class="mb-2"
            />
            <InputForm
              label="パスワード"
              type="password"
              :required="true"
              class="mb-2"
            />
            <InputForm
              label="パスワード確認"
              type="password"
              :required="true"
              class="mb-2"
            />
          </div>
          <div class="flex justify-center">
            <AtomButton>
              登録
            </AtomButton>
          </div>
        </div>
      </template>
    </BaseModal>
    asdf
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

import BaseModal from '~/components/BaseModal.vue';
import InputForm from '~/components/molecules/InputForm.vue'
import AtomButton from '~/components/atoms/AtomButton.vue'

export default Vue.extend({
  components: {
    BaseModal,
    InputForm,
    AtomButton
  }
})
</script>
