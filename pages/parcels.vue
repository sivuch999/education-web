<template>
  <v-row justify="center" align="center" class="index-page">
    <v-col cols="6" sm="6" md="6">
      <v-text-field placeholder="กรุณาระบบคำค้นหา" v-model="keyword"/>
    </v-col>
    <v-col cols="6" sm="6" md="6">
        <v-btn depressed color="primary" v-on:click="fnSearch">ค้นหา</v-btn>
    </v-col>
    <v-col cols="12" sm="12" md="12">
      <v-data-table :headers="headers" :items="parcels" class="elevation-1" />
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      keyword: 'SB1238345TH',
      headers: [
        { text: "ID", value: "parcels_id" },
        { text: "Tracking", value: "tracking" },
        { text: "Receiver To", value: "receiver to" },
        { text: "Description", value: "description" },
        { text: "CreatedAt", value: "created_at" },
      ],
      parcels: [],
    };
  },
  methods: {
    getAll() {
      this.$axios.$post("/parcels/getAll").then((res) => {
        if (res.code == 200) {
          return (this.parcels = res.data);
        }
      });
    },
    fnSearch() {
      console.log(this.keyword);
      console.log(this.$axios)
      this.$axios.$post("/parcels/getAll",{ keyword: this.keyword }).then((res) => {
        console.log(res.data)
        if (res.code == 200) {
          return (this.parcels = res.data);
        }
      });
    }
  },
  async mounted() {
    this.parcels = this.getAll();
  },
  // async asyncData({ app: { $axios } }) {
  //   let parcels_ssr = await Promise.all([
  //     $axios.$post("/parcels/getAll")
  //   ])
  //   return {
  //     parcels_ssr
  //   };
  // },
};
</script>