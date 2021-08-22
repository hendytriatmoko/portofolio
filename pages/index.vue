<template>
  <v-card class="mx-4 mt-7" >
    <v-row>
      <v-col cols="12" md="4" style="background:black;color:white">
        <v-img src="hendy.jpeg" style="position:relative">
          <div class="ml-3" style="margin-top:99%">
            <b>
            <div class="pb-1 pt-5" style="color:white;font-size:20px">HENDI TRIATMOKO</div>
            <div style="color:white;font-size:15px">JUNIOR  FRONT-END DEVELOPER</div>
            </b>
          </div>
        </v-img>
        <h1>ahyvbd</h1>
      </v-col>
      <v-col cols="12" md="8">
        <v-list >
          <v-list-item-group 
            color="#008080"
            class="d-flex align-center justify-space-between">
              <v-list-item @click="pilihJudul(item.no)" v-for="item in kolom" :key="item.no">
                <v-list-item-title align="center">{{ item.judul }}</v-list-item-title>
              </v-list-item>
          </v-list-item-group>
        </v-list>
        <div class="mx-5">
          <div v-if="selectedItem == 0" class="mt-7" style="color:#008080">
            <center>
              <h3 >Hello, I'am</h3>
              <h1 class="pt-4 pb-2">HENDI TRIATMOKO</h1>
              <div class="pt-4 pb-7">JUNIOR FRONT-END DEVELOPER</div>
              <v-divider color="#008080"></v-divider>
              <div class="pt-2">A professional front-end developer from Jakarta, Indonesia.
                I always give the best effort for each projects I did
              </div>
              <h3 class="pt-4">+62 821-1123-9208</h3>
              <div class="pt-4">hendytriatmoko0@gmail.com</div>
              <v-btn
              color="#008080"
              class="white--text mt-4"
            >
              Download CV
            </v-btn>
            </center>
          </div>
          <div v-if="selectedItem == 1" class="mt-7" style="color:#008080;overflow-y:scroll;height:370px">
            <div>
              <center>
                <h2>ABOUT ME</h2>
                <v-divider color="#008080" width="30%"></v-divider>
                <v-row style="width:70%" class="pt-4">
                  <v-col cols="12" md="6" style="text-align:left">
                    <b>
                    <div class="pb-2">
                      <v-icon
                        color="#008080"
                        class="pr-1"
                      >
                        mdi-account
                      </v-icon>
                      Name
                    </div>
                    <div class="pb-2">
                      <v-icon
                        color="#008080"
                        class="pr-1"
                      >
                        mdi-calendar-month
                      </v-icon>
                      Date of birth
                    </div>
                    <div class="pb-2">
                      <v-icon
                        color="#008080"
                        class="pr-1"
                      >
                        mdi-phone
                      </v-icon>
                      Phone
                    </div>
                    <div class="pb-2">
                      <v-icon
                        color="#008080"
                        class="pr-1"
                      >
                        mdi-email-multiple
                      </v-icon>
                      Email
                    </div>
                    <div>
                      <v-icon
                        color="#008080"
                        class="pr-1"
                      >
                        mdi-map-marker
                      </v-icon>
                      Address
                    </div>
                    </b>
                  </v-col>
                  <v-col cols="12" md="6" style="text-align:right">
                    <div class="pb-2">Hendi Triatmoko</div>
                    <div class="pb-2">October 18th 1998</div>
                    <div class="pb-2">+62 821-1123-9208</div>
                    <div class="pb-2">hendytriatmoko0@gmail.com</div>
                    <div >Jakarta, Indonesia</div>
                  </v-col>
                </v-row>
              </center>
            </div>
            <div class="mt-8">
              <center>
                <h2>MY EDUCATION</h2>
                <v-divider color="#008080" width="50%"></v-divider>
                <div style="width:60%">
                <v-timeline dense >
                  <v-timeline-item color="#008080" large icon="mdi-school"></v-timeline-item>
                  <v-timeline-item
                    v-for="(year, i) in years"
                    :key="i"
                    :color="year.color"
                    small
                  >
                    <div class="py-2" style="text-align:left">
                      <h4
                        :class="` ${year.color}--text`"
                        v-text="year.year"
                      ></h4>
                      <h4 :class="`${year.color}--text`">
                        {{ year.sekolah }}
                      </h4>
                      <div class="text-justify">
                        {{ year.desc }}
                      </div>
                    </div>
                  </v-timeline-item>
                </v-timeline>
                </div>
              </center>
            </div>
            <div style="background:#F3F2F2" class="pt-8">
              <center>
                <h2>MY HOBBIES</h2>
                <v-divider color="#008080" width="30%"></v-divider>
                <p class="mx-4 mt-6">
                  Enjoy the storyline deeper by reading a book, or sometimes enjoy some thrilling action scenes just to refresh myself from the routine. Traveling to a beautiful place then take several pictures can be done to find new ideas.
                </p>
                <div class="d-flex align-center justify-space-around pb-2 pt-2">
                  <div>
                    <v-icon color="#008080">mdi-filmstrip-box-multiple</v-icon>
                    <br>
                    Movies
                  </div>
                  <div>
                    <v-icon color="#008080">mdi-camera</v-icon>
                    <br>
                    Photography
                  </div>
                  <div>
                    <v-icon color="#008080">mdi-airplane</v-icon>
                    <br>
                    Traveling
                  </div>
                  <div>
                    <v-icon color="#008080">mdi-hiking</v-icon>
                    <br>
                    Hiking
                  </div>
                </div>
              </center>
            </div>
          </div>
          <div v-if="selectedItem == 2" class="mt-7" style="color:#008080">
            <center>
              <h2>MY SKILL</h2>
              <v-divider color="#008080" width="30%"></v-divider>
              <div class="text-left mt-2" v-for="item in skill" :key="item.no">
                <h3>{{ item.nama }}</h3>
                <v-progress-linear
                  style="border: 2px solid #008080"
                  height="20"
                  color="teal"
                  buffer-value="0"
                  :value="item.value"
                  stream
                >{{item.value}}</v-progress-linear>
              </div>
            </center>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-card>
