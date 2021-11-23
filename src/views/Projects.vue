<template>
  <div class="projects">
    <div class="projects_header">
      <div class="backtohome" @click="openHome">
        <arrow-back :height="24" :width="24" />
      </div>
      <div class="filters"></div>
    </div>

    <div class="projects_content">
      <el-row :gutter="20">
        <el-col v-for="(project, index) in projects" :key="project.index" :xs="24" :sm="12" :md="8" :lg="6" :xl="6" class="projects_content-card">
          <div class="body">
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
            <div class="image" :style="{backgroundImage: `url(${require('@/assets/' + project.image)}`}">

            </div>
            <div class style="position:absolute;box-sizing:border-box;bottom:0;padding:0.5rem; width:100%;display:flex; justify-content:space-between;align-items:end">
              <div class="title">
                <div class="stack"> <span v-for="(item, index) in project.stack" :key="item.index">{{item}}</span></div>
                <div class="text">{{project.title}}</div>
              </div>
              <div class="date">{{project.date}}</div>
            </div>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>
<script>
import ArrowBack from '../components/icons/arrow_back.vue'
export default {
  data() {
    return {
      projects: [
        {
          title: 'ИТ Продукт',
          date: '11.2021',
          tags: ['Landing', 'Practice'],
          image: 'ais.png',
          complexity: 3,
          stack: ['VUE', 'PHP']
        },
        {
          title: 'Рыбный аукцион',
          date: '11.2021',
          tags: ['Landing', 'Practice'],
          image: 'switter.png',
          complexity: 2,
          stack: ['VUE', 'FIREBASE']
        },
        {
          title: 'Аренда жилья',
          date: '11.2021',
          tags: ['Landing', 'Practice'],
          image: 'booking.png',
          complexity: 1,
          stack: ['VUE']
        },
        {
          title: 'АИС по созданию курсов',
          date: '11.2021',
          tags: ['Landing', 'Production'],
          image: 'ais.png',
          complexity: 2,
          stack: ['PHP']
        },
        {
          title: 'Магазин электроники',
          date: '11.2021',
          tags: ['Landing', 'Practice'],
          image: 'techstore.png',
          complexity: 1,
          stack: ['VUE', 'HTML']
        },
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
              background-color: $elementColor;
            }
          }
        }
        .image{
          height: 15rem;
          width: 100%;
          background-repeat: no-repeat;
        background-position: top;
        background-size: 100% auto;
        }
        .title {
          .stack{
            margin-bottom: 0.5rem;
            span{
              font-weight: bold;
              font-size: 0.67rem;
              color: white;
              background-color: $blue;
              padding: 0.2rem;
              margin-right: 0.2rem;
              border-radius: 0.2rem;
            }
            
          }
          .text{
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
</style>