<template>
  <div class="form-wrapper">
    <form @submit.prevent class="main-form">
      <label for="form-name" class="main-form__label">Name</label>
      <input
          v-model="formData.formName"
          type="text"
          id="form-name"
          name="form-name"
          class="main-form__input"
          required
      >
      <label for="form-phone" class="main-form__label">Phone</label>
      <input
          :value="formData.formNumber"
          v-imask="mask"
          @accept="onInputNumber"
          id="form-phone"
          name="form-phone"
          class="main-form__input"
          :pattern="numberRegExp"
          required
      >
      <label for="form-range" class="main-form__label">Temp</label>
      <input
          type="range"
          min="1"
          max="100"
          @input="getRangeColors"
          :style="{background: rangeColors}"
          v-model="formData.formTemp"
          id="form-range"
          name="form-range"
          class="main-form__range"
          list="values"
          required
      >
      <label for="form-comments" class="main-form__label">Comments</label>
      <input
          v-model="formData.formComments"
          type="text" id="form-comments"
          name="form-comments"
          class="main-form__input"
      >
      <div class="main-form__footer">
        <button @click="sendForm" type="submit" class="main-form__button">CALL ME</button>
        <p class="main-form__message">
          By pressing "Send" button
          <br>
          I agree with
          <a class="main-form__footer_link" href="#">Privacy Policy</a>
        </p>
      </div>
    </form>
  </div>
</template>

<script>
import {IMaskDirective} from 'vue-imask'
export default {
  directives: {
    imask: IMaskDirective
  },

  data() {
    return {
      numberRegExp: '^((8|\\+7)[\\- ]?)?(\\(?\\d{3}\\)?[\\- ]?)?[\\d\\- ]{10}$',
      formData: {
        formName: '',
        formNumber: '',
        formTemp: 50,
        formComments: ''
      },
      mask: {
        mask: '{+7}{ (}000{) }000{-}00{-}00',
        lazy: true
      },
      rangeColors: `linear-gradient(90deg, #FF69B4 50%, #5BAAF9 50%)`,
    }
  },

  methods: {
    getRangeColors() {
      this.rangeColors = `linear-gradient(90deg, #FF69B4 ${this.formData.formTemp}%, #5BAAF9 ${this.formData.formTemp}%)`
    },

    onInputNumber (event) {
      const maskRef = event.detail;
      this.formData.formNumber = maskRef.value;
    },

    sendForm() {
      const pattern = new RegExp(this.numberRegExp)
      if (pattern.test(this.formData.formNumber) && this.formData.formName) {
        setTimeout(() => {
          console.log('Валидация прошла успешно. Данные в формате JSON-строки:', JSON.stringify(this.formData))
          this.formData.formNumber = this.formData.formName = this.formData.formComments = ''
          this.formData.formTemp = 50
          this.getRangeColors()
        }, 300)
      } else {
        console.log('Ошибка. Форма заполнена некорректно')
      }
    }
  }
}
</script>

<style scoped>
.form-wrapper {
  margin-top: 200px;
}

.main-form {
  position: relative;
  width: 100%;
}

.main-form input {
  margin-bottom: 50px;
}

.main-form__label {
  display: block;
  letter-spacing: 0.05em;
  font-size: 14px;
}

.main-form__input,
.main-form__range {
  width: 548px;
}

.main-form__range {
  position: relative;
}

.main-form__input {
  height: 30px;
  background: none;
  border-bottom: 1px solid rgba(233, 238, 230, 0.5);
  filter: drop-shadow(4px 0px 4px rgba(0, 0, 0, 0.25));
  font-size: 18px;
}

.main-form__input:focus {
  outline: none;
  border-bottom: 1px solid rgba(222, 222, 115, 0.75);
}

input[type="range"] {
  -webkit-appearance: none;
  height: 1px;
  margin-top: 20px;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  box-sizing: content-box;
  width: 1px;
  height: 1px;
  scale: 12;
  margin: 4px;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background-color: #B6A16B;
  background-clip: padding-box;
  border: 2px solid transparent;
  cursor: ew-resize;
}

input[type="range"]::-moz-range-thumb {
  -webkit-appearance: none;
  box-sizing: content-box;
  width: 1px;
  height: 1px;
  scale: 12;
  margin: 4px;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background-color: #B6A16B;
  background-clip: padding-box;
  border: 2px solid transparent;
  cursor: ew-resize;
}

.main-form__range::before,
.main-form__range::after {
  position: absolute;
  top: 12px;
  font-size: 9px;
  letter-spacing: 0.05em;
}

.main-form__range::after {
  content: 'cold';
  right: 0;
}

.main-form__range::before {
  content: 'hot';
  left: 0;
}

.main-form__footer {
  display: flex;
  align-items: center;
  padding-top: 86px;
}

.main-form__button {
  width: 173px;
  height: 56px;
  margin-right: 72px;
  border-radius: 100px;
  background: none;
  border: 1px solid #EEEBE6;
}

.main-form__button:hover {
  cursor: pointer;
}

.main-form__button:active {
  color: #B6A16B;
  border: 1px solid #B6A16B;
}

.main-form__message {
  letter-spacing: 0.05em;
  line-height: 150%;
  font-size: 13px;
}

.main-form__footer_link {
  color: #FF69B4;
}

@media (max-width: 1200px) {
  .main-form__footer {
    padding-top: 50px;
  }
}

@media (max-width: 1000px) {
  .form-wrapper {
    margin: 50px auto 0;
  }

  .main-form__footer {
    padding-top: 10px;
    display: flex;
    flex-direction: column;
  }

  .main-form__button {
    width: 100%;
    height: 40px;
    margin: 0 0 20px;
  }
}

@media (max-width: 600px) {
  .main-form__input,
  .main-form__range {
    width: 100%;
  }

  .form-wrapper {
    width: 100%;
  }

  .main-form__message {
    font-size: 10px;
  }
}
</style>