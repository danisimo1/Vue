<template>
  <div id="app">
    <div class="container">
      <h3>создания Клиента</h3>
      <label >Фамилия</label><br>
      <input placeholder="Фамилия" type="text" v-model="surname"><br><br>
      <label >Имя</label><br>
      <input placeholder="Имя" type="text" v-model="name"><br><br>
      <label >Отчество</label><br>
      <input placeholder="Отчество" type="text"><br><br>
      <label >Дата рождения</label><br>
      <input placeholder="Дата рождения" type="date" v-model="birthday"><br><br>
      <label >Номер телефона</label><br>
      <input placeholder="+7 XXX XXX-XX-XX" type="tel" v-model="phone_number"><br><br>
      <form>
        <p>Пол</p>
          <p><input name="sex" type="radio" value="male"> М</p>
          <p><input name="sex" type="radio" value="female"> Ж</p>
      </form>
      <p>Группа клиентов</p>
      <select multiple size ="3" v-model="customer_type">
        <option>VIP</option>
        <option>Проблемные</option>
        <option>ОМС</option>
      </select>
      <p>Лечащий врач</p>
      <select>
        <option>Иванов</option>
        <option>Захаров</option>
        <option>Чернышева</option>
      </select><br><br>
      <input type="checkbox">Не отправлять смс
    </div>
    
    <br><br>
    
    <div class="container">
      <h3>Адрес</h3>
      <label>Индекс</label><br>
      <input placeholder="XXX-XXX" type="text"><br><br>
      <label>Страна</label><br>
      <input type="text"><br><br>
      <label>Область</label><br>
      <input type="text"><br><br>
      <label>Город</label><br>
      <input v-model="city" type="text"><br><br>
      <label>Улица</label><br>
      <input type="text"><br><br>
      <label>Дом</label><br>
      <input type="text">
    </div>

    <br><br>

    <div class="container">
      <h3>Документы</h3>
      <p>Тип документа</p>
      <select v-model="document">
        <option>Паспорт</option>
        <option>Свидетельство о рождении</option>
        <option>Вод. удостоверение</option>
      </select><br><br>
      <label>Серия</label><br>
      <input placeholder="XXXX" type="text"><br><br>
      <label>Номер</label><br>
      <input placeholder="XXXXXX" type="text"><br><br>
      <label>Кем выдан</label><br>
      <input type="text"><br><br>
      <label>Дата выдачи</label><br>
      <input v-model="document_date" type="date">
    </div>
    <br><br>
    <div class="container">
      <h3>Введенные данные</h3>
      <p>Имя: {{name}}</p>
      <p>Фамилия: {{surname}}</p>
      <p>ДР: {{birthday}}</p>
      <p>НОМЕР: {{phone_number}}</p>
      <p>тип Клиента: {{customer_type[0]}}</p>
      <p>город: {{city}}</p>
      <p>документ: {{document}}</p>
      <p>дата документа: {{document_date}}</p>
    </div>
    <br><br>
  </div>
</template>

<script>
import useValidate from '@vuelidate/core'
import {required} from '@vuelidate/validators'

export default {
  name: 'App',
  data(){
    return {
      v$: useValidate(),
      name: '',
      surname: '',
      birthday: '',
      phone_number: '',
      customer_type: '',
      city: '',
      document: '',
      document_date: ''
    }
  },
  validations() {
    return {
      name: {required},
      surname: {required},
      birthday: {required},
      phone_number: {required},
      customer_type: {required},
      city: {required},
      document: {required},
      document_date: {required}
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  border: 1px solid gray;
  display: inline-block;
  padding: 20px;
}
</style>
