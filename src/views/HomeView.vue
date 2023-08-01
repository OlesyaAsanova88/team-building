<script setup>
</script>

<template>
  <main>
    <div class="wrapper">
      <div class="about">
         <img src="@/assets/img/resize.png" alt="taurus-my simbol" width="200">
         <h1>Олеся Асанова</h1>
         <p>Я опытный специалист во <strong>frontend разработке</strong>, креативный разработчик безумных идей и
            прекрасная
            мама :)</p>
         <p>Люблю <em>кататься на коньках, отдыхать на природе и проводить время в кругу близких и интересных
               людей</em>.
            Всегда готова к новым открытиям!</p>

         <h3>Мои соцсети =></h3>
         <a href="https://t.me/lesyaAsa" target="_blank">Telegram</a><br />
         <a href="https://www.instagram.com//olesya_asanova88" target="_blank">Instagram</a><br />
         <a href="https://vk.com/@id157253924" target="_blank">VK</a>
      </div>
      <div class="stack">
         <h2>Мой стек:</h2>
         <img src="@/assets/img/html-5 (1).png" alt="">
         <img src="@/assets/img/css-filetype.png" alt="">
         <img src="@/assets/img/javascript (1).png" alt="">
         <img src="@/assets/img/git.png" alt="">
         <img src="@/assets/img/github.png" alt="">
         <ul class="list">
            <li>HTML</li>
            <li>CSS</li>
            <li>SCSS</li>
            <li>Bootstrap</li>
            <li>JS</li>
            <li>VUE3 composition API</li>
            <li>GIT</li>
         </ul>
      </div>
      <div class="experience">
         <table class="grid">
            <h2>Мой опыт :</h2>
            <tr>
               <td>ПАО Сбербанк</td>
               <td>КБП</td>
               <td>2014-2017</td>
            </tr>
            <tr>
               <td>ПАО ПОЧТА БАНК</td>
               <td>Финансовый эксперт</td>
               <td>2017-2020</td>
            </tr>
            <tr>
               <td>ГУАП</td>
               <td>Программист</td>
               <td>2022-2023</td>
            </tr>
         </table>
      </div>

      <div class="contact">
         <h2>Связаться со мной</h2>
         <form action="">
            <div class="form-grup">
               <label for="name">Представьтесь:</label><br />
               <input type="text" id="name" placeholder="введите имя...">
            </div>
            <div class="form-grup">
               <label for="email">Email:</label><br />
               <input type="email" id="email" placeholder="введите email...">
            </div>
            <div class="form-grup">
               <label for="masege">Ваше сообщение:</label><br />
               <textarea id="masege" placeholder="введите текст.."></textarea>
            </div>
            <input class="btn" type="submit" value="Отправить мне вопрос">
         </form>
      </div>
   </div>
  </main>
</template>

<style scoped lang="scss">
.wrapper {
  color: #fff;
  width: 100vh;
  margin: 0 auto;
  align-items: center;
  text-align: center;
  padding: 50px;
  border: 3px solid #fff;
  box-shadow: 0 0 15px violet;
}
.about,
.stack,
.experience,
.contact {
  border: 3px solid #fff;
  box-shadow: 0 0 15px violet;
  max-width: 1400px;
  margin: 30px;
  padding: 30px;
}
.about img {
  border: 3px solid aqua;
  box-shadow: 0 0 15px violet;
}
.list {
  list-style: none;
  padding: 0;
  margin: 0;
}
.list li {
  margin-bottom: 10px;
}
.list li:hover {
  color: aqua;
}
.grid {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  border: 2px solid aqua;
  line-height: 3;
  padding: 45px;
  border-spacing: 15px;
}
.grid td {
  border-right: 1px solid #fff;
  padding-right: 20px;
  box-shadow: 0 0 15px violet;
}
.grid td:nth-last-child(3) {
  border-left: 1px solid #fff;
  padding-left: 20px;
}

a {
  color: aqua;
  cursor: pointer;
}
a:hover {
  color: violet;
}
a:visited {
  color: fuchsia;
}
.form-grup input {
  padding: 10px 45px;
  border-radius: 5px;
  box-sizing: border-box;
  outline: none;
  text-align: center;
}
.form-grup input:focus {
  border: 3px solid aqua;
  background-color: rgb(235, 170, 218);
}
.form-grup textarea {
  border-radius: 5px;
  text-align: center;
}
.form-grup textarea:focus {
  border: 3px solid aqua;
  background-color: rgb(235, 170, 218);
}

.btn {
  padding: 5px 15px;
  background-color: aqua;
  border-radius: 0 10px 0 10px;
  font-weight: bold;
  box-shadow: 0 0 15px violet;
  cursor: pointer;
}
.btn:hover {
  background-color: violet;
}

@media (max-width: 764px) {
  body {
     margin: 0;
     padding: 0;
  }
  .wrapper {
     width: 95%;
     margin: 0;
     padding: 5px;
     text-align: center;
     align-items: center;
  }
  .about,
  .stack,
  .experience,
  .contact {
     margin: 10px;
     padding: 10px;
  }
  .form-grup input {
     padding: 10px 15px;
  }
  .form-grup textarea {
     padding: 10px 15px;
  }
}
</style>
