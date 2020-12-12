<template>
  <div class="page-content">
      <div class="header">
        <input class="serach_header" type="text" placeholder="Поиск по системе">
        <div class="avtor">
          <h4>Dmitry</h4>
          <p>Администратор</p>
        </div>
      </div>
      <div class="content-categories">
        <div class="label-wrapper">
          <input class="nav-item" name="nav" type="radio" id="opt-1">
          <label class="category" for="opt-1">Парамерты</label>
        </div>
        <div class="label-wrapper">
          <input class="nav-item" name="nav" type="radio" id="opt-1">
          <label class="category" for="opt-1">Вопросы</label>
        </div>
        <div class="label-wrapper">
          <input class="nav-item" name="nav" type="radio" id="opt-2">
          <label class="category" for="opt-2">Логика</label>
        </div>
        <div class="label-wrapper">
          <input class="nav-item" name="nav" type="radio" id="opt-3">
          <label class="category" for="opt-3">Условия</label>
        </div>
        <div class="label-wrapper">
          <input class="nav-item" name="nav" type="radio" id="opt-4" checked>
          <label class="category" for="opt-4">Респонденты</label>
        </div>

      </div>
      <div class="tasks-wrapper">
        <div v-if="conditionOne">
        <div class="task">
            <span class="label-text">Условие 1</span>
          <select class="input-task">
            <option selected disabled>Выберите респодента</option>
            <option value="Респодент 1">Респодент 1</option>
            <option value="Респодент 2">Респодент 2</option>
          </select>
        </div>
        <div class="task">
            <span class="label-text">Дипазон 1</span>
          <div class="mini-input-task">
            от <input type="text">
            до <input type="text">
          </div>
        </div>
        <div class="task" v-if="show">
          <span class="label-text">Дипазон 1</span>
          <div class="mini-input-task">
            от <input type="text">
            до <input type="text">
          </div>
        </div>
        <div class="button">
          <button class="add" v-on:click="show = !show">Добавить диапазон</button>
          <button class="delete" v-on:click="conditionOne = !conditionOne">Удалить условие</button>
        </div>
        </div>
        <div class="header upcoming"></div>
        <div v-if="conditionTwo">
        <div class="task">
          <span class="label-text"><b>Условие 2</b></span>
          <select class="input-task">
            <option selected disabled>Тип карты лояльности</option>
            <option value="Респодент 1">Карта 1</option>
            <option value="Респодент 2">Карта 2</option>
          </select>
        </div>
        <div class="task">
          <span class="label-text">тип</span>
          <select class="input-task">
            <option selected disabled>gold</option>
            <option value="Респодент 1">siler</option>
          </select>
        </div>
        <div class="task" v-if="showType">
          <span class="label-text">тип 2</span>
          <select class="input-task">
            <option selected disabled>gold</option>
            <option value="Респодент 1">siler</option>
          </select>
        </div>
        <div class="button">
          <button class="add" v-on:click="showType = !showType">Добавить диапазон</button>
          <button class="delete" v-on:click="conditionTwo = !conditionTwo">Удалить условие</button>
        </div>
        </div>
        <div class="header upcoming"></div>
        <div v-if="conditionThree">
        <div class="task">
          <span class="label-text"><b>Условие 3</b></span>
          <select class="input-task">
            <option selected disabled>Статус карты лояльности</option>
            <option value="Респодент 1">Статус 1</option>
            <option value="Респодент 2">Статус 2</option>
          </select>
        </div>
        <div class="task">
          <span class="label-text">статус 1</span>
          <select class="input-task">
            <option selected disabled>Активна</option>
            <option value="Респодент 1">Активна</option>
          </select>
        </div>
        <div class="task" v-if="showStatus">
          <span class="label-text">статус 2</span>
          <select class="input-task">
            <option selected disabled>Активна</option>
            <option value="Респодент 1">Активна</option>
          </select>
        </div>
        <div class="button">
          <button class="add" v-on:click="showStatus = !showStatus">Добавить диапазон</button>
          <button class="delete" v-on:click="conditionThree = !conditionThree">Удалить диапазон</button>
        </div>
        <div class="button-footer">
          <button class="testPool">Протестировать опрос</button>
        <button class="next">Далее</button>
        </div>
        </div>
      </div>
      </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      showType: false,
      showStatus: false,
      conditionOne: true,
      conditionTwo: true,
      conditionThree: true
    }
  }
  }
</script>

<style scoped>
.input-task {
  width: 80%;
  height: 2em;
  border: 1px solid #d1d1d1;
  position: relative;

}
.mini-input-task {
  display: inline-block;
  position: relative;
  left: -31rem;
}
.mini-input-task input {
  width: 8em;
  height: 2.5em;
}
.delete {
  float: right;
  height: 2.5rem;
  border: 1px solid #fe4d46;
  color: #fe4d46;
  background: none;
}
.add {
  position: relative;
  left: 15rem;
  height: 2.5rem;
  border: 1px solid #7dd21f;
  color: #7dd21f;
  background: none;
}
.testPool {
  float: left;
  margin-top: 15px;
  height: 2.5rem;
  width: 155px;
  border: 1px solid #ffffff;
  border-radius: 5px;
  color: #00b003;
  background: #ffffff;
  box-shadow: 0 0 5px rgba(0,0,0,0.3);
}
.next {
  float: right;
  margin-top: 15px;
  height: 2.5rem;
  width: 95px;
  border: 1px solid #00b003;
  border-radius: 5px;
  color: #ffffff;
  background: #00b003;
}
</style>
