<template>
  <el-row type="flex" justify="center" class="portfolio">
    <el-col :xs="0" :sm="1" :md="1" :lg="1" :xl="1">
      <div class></div>
    </el-col>
    <el-col :xs="24" :sm="24" :md="6" :lg="6" :xl="6">
      <div class="portfolio__left-side">
        <img src="../assets/photo.jpg" alt />
        <span class="portfolio__left-side--title">
          Sedov Maxim
          <br />
          <el-tag>& I AM FRONTEND VUE DEVELOPER</el-tag>
        </span>
        <el-divider></el-divider>
        <div class="portfolio__left-side--links">
          <a href="https://vk.com/sedovmax" target="_blank">
            <img src="https://i.ibb.co/MBFzMcw/vk-2.png" alt="vk" border="0" />
          </a>
          <a href="https://www.instagram.com/sdvmxm" target="_blank">
            <img src="https://i.ibb.co/r2wt2gc/instagram.png" alt="instagram" border="0" />
          </a>
          <a href="https://t.me/sdvmxm" target="_blank">
            <img src="https://i.ibb.co/RcJfZsr/telegram-1.png" alt="telegram" border="0" />
          </a>
          <a href="https://github.com/MaximSedov" target="_blank">
            <img src="https://i.ibb.co/ZdzCdF9/github.png" alt="github" border="0" />
          </a>
        </div>
        <el-divider></el-divider>
        <span class="portfolio__left-side--text">
          <strong>ЧТО Я МОГУ?</strong>
          <br />
          <br />Спроектирую и разработаю сайт, приложение под Ваши предпочтения
          на современном фреймворке VUE 3. Подарите своим клиентам новый опыт
          взаимодействия с компанией с помощью продуманного функционала и
          дизайна.
        </span>
        <el-divider></el-divider>
        <div class="portfolio__left-side--button">
          <el-button @click="open">Оставить заявку</el-button>
        </div>
      </div>
    </el-col>
    <el-col :xs="0" :sm="1" :md="1" :lg="1" :xl="1">
      <div class></div>
    </el-col>
    <el-col :xs="24" :sm="24" :md="15" :lg="15" :xl="15">
      <div class="portfolio__right-side">
        <div class="portfolio__right-side--navbar">
          <ul>
            <a href v-scroll-to="{ el: '#about', offset: -95 }">
              <li>Обо мне</li>
            </a>
            <a href v-scroll-to="{ el: '#skills', offset: -95 }">
              <li>Навыки</li>
            </a>
            <a href v-scroll-to="{ el: '#education', offset: -95 }">
              <li>Образование</li>
            </a>
            <a href v-scroll-to="{ el: '#portfolio', offset: -95 }">
              <li>Портфолио</li>
            </a>
          </ul>

          <el-progress color="#da7f8f" :show-text="false" :percentage="percentage * 100"></el-progress>
        </div>
        <div class="portfolio__right-side--navbar_mobile">
          <el-button @click="drawer = true">
             <menuIcon :height="24" :width="24"/>
          </el-button>
        </div>

        <el-drawer show-close v-model="drawer" direction="ttb" size="100%">
          <div class>
            <a @click="drawer = false" v-scroll-to="{ el: '#about', offset: -80 }" href="#">Обо мне</a>
          </div>
          <div class>
            <a @click="drawer = false" v-scroll-to="{ el: '#skills', offset: -80 }" href="#">Навыки</a>
          </div>
          <div class>
            <a @click="drawer = false" v-scroll-to="{ el: '#education', offset: -80 }" href="#">Образование</a>
          </div>
          <div class>
            <a @click="drawer = false" v-scroll-to="{ el: '#portfolio', offset: -80 }" href="#">Портфолио</a>
          </div>
        </el-drawer>

        <div class="portfolio__right-side--block">
          <el-row class="portfolio__right-side--block--home" type="flex" justify="center" align="middle">
            <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
              <span class="title">Hello.</span>
              <br />
              <span class="subtitle">My name is Maxim</span>
              <br />
              <span class="subtitle--who">
                & I AM
                <strong>FRONTEND VUE DEVELOPER</strong>
              </span>
            </el-col>
            <el-col :xs="0" :sm="0" :md="12" :lg="12" :xl="12"></el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="about">
          <el-row class="portfolio__right-side--block--about">
            <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
              <div class="title">
              <profile :height="40" :width="40"/> <div>Обо мне</div>
              </div>
              <br />
              <span class="text">
                Опыт в WEB-разработке получал в процессе учебы в колледже, также
                на основаниях собственной инициативы (на протяжении 3 лет) через
                онлайн курсы, проходил некоторое множество интенсивов, сейчас
                занимаюсь развитием во vue.js 3 версии.
                <br />
                <br />Принимал участие в чемпионате WorldSkills (Компетенция
                Web-дизайн - 3 место в регионе, Компетенция Прототипирование -1
                место в регионе и отбор на нац.финал (апрель 2018))
                <br />
                <br />Предпочтительное направление в работе - разработка сайтов,
                интерфейсов, приложений на языке JavaScript ( HTML + CSS) с
                применением vue.js 3.
              </span>
            </el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="skills">
          <el-row class="portfolio__right-side--block--skills">
            <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
              <div class="title">
              <logic :height="40" :width="40"/> <div>Навыки</div>
              </div>
              <br />
              <el-row>
                <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12" style="font-size: 1.2rem">
                  <span>HTML</span>
                  <el-progress color="#da7f8f" :percentage="98"></el-progress>
                  <br />
                  <span>CSS</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>BOOTSTRAP</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>ELEMENT UI</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>NAIVE UI</span>
                  <el-progress color="#da7f8f" :percentage="90"></el-progress>
                  <br />
                  <span>FIGMA</span>
                  <el-progress color="#da7f8f" :percentage="65"></el-progress>
                  <br />
                  <span>IONIC</span>
                  <el-progress color="#da7f8f" :percentage="98"></el-progress>
                  <br />
                  <span>CAPACITOR</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>APPWRITE</span>
                  <el-progress color="#da7f8f" :percentage="80"></el-progress>
                  <br />
                </el-col>
                <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12" style="font-size: 1.2rem">
                  <span>PHP</span>
                  <el-progress color="#da7f8f" :percentage="25"></el-progress>
                  <br />
                  <span>PostgreSQL</span>
                  <el-progress color="#da7f8f" :percentage="75"></el-progress>
                  <br />
                  <span>JS</span>
                  <el-progress color="#da7f8f" :percentage="80"></el-progress>
                  <br />
                  <span>PINIA</span>
                  <el-progress color="#da7f8f" :percentage="90"></el-progress>
                  <br />
                  <span>VUE 3</span>
                  <el-progress color="#da7f8f" :percentage="95"></el-progress>
                  <br />
                  <span>VUEUSE</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>FIREBASE</span>
                  <el-progress color="#da7f8f" :percentage="50"></el-progress>
                  <br />
                  <span>SUPABASE</span>
                  <el-progress color="#da7f8f" :percentage="85"></el-progress>
                  <br />
                  <span>DevOps</span>
                  <el-progress color="#da7f8f" :percentage="15"></el-progress>
                  <br />
                </el-col>
              </el-row>
            </el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="education">
          <el-row class="portfolio__right-side--block--education">
            <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
              <div class="title">
              <document :height="40" :width="40"/> <div>Учеба</div>
              </div>
              <br />
              <el-collapse accordion>
                <el-collapse-item name="1">
                  <template #title>Колледж</template>
                  <div>
                    Учился по специальности "Программирование в компьютерных
                    системах" на протяжении 4 лет. За время учебы был номирован
                    на Президентскую стипендию. Участвовал в различных
                    олимпиадах, научных проектах и конкурсах, в т.ч.
                    WorldSkills.
                  </div>
                </el-collapse-item>
                <el-collapse-item name="2">
                  <template #title>Университет</template>
                  <div>
                    Имею диплом о высшем образовании (бакалавр) по
                    направлению "Прикладная информатика".
                  </div>
                </el-collapse-item>
                <el-collapse-item name="3">
                  <template #title>Курсы</template>
                  <div>
                    Прошел целое множество разнообразных курсов, расширяя свои навыки и продолжаю познавать новое. 
                  </div>
                </el-collapse-item>
                <el-collapse-item name="4">
                  <template #title>Работа</template>
                  <div>
                    На данный момент работаю на коммерческом проекте.
                  </div>
                </el-collapse-item>
              </el-collapse>
            </el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="portfolio">
          <el-row class="portfolio__right-side--block--portfolio">
            <el-col :span="24">
              <div class="title">
              <cubic :height="40" :width="40"/> <div>Портфолио</div>
              </div>
              <br />
              <el-row>
                <el-col class="techstore" :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
                  <span class="portfolio_text">
                    <span class="portfolio_titletext">TECH STORE</span>
                    <br />
                    <span class="portfolio_subtext">магазин электроники</span>
                  </span>
                </el-col>
                <el-col class="ais" :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
                  <span class="portfolio_text">
                    <span class="portfolio_titletext">AIS</span>
                    <br />
                    <span class="portfolio_subtext">система по создания курсов</span>
                  </span>
                </el-col>
                <el-col class="booking" :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
                  <span class="portfolio_text">
                    <span class="portfolio_titletext">BOOKING</span>
                    <br />
                    <span class="portfolio_subtext">бронирование жилых помещений</span>
                  </span>
                </el-col>
                <el-col class="switter" :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
                  <span class="portfolio_text">
                    <span class="portfolio_titletext">SWITTER</span>
                    <br />
                    <span class="portfolio_subtext">пародия на твиттер</span>
                  </span>
                </el-col>
              </el-row>
              <el-row>
                <el-col class="portfolio__right-side--block--portfolio__button">
                  <el-button @click="openProjects">Открыть подробнее</el-button>
                </el-col>
              </el-row>
            </el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="rewiew">
          <el-row class="portfolio__right-side--block--rewiew">
            <el-col :span="24">
              <span class="title">
                <i class="el-icon-s-comment"></i> Отзывы
              </span>
              <br />
            </el-col>
          </el-row>
        </div>
        <div class="portfolio__right-side--block" id="contacts">
          <el-row class="portfolio__right-side--block--contacts">
            <el-col :span="24">
              <span class="title">
                <i class="el-icon-phone-outline"></i> Контакты
              </span>
              <br />
            </el-col>
          </el-row>
        </div>
      </div>
    </el-col>
    <el-col :xs="0" :sm="1" :md="1" :lg="1" :xl="1">
      <div class></div>
    </el-col>
  </el-row>
