<template>
  <div class="container">
    <BaseModal>
      <template>
        <div class="px-2">
          <div class="flex justify-center font-bold text-xl py-2">
            ファイルアップロード
          </div>
          <div class="py-6">
            <AtomLabel class="text-lg" label="1. アップロードするコンテンツを選択"/>
            <div class="py-2 mb-4">
              <UploadFile
                v-model="$data.file"
              />
            </div>
            <AtomLabel class="text-lg" label="2. PBC秘密鍵を入力"/>
            <AtomInput
              v-model="$data.privKey"
              type="text"
              class="mb-2"
              placeholder="0xaaaaaa......"
              />
            <div class="flex justify-center">
              <AtomButton>
                メタデータ作成
              </AtomButton>
            </div>
            <div class="flex justify-center py-2">
              <DownArrowIcon/>
            </div>
          </div>
        </div>
      </template>
    </BaseModal>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

import BaseModal from '~/components/BaseModal.vue';
import AtomFileInput from '~/components/atoms/AtomFileInput.vue'
import DownArrowIcon from '~/components/icons/DownArrowIcon.vue'
import AtomButton from '~/components/atoms/AtomButton.vue'
import AtomLabel from '~/components/atoms/AtomLabel.vue'
import AtomInput from '~/components/atoms/AtomInput.vue'
import AtomFileCard from '~/components/atoms/AtomFileCard.vue'
import UploadFile from '~/components/molecules/UploadFile.vue'

import { SelectFile } from '~/interfaces/content';

export default Vue.extend({
  components: {
    BaseModal,
    AtomFileInput,
    AtomButton,
    AtomInput,
    AtomLabel,
    DownArrowIcon,
    AtomFileCard,
    UploadFile
  },
  data() {
    return {
      file: {} as SelectFile,
      privKey: ''
    }
  },
  methods: {
    makeMetaData():void {
      this.$data.file.file.append('priv_key', this.$data,privKey)
      this.$axios.$post('localhost:8000/content', thos.$data.file.file)
    }
  }
})
</script>
