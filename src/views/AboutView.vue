<script setup>
import { ref } from "vue";

const players = ref([
  {
    id: 164679,
    name: "Руслан",
    surname: "Иванов",
    birthday: "2009-07-07",
  },
  {
    id: 163246,
    name: "Артем",
    surname: "Пулов",
    birthday: "1998-08-09",
  },
  {
    id: 164535,
    name: "Иван",
    surname: "Путров",
    birthday: "2007-04-10",
  },
  {
    id: 163604,
    name: "Александр",
    surname: "Назаров",
    birthday: "2004-10-06",
  },
  {
    id: 163636,
    name: "Иван",
    surname: "Киселев",
    birthday: "2005-10-29",
  },
  {
    id: 164836,
    name: "Ольгерд",
    surname: "Ковенко",
    birthday: "2006-12-25",
  },
  {
    id: 164101,
    name: "Павел",
    surname: "Кондратьев",
    birthday: "1985-10-20",
  },
  {
    id: 164457,
    name: "Иван",
    surname: "Ковенко",
    birthday: "2006-07-18",
  },
  {
    id: 162937,
    name: "Александр",
    surname: "Миронов",
    birthday: "2000-03-29",
  },
  {
    id: 164009,
    name: "Артем",
    surname: "Красковский",
    birthday: "1985-10-20",
  },
]);
const groups = ref([
  {
    group_id: 1,
    players: [],
  },
  {
    group_id: 2,
    players: [],
  },
  {
    group_id: 3,
    players: [],
  },
]);

const moveToGroup = (player) => {
  const result = groups.value.reduce((acc, item) => {
    if (item.players.length === 3) return acc;
    if (acc === undefined) return;

    item.players.push(player);
    return undefined;
  }, player);

  if (result === undefined) {
    players.value = filteredById(players.value, player.id);
  }
};

const filteredById = (array, id) => {
  return array.filter((item) => item.id !== id);
};

const moveFromGroup = (player, group) => {
  players.value.push(player);
  group.players = filteredById(group.players, player.id);
};

const submitBtn = (e) => {
  if(groups.value[0].players.length === 3 && groups.value[1].players.length === 3 && groups.value[2].players.length === 3) {
    alert('Данные отправлены. Команды распределены.')
  }
  else {
    alert('Данные не отправлены. Команды не распределены.')
  }
  
};
</script>
<template>
  <div class="main">
    <div class="container">
      <table class="mt-5 table table-dark table-striped table-hover">
        <thead>
          <tr>
            <th scope="col">Номер</th>
            <th scope="col">Участник</th>
            <th scope="col">Дата рождения</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="player in players" :key="player.id" @click="moveToGroup(player)">
            <th scope="row">{{ player.id }}</th>
            <td>{{ player.name }} {{ player.surname }}</td>
            <td>{{ player.birthday }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="container mt-5">
      <form action="">
        <div class="row d-flex justify-content-between">
          <div class="col-md-4 col-sm-12">
            <div class="card mb-3">
              <div class="card-body" v-for="group in groups" :key="group.group_id">
                <h5 class="card-title">Группа: {{ group.group_id }}</h5>
                <p
                  class="card-text"
                  v-for="player in group.players"
                  :key="player"
                  @click="moveFromGroup(player, group)"
                >
                  {{ player.name }} {{ player.surname }} {{ player.birthday }}
                </p>
              </div>
            </div>
          </div>
        </div>

        <div class="btn-block">
          <button class="btn-submit" type="submit" @click.prevent="submitBtn">
            Сохранить
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  font-family: "Prata", sans-serif;
}
.btn-block {
  margin-top: 30px;
  display: flex;
  justify-content: center;
}
.btn-submit {
  padding: 8px 55px;
  border: none;
  border-radius: 5px;
  color: teal;
  background-color: #fff;
  box-shadow: 0 0 15px teal;
}
.btn-submit:hover {
  color: #fff;
  background-color: rgb(39, 199, 151);
}
.card-title {
  border-bottom: 1px solid teal;
}
</style>
