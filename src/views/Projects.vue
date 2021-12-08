<template>
  <div class="projects">
    <div class="projects_header">
      <div class="backtohome" @click="openHome">
        <arrow-back :height="24" :width="24" />
      </div>
     <!--  <div class="filters"></div> -->
    </div>

    <div class="projects_content">
      <el-row :gutter="20">
        <el-col v-for="(project, index) in projects" :key="project.index" :xs="24" :sm="12" :md="8" :lg="6" :xl="6" class="projects_content-card">
          <div class="body" @click="openProjectInfo(project)">
            <div class="tags">
              <el-tooltip effect="light" class="item" :content="complexityTransform(project.complexity)" placement="right">
                <div class="complexity" :class="'active-'+project.complexity">
                  <div></div>
                  <div></div>
                  <div></div>
                </div>
              </el-tooltip>

              <div style="display:flex">
                <span v-for="(tag, index) in project.tags" :key="tag.index" :class="tag">{{tag}}</span>
              </div>
            </div>
            <div class="image" :style="{backgroundImage: `url(${require('@/assets/' + project.image)}`}"></div>
            <div class style="position:absolute;box-sizing:border-box;bottom:0;padding:0.5rem; width:100%;display:flex; justify-content:space-between;align-items:end">
              <div class="title">
                <div class="stack">
                  <span v-for="(item, index) in project.stack" :key="item.index">{{item}}</span>
                </div>
                <div class="text">{{project.title}}</div>
              </div>
              <div class="date">{{project.date}}</div>
            </div>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
  <el-drawer v-model="drawer" title="Описание проекта" direction="btt" size="100%">
    <el-row class="actual_project-info">
      <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12">
        <div style="display: flex; justify-content: space-between; align-items:center">
          <div class="actual_project-info__stack">
            <el-tooltip effect="light" class="item" :content="complexityTransform(actualProject.complexity)" placement="right">
              <div class="complexity" :class="'active-'+actualProject.complexity">
                <div></div>
                <div></div>
                <div></div>
              </div>
            </el-tooltip>
            <span v-for="(item, index) in actualProject.stack" :key="item.index">{{item}}</span>
          </div>
          <div class="actual_project-info__tags">
            <span v-for="(tag, index) in actualProject.tags" :key="tag.index" :class="tag">{{tag}}</span>
          </div>
        </div>
        <div class="actual_project-info__title">{{actualProject.title}}</div>
        <div class="actual_project-info__date">Дата опубликования: {{actualProject.date}}</div>
        <div class="actual_project-info__description">
          <b>Описание:</b>
          <br />
          <p v-for="(description, index) in actualProject.description" :key="description.index"> {{description}}</p>
        </div>
        <div class="actual_project-info__tech">
          <b>Технологии:</b>
          <br />
          <span v-for="(item, index) in actualProject.stack" :key="item.index">
            <div class="item">
              <span>{{item}}</span>
              {{' - ' + actualProject.tech[index]}}
            </div>
          </span>
        </div>
        <div class="actual_project-info__links">
          <b>Просмотр:</b>
          <br />
          <div v-if="actualProject.links.length>0">
            <el-link target="_blank" :href="'https://'+item" type="info" v-for="(item, index) in actualProject.links" :key="item.index">{{item}}</el-link>
          </div>
          <div class v-else>
            <el-link target="_blank" href type="info">Недоступно для просмотра</el-link>
          </div>
        </div>
        <div class="actual_project-info__button">
          <div @click="drawer = false" class="">Закрыть</div>
        </div>
      </el-col>
      <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" style="background-color: #e1e5ea; border-radius: 0.5rem">
        <div class="actual_project-info__image">
          <div class="demo-image__preview">
            <el-image style="width: 100%; height: 100%" :src="require('@/assets/' + actualProject.image)" :preview-src-list="[require('@/assets/' + actualProject.image)]"></el-image>
          </div>
        </div>
      </el-col>
    </el-row>
  </el-drawer>
