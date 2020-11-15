<template>
  <v-row justify="center" align="center" class="index-page">
    <v-col cols="12" sm="12" md="5">
      <v-card class="unset-box-shadow">
        <v-card-title class="headline font-weight-black text-title unset-background-color">
          <label>ระบบบริหารจัดการนิติบุคคล</label>
          <label>คอนโด และ บ้านจัดสรร</label>
        </v-card-title>
        <v-card-text>
          <label class="subtitle-1 font-weight-bold text-detail">
            บริหารจัดการโครงการอสังหาริมทรัพย์ของคุณได้อย่างง่ายดาย สะดวก รวดเร็ว คลอบคลุม ไม่ต้องโหลดแอพพลิเคชั่น
          </label>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn class="primary btn-sample" nuxt to="/inspire">ทดลองใช้ฟรี 30 วัน</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
    <v-col cols="12" sm="12" md="7" class="text-center">
      <div>
        <welcome-logo />
      </div>
    </v-col>
  </v-row>
</template>

<script>
import WelcomeLogo from '~/components/WelcomeLogo.vue'

export default {
  components: {
    WelcomeLogo
  }
}
</script>

<style>
  .btn-sample {
    background: transparent linear-gradient(90deg,#ffd800,#fc9c00) 0 0 no-repeat padding-box;
    border-radius: 20px;
    border: none;
    opacity: 1;
    padding: 5px 15px;
    color: #fff;
  }


  .index-page .text-title {
    margin-top: 6rem;
    color: #004796! important;
    text-shadow: 0 3px 0 rgba(42,66,93,.10196);
  }
  .index-page .text-detail {
    text-shadow: 0 3px 0 rgba(42,66,93,.10196);
  }
  .index-page .unset-box-shadow {
    box-shadow: unset !important;
  }
  .index-page .unset-background-color {
    background-color: unset !important;
  }

  @media only screen and (max-width: 600px) {
    .index-page {
      text-align: center !important;
    }
    .index-page .v-card__actions {
      display: block !important;
    }
    .index-page .text-title {
      margin-top: unset !important;
      justify-content: center;
    }
    .index-page .welcome-logo {
      width: 100% !important;
    }
  }

</style>