</template>
<script>
export default {
  name: 'index',
  data: () => ({
    kolom:[
      {judul:'WELCOME',no:0},
      {judul:'PROFILE',no:1},
      {judul:'RESUME',no:2},
      {judul:'PORTOFOLIO',no:3},
      {judul:'CONTACT',no:4},
    ],
    selectedItem: 0,
    years: [
      {
        color: '#008080',
        year: '2017 - 2021',
        sekolah: 'UPN VETERAN JAKARTA',
        desc: 'Bachelor of information systems from UPN VETERAN JAKARTA. Pass with compliments. And start developing programming skills by Initiating many programming projects on campus. Participate in several programming competitions',
      },
      {
        color: '#008080',
        year: '2014 - 2017',
        sekolah: 'SMAN 102 JAKARTA',
        desc: 'Science major. Getting interested in information technology and learning about robotics. So interested in mathematics that he participated in several math championships',
      },
      {
        color: '#008080',
        year: '2011 - 2014',
        sekolah: 'SMPN 90 JAKARTA',
        desc: 'Started liked in computer graphic design. learn corel draw and photo editor',
      },
      {
        color: '#008080',
        year: '2005 - 2011',
        sekolah: 'SDN 12 JAKARTA',
        desc: 'SDN 12 PT is the first formal school which I attended. Many achievements were obtained and many experience gained.',
      },
    ],
    skill:[
      {
        no:0,
        nama:'HTML',
        value:0,
        nilai: 95,
      },
      {
        no:1,
        nama:'CSS',
        value:0,
        nilai: 80,
      }
    ],
    interval : 0,
  }),
  methods: {
    async pilihJudul(no){
      this.selectedItem = no
      if (no == 2) {
        setTimeout(() => {
        this.interval = setInterval(() => {
          if (this.skill[0].value == this.skill[0].nilai) {
            
          }if (this.skill[0].value != this.skill[0].nilai){
            this.skill[0].value += 1
          }
          if (this.skill[1].value == this.skill[1].nilai) {
            
          }if (this.skill[1].value != this.skill[1].nilai){
            this.skill[1].value += 1
          }
        }, 80)
      }, 1500)
      }
    }
  },
  async mounted() {
        
  }
}
</script>