</template>


<script>
import { useSnakke } from 'vue-snakke'
const { progress } = useSnakke()
import logic from '../components/icons/logic.vue'
import document from '../components/icons/file-text.vue'
import cubic from '../components/icons/grid-interface.vue'
import profile from '../components/icons/profile-1.vue'
import menuIcon from '../components/icons/menu.vue'

export default 
  {
  data() {
    return {
      percentage: progress,
      drawer: false
    }
  },
  methods: {
    progressBar() {
      console.log('scroll')
      this.percentage = 25
    },
    open() {
      this.$alert('Я жду Вашего сообщения в ВК или Телеграме', 'Написать', {
        confirmButtonText: 'OK'
      })
    },
    openProjects(){
      this.$router.push('/projects')
    }
  },
  components:{
    logic, document, cubic, profile, menuIcon
  }
}
</script>

<style lang="scss">
$mainBackground: #e1e5ea;
$cardBackground: #faf3f3;
$headerColor: #a7bbc7;
$elementColor: #da7f8f;
$white: #ffffff;
$textColor: #2c3e50;
.portfolio {
  margin-top: 60px;
  &__left-side {
    background-color: $cardBackground;
    border-radius: 1rem;
    padding: 2rem;
    position: sticky;
    top: 1rem;
    overflow-y: scroll;
    img {
      width: 100%;
      border-radius: 2rem;
    }
    &--title {
      padding-top: 2rem;
      padding-bottom: 2rem;
      display: block;
      font-size: 2rem;
      text-align: center;
      text-transform: uppercase;
      .el-tag {
        color: $elementColor;
        border-color: $elementColor;
        background-color: $cardBackground;
      }
    }
    &--links {
      padding-top: 1rem;
      padding-bottom: 1rem;
      display: block;
      font-size: 1rem;
      text-align: center;
      a {
        display: inline-block;
        font-size: 0.5rem;
        img {
          border-radius: 0;
          width: 50%;
        }
        img:hover {
          transform: scale(1.1);
          cursor: pointer;
        }
      }
    }
    &--text {
      padding-top: 2rem;
      padding-bottom: 2rem;
      display: block;
      font-size: 1.2rem;
      text-align: left;
    }
    &--button {
      padding-top: 2rem;
      padding-bottom: 2rem;
      display: block;
      text-align: center;
      button,
      button:focus {
        font-size: 1.4rem;
        background-color: $elementColor;
        color: $white;
        border-color: $elementColor;
      }
      button:hover {
        background-color: $headerColor;
        color: $white;
        border-color: $headerColor;
      }
    }
  }
  &__right-side {
    &--navbar {
      z-index: 1;
      border-radius: 1rem 1rem 0 0;
      position: sticky;
      top: 0;
      text-align: center;
      box-sizing: border-box;
      height: 85px;
      line-height: 80px;
      background-color: $cardBackground;
      margin-bottom: 2rem;
      ul {
        display: block;

        a {
          text-decoration: none;
          color: $headerColor;
          font-weight: bold;
        }
        li {
          display: inline-block;
          font-size: 1.2rem;
          padding-right: 2rem;
          padding-left: 2rem;
          transition: all 0.3s ease-out;
        }
        li:hover,
        li:focus,
        li:active {
          background-color: $elementColor;
          color: $white;
          cursor: pointer;
        }
      }
    }
    &--navbar_mobile {
      display: none;
      z-index: 1;
      border-radius: 1rem 1rem 0 0;
      position: sticky;
      top: 1rem;
      text-align: right;
      box-sizing: border-box;
      margin-bottom: 1rem;
      margin-top: 1rem;
      margin-right: 1rem;
      button,
      button:focus {
        background-color: $white;
        color: $white;
        border: none;
      }
      button:hover {
        background-color: $headerColor;
        color: $white;
        border: none;
      }
    }
    .el-drawer {
      div {
        margin-bottom: 30px;
        text-align: center;
      }
      a {
        text-decoration: none;
        color: $elementColor;
        font-size: 2.5rem;
      }
    }
    &--block {
      border-radius: 1rem;
      min-height: 25rem;
      background-color: $cardBackground;
      margin-bottom: 2rem;
      padding: 2rem;
      &--home {
        background-image: url('../assets/perfect.png');
        background-repeat: no-repeat;
        background-position: center right;
        height: 25rem;
        .title {
          font-size: 5rem;
          font-weight: bold;
        }
        .subtitle {
          font-size: 3rem;
          font-weight: 400;
        }
        .subtitle--who {
          font-size: 2rem;
          font-weight: 200;
          text-transform: lowercase;
          color: $elementColor;
        }
      }
      &--about {
        height: 100%;
        .title {
          display: flex;
          align-items: center;
          font-size: 2.5rem;
          font-weight: bold;
          i {
            color: $elementColor;
          }
          div{
            margin-left: 1rem;
          }
        }
        .text {
          font-size: 1.2rem;
        }
      }
      &--skills {
        height: 100%;
        .title {
          display: flex;
          align-items: center;
          font-size: 2.5rem;
          font-weight: bold;
          i {
            color: $elementColor;
          }
          div{
            margin-left: 1rem;
          }
        }
      }
      &--education {
        height: 100%;
        .title {
           display: flex;
          align-items: center;
          font-size: 2.5rem;
          font-weight: bold;
          i {
            color: $elementColor;
          }
          div{
            margin-left: 1rem;
          }
        }
        .el-collapse-item__header {
          font-size: 1.4rem;
          padding: 1rem;
          background-color: $mainBackground;
        }
        .el-collapse-item__header:hover,
        .el-collapse-item__header:focus {
          color: $elementColor;
        }
        .el-collapse-item__content {
          font-size: 1.2rem;
          padding: 1rem;
          background-color: $cardBackground;
        }
      }
      &--portfolio {
        height: 100%;
        .title {
          display: flex;
          align-items: center;
          font-size: 2.5rem;
          font-weight: bold;
          i {
            color: $elementColor;
          }
          div{
            margin-left: 1rem;
          }
        }
        .portfolio_text {
          height: 15rem;
          text-align: center;
          color: $white;
          display: flex;
          align-items: center;
          justify-content: center;
          .portfolio_titletext {
            width: 100%;

            font-size: 2rem;
            font-weight: bold;
          }
          .portfolio_subtext {
            width: 100%;

            font-size: 1.2rem;
            font-weight: 200;
          }
        }
        .switter {
          background-color: $elementColor;
          background-repeat: no-repeat;
          background-position: center center;
          background-size: 100%;
          height: 15rem;
          transition: all 1s ease-out;
          border-radius: 1rem;
        }
        .switter:hover {
          background-image: url('../assets/switter.png');
        }
        .switter:hover .portfolio_text {
          display: none;
        }
        .ais {
          background-color: $headerColor;
          background-repeat: no-repeat;
          background-position: center center;
          background-size: 100%;
          height: 15rem;
          transition: all 1s ease-out;
          border-radius: 1rem;
        }
        .ais:hover {
          background-image: url('../assets/ais.png');
        }
        .ais:hover .portfolio_text {
          display: none;
        }
        .techstore {
          background-color: $elementColor;
          background-repeat: no-repeat;
          background-position: center center;
          background-size: 100%;
          height: 15rem;
          transition: all 1s ease-out;
          border-radius: 1rem;
          margin-bottom: 1rem;
        }
        .techstore:hover {
          background-image: url('../assets/techstore.png');
        }
        .techstore:hover .portfolio_text {
          display: none;
        }
        .booking {
          background-color: $headerColor;
          background-repeat: no-repeat;
          background-position: center center;
          background-size: 100%;
          height: 15rem;
          transition: all 1s ease-out;
          border-radius: 1rem;
        }
        .booking:hover {
          background-image: url('../assets/booking.png');
        }
        .booking:hover .portfolio_text {
          display: none;
        }
        &__button {
          padding-top: 2rem;
          display: block;
          text-align: center;
          button,
          button:focus {
            font-size: 1.4rem;
            background-color: $elementColor;
            color: $white;
            border-color: $elementColor;
          }
          button:hover {
            background-color: $headerColor;
            color: $white;
            border-color: $headerColor;
          }
        }
      }
      &--rewiew {
        height: 100%;
        .title {
          font-size: 2.5rem;
          font-weight: bold;
          display: block;
          i {
            color: $elementColor;
          }
        }
      }
      &--contacts {
        height: 100%;
        .title {
          font-size: 2.5rem;
          font-weight: bold;
          display: block;
          i {
            color: $elementColor;
          }
        }
      }
    }
  }
}
#contacts,
#rewiew {
  display: none;
}
.el-message-box {
  &__title {
    font-size: 2rem !important;
    font-family: 'Nunito', sans-serif !important;
  }
  &__message {
    font-size: 1.2rem;
    font-family: 'Nunito', sans-serif;
  }
  button.el-button--primary,
  button.el-button--primary:focus {
    font-size: 1.2rem;
    background-color: $elementColor;
    color: $white;
    border-color: $elementColor;
  }
  button.el-button--primary:hover {
    background-color: $headerColor;
    color: $white;
    border-color: $headerColor;
  }
}
@media (max-width: 1500px) {
  .portfolio__right-side--navbar ul li {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
@media (max-width: 1200px) {
  .portfolio__right-side--navbar {
    display: none;
  }
  .portfolio__right-side--navbar_mobile {
    display: block;
  }
}
@media (max-width: 992px) {
  .portfolio__left-side {
    overflow-y: visible;
  }
  .portfolio__right-side--block--home {
    background: none;
  }
  #app {
    margin-top: 0;
  }
  .portfolio__right-side--block--portfolio {
    .techstore,
    .ais,
    .techstore,
    .booking {
      margin-bottom: 1rem;
    }
  }
  .el-message-box {
    width: 100% !important;
  }
}
</style>
