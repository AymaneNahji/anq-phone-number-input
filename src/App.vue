<template>
  <div class="q-pa-md">
    <h4>Phone Number Input Examples</h4>
    
    <!-- Basic Usage -->
    <div class="q-mb-md">
      <h6>Basic Usage</h6>
      <AnqPhoneNumberInput
        v-model="phoneNumber"
        @selectCountry="onCountrySelect"
      />
      <div class="q-mt-sm text-caption">
        Selected phone number: {{ phoneNumber }}
      </div>
    </div>

    <!-- With Custom Labels -->
    <div class="q-mb-md">
      <h6>Custom Labels</h6>
      <AnqPhoneNumberInput
        v-model="phoneNumber2"
        :countryProps="{
          label: 'Select Country',
          defaultCountry: 'US'
        }"
        label="Enter Phone Number"
      />
    </div>

    <!-- With Excluded Countries -->
    <div class="q-mb-md">
      <h6>Excluded Countries</h6>
      <AnqPhoneNumberInput
        v-model="phoneNumber3"
        :countryProps="{
          excludeCountries: ['RU', 'CN'],
          defaultCountry: 'US'
        }"
      />
    </div>

    <!-- With Validation -->
    <div class="q-mb-md">
      <h6>With Validation</h6>
      <AnqPhoneNumberInput
        v-model="phoneNumber4"
        :rules="[val => !!val || 'Phone number is required']"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import AnqPhoneNumberInput from './components/AnqPhoneNumberInput.vue'
import type { ICountryData } from 'countries-list'

const phoneNumber = ref('')
const phoneNumber2 = ref('')
const phoneNumber3 = ref('')
const phoneNumber4 = ref('')

const onCountrySelect = (country: ICountryData) => {
  console.log('Selected country:', country.name)
}
</script>

<style>
.q-pa-md {
  max-width: 600px;
  margin: 0 auto;
}
</style>
