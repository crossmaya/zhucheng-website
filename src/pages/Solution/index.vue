<template>
  <div class="solution">
    <PicAndBreadcrumb :data="data" />
    <SolutionContent />
    <ContactUsForm />
  </div>
</template>

<script>
  import SolutionContent from './components/SolutionContent'
  import ContactUsForm from './components/ContactUsForm'
  import PicAndBreadcrumb from "@/components/PicAndBreadcrumb";
  import service from "@/api/service";

  export default {
    name: 'index',
    components: {
      SolutionContent,
      PicAndBreadcrumb,
      ContactUsForm,
    },
    data() {
      return {
        data: {
          title: '解决方案', slogan: ['精益求精    合作共赢'],
          img: 'assets/image/solution_bg.png', content: '首页>解决方案'
        },
      }
    },
    methods: {
      getBg() {
        service.getImgs({
          pageNo: 1,
          pageSize: 100,
          orderByClause: 'id desc',
          imgType: 4
        }).then(res => {
          if (res.list && res.list.length) {
            this.data.img = res.list[0].imgurl
          }
        })
      }
    },
    created(){
      this.getBg()
    }
  }
</script>

<style lang="less" scoped>

</style>
