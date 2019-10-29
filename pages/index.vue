<template>
  <div>
    <div class="profile">
      <h1>PROFILE</h1>
      <v-layout>
        <v-flex xs12 md6>
          <img src="~/assets/profile.jpg">
        </v-flex>
        <v-flex xs12 md6>
          <div>
            <!-- <p>・Name ：Murota Taiki</p>
            <p>・Age  ：27</p>
            <p>・Base ：Tokyo</p>
            <p>・Hobby  ：Work out</p> -->
            <p>・名前　：　室田　大気</p>
            <p>・年齢　：　27歳</p>
            <p>・出身　：　北海道</p>
            <p>・在住　：　東京</p>
            <p>・趣味　：　筋トレ、勉強</p>
            <p>・経歴</p>
            <v-simple-table class="profile-table">
              <thead>
                <tr>
                  <th class="text-left">Date</th>
                  <th class="text-left">Topic</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in items" :key="item.id">
                  <td>{{ item.date }}</td>
                  <td>{{ item.topic }}</td>
                </tr>
              </tbody>
            </v-simple-table>
          </div>
        </v-flex>
     </v-layout>
    </div>
    <div class="skills">
      <h1>SKILLS</h1>
      <v-layout row wrap>
        <v-flex xs12 md4>
          <div class="skill-button">
            <v-btn class="skill-front" @click="frontSkill">フロントエンド</v-btn>
          </div>
          <div class="skill-list" v-if="skillDisplay == 'front'">
            <div v-for="item in front" :key="item.skill">
              <v-btn outline rounded class="primary">{{item.skill}}<br />{{item.level}}</v-btn>
            </div>
          </div>
        </v-flex>
        <v-flex xs12 md4>
          <div class="skill-button">
            <v-btn class="skill-back" @click="backSkill">バックエンド</v-btn>
          </div>
          <div class="skill-list" v-if="skillDisplay == 'back'">
            <div v-for="item in back" :key="item.skill">
              <v-btn rounded class="primary">{{ item.skill }}<br />{{item.level}}</v-btn>
            </div>
          </div>
        </v-flex>
        <v-flex xs12 md4>
          <div class="skill-button">
            <v-btn class="skill-others" @click="otherSkill">その他</v-btn>
          </div>
          <div class="skill-list" v-if="skillDisplay == 'other'">
            <div v-for="item in other" :key="item.skill">
              <v-btn rounded class="primary">{{item.skill}}<br />{{item.level}}</v-btn>
            </div>
          </div>
        </v-flex>
        <v-flex md12>
          <v-btn class="success" to="/works" style="width:20%; margin:150px 40% 0; height:40px;" nuxt>作成実績へ</v-btn>
        </v-flex>
      </v-layout>
    </div>
    <div class="future">
      <h1>FUTURE</h1>
      <v-layout>
        <v-flex offset-md1 xs12 md4>
          <v-card>
            <v-card-title>興味のある言語</v-card-title>
            <v-card-text>
              <ul>
                <li>Laravel</li>
                <li>django</li>
                <li>Kotlin</li>
                <li>Angular.js</li>
              </ul>
            </v-card-text>
          </v-card>
        </v-flex>
        <v-flex offset-md2 xs12 md4>
          <v-card>
            <v-card-title>意気込み</v-card-title>
            <v-card-text>
              日々成長！！
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data(){
    return{
      skillDisplay : 'nothing',
      items: [
        {
          id : 1,
          date : '1992年',
          topic : '生誕'
        },{
          id : 2,
          date : '2017年',
          topic : '某国立大学大学院のマテリアル系専攻卒業'
        },{
          id : 3,
          date : '〃',
          topic : '某メーカーの研究職として社会人デビュー'
        },{
          id : 4,
          date : '2019年',
          topic : 'エンジニアに転職'
        },{
          id : 5,
          date : '現在',
          topic : 'ソフトウェアエンジニア'
        }
      ],
      front : [
        {
          skill : 'HTML5',
          level : '★★★★'
        },{
          skill : 'CSS3',
          level : '★★★'
        },{
          skill : 'javascript',
          level : '★★'
        },{
          skill : 'jQuery',
          level : '★★★'
        },{
          skill : 'vue.js',
          level : '★★'
        },{
          skill : 'typescript',
          level : '★'
        }
      ],
      back : [
        {
          skill : 'Java',
          level : '★★★'
        },{
          skill : 'Spring',
          level : '★★★★'
        }
      ],
      other : [
        {
          skill : 'MySQL',
          level : '★★★'
        },{
          skill : 'firebase',
          level : '★★'
        },{
          skill : 'git',
          level : '★★★★'
        },{
          skill : 'Nuxt.js',
          level : '★★'
        }
      ]
    }
  },
  methods: {
    frontSkill: function(){
      this.skillDisplay = 'front'
    },
    backSkill: function(){
      this.skillDisplay = 'back'
    },
    otherSkill: function(){
      this.skillDisplay = 'other'
    }
  }
})
</script>

<style>
h1{
  margin: 30px 0 30px;
  font-size: 50px;
  text-align:center;
}
.skills h1, .future h1{
  border-top: 1px solid gray;
  margin-top: 80px;
  padding-top: 50px;
}
.profile div div img{
  border-radius: 50%;
  width:100%;
}

.profile div div div p{
  margin-left: 15%;
  font-size: 30px;
}
.profile-table{
  margin-left: 20%;
}
.skill-button{
  margin-bottom: 20px;
}
.skills div div button{
  width: 80%;
  margin-left: 10%;
}
.skill-list{
  text-align: center;
}
.skill-list div button{
  margin: 0 10% 20px 10%;
  width: 100%;
}
.v-btn{
  text-transform: none;
}
</style>
