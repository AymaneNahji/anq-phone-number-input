# An-Quasar Phone Number Input

A Vue 3 component for phone number input with country selection, built with Quasar Framework.

## Features

- Country selection with flag icons
- Phone number formatting
- Customizable labels
- Country exclusion support
- Built-in validation
- TypeScript support
- Quasar Framework integration

## Installation

```bash
npm install anq-phone-number-input
```

## Basic Usage

```vue
<template>
  <AnqPhoneNumberInput
    v-model="phoneNumber"
    @selectCountry="onCountrySelect"
  />
</template>

<script setup lang="ts">
import { ref } from 'vue'
import AnqPhoneNumberInput from 'an-quasar-phone-number-input'
import type { ICountryData } from 'countries-list'

const phoneNumber = ref('')

const onCountrySelect = (country: ICountryData) => {
  console.log('Selected country:', country.name)
}
</script>
```

## Props

| Prop | Type | Description |
|------|------|-------------|
| modelValue | string | The phone number value (v-model) |
| label | string | Label for the phone number input field |
| countryProps | object | Configuration for country selection |
| rules | array | Validation rules (compatible with Quasar's validation) |

### CountryProps Options

| Option | Type | Description |
|--------|------|-------------|
| label | string | Label for the country select field |
| defaultCountry | string | Default country code (e.g., 'US') |
| excludeCountries | string[] | Array of country codes to exclude |

## Events

| Event | Parameters | Description |
|-------|------------|-------------|
| selectCountry | ICountryData | Emitted when a country is selected |

## Examples

### Basic Usage
```vue
<AnqPhoneNumberInput
  v-model="phoneNumber"
  @selectCountry="onCountrySelect"
/>
```

### With Custom Labels
```vue
<AnqPhoneNumberInput
  v-model="phoneNumber"
  :countryProps="{
    label: 'Select Country',
    defaultCountry: 'US'
  }"
  label="Enter Phone Number"
/>
```

### With Excluded Countries
```vue
<AnqPhoneNumberInput
  v-model="phoneNumber"
  :countryProps="{
    excludeCountries: ['RU', 'CN'],
    defaultCountry: 'US'
  }"
/>
```

### With Validation
```vue
<AnqPhoneNumberInput
  v-model="phoneNumber"
  :rules="[val => !!val || 'Phone number is required']"
/>
```

## Dependencies

- Vue 3
- Quasar Framework
- countries-list

## License

MIT 