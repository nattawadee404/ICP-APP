<template>
  <q-layout view="hHh Lpr lFf">
    <q-page-container class="bg-grey-2">
      <q-page
        padding
        class="row items-center justify-center"
        style="background: linear-gradient(#74c588, #0ad13c)"
      >
        <div class="row full-width">
          <div class="col-md-8 offset-md-2 col-xs-12 q-pa-xs">
            <q-card flat class="bg-white text-black">
              <q-card-section class="bg-deep-purple-7">
                <h4 class="text-h5 text-white q-my-xs text-center">
                  {{ title }}
                </h4>
              </q-card-section>
              <div class="row">
                <div class="col-md-6 col-xs-12 q-pa-xs">
                  <q-img
                    placeholder-src="~assets/images/user1.jpg"
                    src="~assets/images/user1.jpg"
                    spinner-color="white"
                  ></q-img>
                </div>
                <div class="col-md-6 col-xs-12">
                  <div class="q-pa-md">
                    <q-form class="q-gutter-md">
                      <div class="row">
                        <div class="col-md-12 col-xs-12 q-pa-xs text-center">
                          <h6>คุณต้องการออกระบบใช่หรือไม่?</h6>
                          <q-btn
                            class="btn btn-dark btn-lg btn-block"
                            color="primary"
                            label="ยืนยัน"
                            icon="check_box"
                            @Click="confirm()"
                            to="/"
                          />
                          <q-btn
                            class="btn btn-dark btn-lg btn-block"
                            flat
                            color="primary"
                            label="ยกเลิก"
                            icon="dangerous"
                            to="/"
                          />
                        </div>
                      </div>
                    </q-form>
                  </div>
                </div>
              </div>
            </q-card>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  data() {
    return {
      title: "ออกจากระบบ",
    };
  },
  methods: {
    confirm() {
      this.$store.commit("setMyAuthenticate", false);
      this.$store.commit("setMyMember_id", 0);
      this.$store.commit("setMyName", "");
      this.$store.commit("setMyStatus", "");
      // this.$router.replace({ name: "home" });
    },
    cancel() {
      // this.$router.replace({ name: "home" });
    },
  },
};
</script>
<style scoped></style>