</template>
<script>
import ArrowBack from '../components/icons/arrow_back.vue'
export default {
  data() {
    return {
      drawer: false,
      actualProject: {},
      projects: [
        {
          title: 'ИТ Продукт',
          sortDate: '202111',
          date: '11.2021',
          tags: ['Landing', 'Practice'],
          image: 'product.png',
          complexity: 1,
          stack: ['HTML+CSS','VUE','ELEMENT-UI', 'xicons', 'A&R'],
          description:['Практический проект представляет собой верстку лэндинга - презентацию разработанного мобильного приложения.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'пакет иконок', 'адаптивность и резиновость'],
          links: ['sdvmxm.ru/product', 'github.com/MaximSedov/product'],
        },
        {
          title: 'Пародия на твиттер',
          sortDate: '201807',
          date: '07.2018',
          tags: ['SPA', 'Practice'],
          image: 'switter.png',
          complexity: 2,
          stack: ['HTML+CSS', 'PHP'],
          description: ['Реализован функционал публикации сообщений на общей странице при авторизации под личным аккаунтом. Подсчет общего количества сообщений, авторство и дата/время над сообщением, уведомления об успешной/безуспешной работе.'],
          tech: ['разметка', 'серверный язык программирования'],
          links: [],
        },
        {
          title: 'Аренда жилья',
          sortDate: '201906',
          date: '06.2019',
          tags: ['Practice'],
          image: 'booking.png',
          complexity: 1,
          stack: ['HTML+CSS'],
          description: ['В рамках практики.'],
          tech: ['разметка'],
          links: [],
        },
        {
          title: 'АИС по созданию курсов',
          sortDate: '201906',
          date: '06.2019',
          tags: ['Multi-page', 'Production'],
          image: 'ais.png',
          complexity: 3,
          stack: ['HTML+CSS','PHP', 'Font-Awesome', 'A&R'],
          description: ['Автоматизированная информационная система по созданию курсов. Дипломный проект.'],
          tech: ['разметка', 'серверный язык программирования', 'иконки', 'адаптивность и резиновость'],
          links: [],
        },
        {
          title: 'Магазин электроники',
          sortDate: '201905',
          date: '05.2019',
          tags: ['Practice'],
          image: 'techstore.png',
          complexity: 1,
          stack: ['HTML+CSS', 'JS'],
          description: [''],
          tech: ['разметка', 'язык программирования'],
          links: [],
        },
        {
          title: 'Аукцион рыбок',
          sortDate: '202110',
          date: '10.2021',
          tags: ['SPA','Practice'],
          image: 'pisces.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI'],
          description: ['Практический проект представляет собой платформу аукциона экзотических рыбок.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE'],
          links: ['sdvmxm.ru/pisces'],
        },
        {
          title: 'Волонтерское движение',
          sortDate: '202111',
          date: '11.2021',
          tags: ['SPA','Practice'],
          image: 'foodsharing.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'xicons', 'A&R'],
          description: ['Проект в рамках хакатона.','Практический проект представляет собой платформу для работы волонтеров фудшеринга.','АНО «Фудшеринг» — сервис по распределению продуктов питания с истекающим сроком годности — привлекает волонтеров для своей деятельности. Сейчас в базе организации порядка 2 тысяч волонтеров. Они регулярно забирают продукты из магазинов, пекарен или кафе, а затем раздают своим подопечным (постоянным получателям продовольственной помощи).','При каждой передаче еды волонтеры заполняют и подписывают соответствующий акт. Для более эффективной работы АНО «Фудшеринг» требуется веб-приложение, которое позволит рекрутировать и обучать волонтеров, автоматизировать их каждодневную работу с актами и поможет вести мониторинг волонтерской деятельности.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'пакет иконок', 'адаптивность и резиновость'],
          links: ['sdvmxm.ru/foodsharing'],
        },
        {
          title: 'CYBERNUR - турниры по FIFA',
          sortDate: '202106',
          date: '06.2021',
          tags: ['SPA','Production'],
          image: 'cybernur-landing.png',
          complexity: 3,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'A&R', 'FIREBASE'],
          description: ['Ко мне обратился Илья, он является организатором турниров по игре FIFA, в связи с этим появилась необходимость в сервисе, который поможет организовать все внутренние процессы по проведению турниров.', 'Первой задачей было создание промо-страницы, на которой кратко отображается информация о компании, история создания, текущий турнир, инструкция, о том, как принять участие, а так же партнеры и спонсоры турниров.', 'Второй задачей было создание онлайн платформы, в которой участники могут подавать заявку на участие, отслеживать результаты турниров и рейтинг игроков.'],
           tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость', 'база данных'],
          links: ['https://vk.com/@sedovmax-case-cybernur', 'https://cybernur.ru/', 'https://cybernur.online/'],
        },
        {
          title: 'Экомаршруты',
          sortDate: '202109',
          date: '09.2021',
          tags: ['SPA','Production'],
          image: 'map.png',
          complexity: 3,
          stack: ['HTML+CSS', 'VUE', 'PRIME-VUE', 'A&R', 'OpenStreetMap'],
          description: ['Командная работа в рамках ХАКАТОНА.','«Мы разработали ПО для построения оптимального экологичного маршрута на разных типах транспорта».','Разработка является как дополнением к существующему приложению "Московский транспорт", так и самостоятельным кроссплатформенным ПО в котором пользователи могут построить динамический маршрут для прогулок или поездок на велосипеде и самокате.', 'Технологический стек: vue.js, python, OpenStreetMap, Rest API, GraphHopper, JSON, Docker.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость', 'некоммерческий веб-картографический проект по созданию силами сообщества участников — пользователей Интернета подробной свободной и бесплатной географической карты мира.'],
          links: ['https://www.youtube.com/watch?v=PQVbtcgLim8&ab_channel=MaximSedov'],
        },
        {
          title: 'Redrowant',
          sortDate: '202105',
          date: '05.2021',
          tags: ['Landing','Test-Task'],
          image: 'redrowant.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'A&R',],
          description: ['Лендинг предоставленного макета в рамках тестового задания по вакансии.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость'],
          links: ['https://maximsedov.github.io/redrowant/'],
        },
        {
          title: 'GS',
          sortDate: '202105',
          date: '05.2021',
          tags: ['SPA','Test-Task'],
          image: 'gs.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'A&R',],
          description: ['Тренажер памяти в рамках тестового задания по вакансии.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость'],
          links: ['https://maximsedov.github.io/gs/', 'https://github.com/MaximSedov/gs'],
        },
        {
          title: 'Oxem',
          sortDate: '202106',
          date: '06.2021',
          tags: ['SPA','Test-Task'],
          image: 'oxem.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'A&R',],
          description: ['Подключение к базе и отрисовка таблицы с поиском, пагинацией и добавлением новых строк в рамках тестового задания по вакансии.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость'],
          links: ['https://maximsedov.github.io/oxem/', 'https://github.com/MaximSedov/oxem'],
        },
        {
          title: 'WEBSTR',
          sortDate: '202107',
          date: '07.2021',
          tags: ['SPA','Test-Task'],
          image: 'webstr.png',
          complexity: 1,
          stack: ['HTML+CSS', 'VUE', 'ELEMENT-UI', 'A&R',],
          description: ['To-do лист с сохранением в localstorage в рамках тестового задания по вакансии.'],
          tech: ['разметка','JS фреймворк','UI библиотека на VUE', 'адаптивность и резиновость'],
          links: ['https://maximsedov.github.io/webstr/', 'https://github.com/MaximSedov/webstr'],
        }
      ],
    }
  },
  components: {
    ArrowBack,
  },
  methods: {
    openHome() {
      this.$router.push('/')
    },
    complexityTransform(complexity) {
      switch (complexity) {
        case 1:
          return 'Легко'
        case 2:
          return 'Средне'
        case 3:
          return 'Сложно'
        default:
          return 'Неизвестно'
      }
    },
    openProjectInfo(project) {
      this.drawer = true
      this.actualProject = project
    },
    byField(field) {
  return (a, b) => a[field] < b[field] ? 1 : -1;
}
  },
  mounted(){
    this.projects.sort(this.byField('sortDate'));
  },
  computed: {},
}
</script>
<style lang="scss">
$mainBackground: #e1e5ea;
$cardBackground: #faf3f3;
$headerColor: #a7bbc7;
$elementColor: #da7f8f;
$green: #72f07d;
$blue: #8aacff;
$white: #ffffff;
$yellow: #ffcc1d;
$red: #f23557;
$purple: #6f69ac;
$textColor: #2c3e50;
$orange: #FF7800;
.projects {
  &_header {
    height: 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem;
    .backtohome {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 3rem;
      height: 100%;
      background-color: $white;
      margin-right: 2rem;
      flex-shrink: 0;
      border-radius: 1rem;
      &:hover {
        cursor: pointer;
        background-color: $cardBackground;
      }
    }
    .filters {
      width: 100%;
      height: 100%;
      background-color: $white;
      border-radius: 1rem;
    }
  }
  &_content {
    padding: 2rem;
    &-card {
      color: $textColor;
      margin-bottom: 20px;
      .body {
        height: 24rem;
        position: relative;
        background-color: $white;
        border-radius: 1rem;
        .tags {
          width: 100%;
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          align-items: center;
          span {
            display: block;
            padding: 0.5rem;
            margin: 0.5rem;
            border-radius: 0.5rem;
            color: $white;
            font-weight: bold;
          }
          span.Practice {
            background-color: $purple;
          }
          span.Landing {
            background-color: $blue;
          }
          span.Production {
            background-color: $yellow;
          }
          span.Test-Task {
            background-color: $purple;
          }
          span.SPA{
            background-color: $textColor;
          }
          span.Multi-page{
            background-color: $orange;
          }
          .complexity {
            position: relative;
            display: flex;
            justify-content: space-between;
            width: 1rem;
            margin: 0.5rem;
            align-items: flex-end;
            flex-shrink: 0;
            div {
              border-radius: 0.2rem;
              flex-shrink: 0;
              width: 0.2rem;
              background-color: $mainBackground;
            }
            div:nth-child(1) {
              height: 0.5rem;
            }
            div:nth-child(2) {
              height: 1rem;
            }
            div:nth-child(3) {
              height: 1.5rem;
            }
          }
          .complexity.active-1 {
            div:nth-child(1) {
              background-color: $green;
            }
          }
          .complexity.active-2 {
            div:nth-child(1) {
              background-color: $yellow;
            }
            div:nth-child(2) {
              background-color: $yellow;
            }
          }
          .complexity.active-3 {
            div {
              background-color: $orange;
            }
          }
        }
        .image {
          height: 15rem;
          width: 100%;
          background-repeat: no-repeat;
          background-position: top;
          background-size: 100% auto;
        }
        .title {
          .stack {
            margin-bottom: 0.5rem;
            span {
              font-weight: bold;
              font-size: 0.67rem;
              color: white;
              background-color: $blue;
              padding: 0.2rem;
              margin-right: 0.2rem;
              border-radius: 0.2rem;
              text-transform: uppercase;
            }
          }
          .text {
            font-size: 1.8rem;
            font-weight: bold;
            line-height: 2rem;
          }
        }
        .date {
          font-weight: bold;
        }
      }
      &:hover {
        .body {
          cursor: pointer;
          -webkit-box-shadow: 4px 4px 8px 0px $cardBackground;
          -moz-box-shadow: 4px 4px 8px 0px $cardBackground;
          box-shadow: 4px 4px 8px 0px $cardBackground;
        }
      }
    }
  }
}
.el-drawer {
  .actual_project-info {
    &__title {
      font-size: 2rem;
      font-weight: bold;
    }
    &__stack {
      margin-bottom: 0.5rem;
      span {
        font-weight: bold;
        font-size: 0.67rem;
        color: white;
        background-color: $blue;
        padding: 0.2rem;
        margin-right: 0.2rem;
        border-radius: 0.2rem;
        text-transform: uppercase;
      }
      .complexity {
        position: relative;
        display: flex;
        justify-content: space-between;
        width: 1rem;
        margin: 0.5rem;
        margin-left: 0;
        align-items: flex-end;
        flex-shrink: 0;
        div {
          border-radius: 0.2rem;
          flex-shrink: 0;
          width: 0.2rem;
          background-color: $mainBackground;
        }
        div:nth-child(1) {
          height: 0.5rem;
        }
        div:nth-child(2) {
          height: 1rem;
        }
        div:nth-child(3) {
          height: 1.5rem;
        }
      }
      .complexity.active-1 {
        div:nth-child(1) {
          background-color: $green;
        }
      }
      .complexity.active-2 {
        div:nth-child(1) {
          background-color: $yellow;
        }
        div:nth-child(2) {
          background-color: $yellow;
        }
      }
      .complexity.active-3 {
        div {
          background-color: $orange;
        }
      }
    }
    &__tags {
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: end;
      align-items: center;
      span {
        display: block;
        padding: 0.5rem;
        margin: 0.5rem;
        border-radius: 0.5rem;
        color: $white;
        font-weight: bold;
      }
      span.Practice {
        background-color: $purple;
      }
      span.Landing {
        background-color: $blue;
      }
      span.Production {
        background-color: $yellow;
      }
      span.Test-Task {
            background-color: $purple;
          }
      span.SPA{
            background-color: $textColor;
          }
          span.Multi-page{
            background-color: $orange;
          }
    }
    &__date {
      font-weight: bold;
      color: $purple;
    }
    &__description {
      margin-top: 2rem;
      font-size: 1.2rem;
    }
    &__tech {
      margin-top: 2rem;
      font-size: 1.2rem;
      .item {
        margin-top: 1rem;
        span {
          font-weight: bold;
          color: white;
          background-color: $blue;
          padding: 0.2rem;
          border-radius: 0.2rem;
          text-transform: uppercase;
        }
      }
    }
    &__links {
      margin-top: 2rem;
      font-size: 1.2rem;
      .el-link {
        margin-right: 1rem;
      }
    }
    &__button{
      margin-top: 2rem;
      margin-bottom: 2rem;
      div{
        transition: all 0.3s;
        text-align: center;
        width: 7rem;
        box-sizing: border-box;
        padding: 0.7rem 0.5rem;
        background-color: $blue;
        color: white;
        font-size: 1.2rem;
        border-radius: 0.5rem;
        &:hover{
          cursor: pointer;
          background-color: $purple;
        }
      }
    }
    &__image {
      display: flex;
      align-items: center;
      width: 100%;
      height: 100%;
      padding: 1rem;
      box-sizing: border-box;
    }
  }
  &__close-btn{
    .el-icon{
      font-size: 2rem;
    }
&:hover{
    i{
      color: $blue;
    }
  }
  }
  
}
</style>