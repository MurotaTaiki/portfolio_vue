<template>
<v-card color="basil">
    <v-card-title class="text-center justify-center py-6">
      <h2 class="font-weight-bold display-3 basil--text">作成実績</h2>
    </v-card-title>

    <v-tabs v-model="tab" background-color="transparent" color="basil" grow>
      <v-tab href="#">個人開発</v-tab>
      <v-tab href="#">企業開発</v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item>
        <v-layout row wrap>
                      <div>
          <v-flex v-for="item in privateDevelop" :key="item.id" md4>

              <v-card flat color="basil">
                  <img :src="item.image" style="width:50%">
              </v-card>
                        </v-flex>
            </div>

        </v-layout>
      </v-tab-item>    
      <v-tab-item>
        <div v-for="item in companyDevelop" :key="item.title">
          <v-simple-table>
              <thead>
                <tr>
                  <th class="text-left" colspan="2">{{item.title}}</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>内容</td>
                  <td>{{item.content}}</td>
                </tr>
                <tr>
                  <td>担当業務</td>
                  <td>{{item.task}}</td>
                </tr>
                <tr>
                  <td>役割</td>
                  <td style="white-space: pre-line">{{item.role}}</td>
                </tr>
                <tr>
                  <td>開発環境</td>
                  <td style="white-space: pre-line">{{item.development}}</td>
                </tr>
              </tbody>
            </v-simple-table>
        </div>
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
   data () {
      return {
        tab: null,
        items: [
          {
            develop : '個人開発',
            value : '1'
          },{
            develop : '企業開発',
            value : '2'
          }
        ],
        privateDevelop: [
          {
            id:1,
            image: require("~/assets/profile.jpg")
          },{
            id:2,
            image: require("~/assets/profile.jpg")
          }
        ],
        companyDevelop: [
          {
            title: '金融機関向け顧客管理機能の開発',
            content: '金融機関を対象とした、顧客情報の講座情報等の管理を行う',
            task: '顧客の登録情報の検索フォームを作成し、検索結果に基づく動的なテーブルの作成',
            role: `フロントエンド ：30%
                   バックエンド　：70%`,
            development: `OS　：Windows
                          言語　：HTML5,CSS3,Bootstrap3,jQuery,Spring
                          DB　：MySQL`
          },{
            title: 'ショッピングサイトにおけるユーザーごとの推薦商品表示機構の開発',
            content: 'ショッピングサイトにアクセスしたユーザーのログを取得し、各ユーザーが興味のありそうな商品を動的に変更し表示する',
            task: `取得したログを用いた表示ルールを作成し、取扱商品との紐付け
                   管理画面でのユーザーごとの権限付与`,
            role: `フロントエンド ：10%
                   バックエンド　：70%
                   データ定義　：20%`,
            development: `OS　：Windows
                          言語　：HTML5,CSS3,Bootstrap3,jQuery,Spring
                          DB　：MySQL`
          }
        ]
      }
    }
})
</script>