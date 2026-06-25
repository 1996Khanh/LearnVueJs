<script setup>
import { computed } from 'vue'

const props = defineProps({
  // Kiểu cơ bản: Number
  propA: Number,

  // Nhiều kiểu được phép: String HOẶC Number
  propB: [String, Number],

  // Bắt buộc phải truyền từ cha
  propC: {
    type: String,
    required: true,
  },

  // Không truyền thì dùng default 100
  propD: {
    type: Number,
    default: 100,
  },

  // Object / array
  propE: {
    type: Object,
  },

  // Custom validator — chỉ chấp nhận 3 giá trị
  propF: {
    type: String,
    validator(value) {
      return ['success', 'warning', 'error'].includes(value)
    },
  },

  // Function từ cha (JSON.stringify không in được → xem nút bên dưới)
  propG: {
    type: Function,
  },

  disable: Boolean,
})

// Gom props để in JSON (function → chuỗi mô tả)
const propsForJson = computed(() => ({
  propA: props.propA,
  propB: props.propB,
  propC: props.propC,
  propD: props.propD,
  propE: props.propE,
  propF: props.propF,
  propG: props.propG ? '[Function]' : null,
  disable: props.disable,
}))
</script>

<template>
  <section>
    <h3>Các loại prop (dễ hiểu)</h3>
    <ul>
      <li><strong>propA</strong> — Number: {{ propA }}</li>
      <li><strong>propB</strong> — String | Number: {{ propB }}</li>
      <li><strong>propC</strong> — required String: {{ propC }}</li>
      <li><strong>propD</strong> — Number + default: {{ propD }}</li>
      <li><strong>propE</strong> — Object: {{ propE?.message }}</li>
      <li><strong>propF</strong> — validator: {{ propF }}</li>
      <li><strong>propG</strong> — Function: {{ propG ? 'có' : 'không' }}</li>
      <li><strong>disable</strong> — Boolean: {{ disable }}</li>
    </ul>

    <p>JSON (function hiển thị dạng [Function]):</p>
    <p>{{ JSON.stringify(propsForJson) }}</p>

    <button type="button" :disabled="disable" @click="propG?.()">
      Gọi propG (xem Console)
    </button>
  </section>
</template>
