<template>
  <div>
    <div class="block block-two">
      <div>
        <h2 class="display-3 font-weight-black">
          <span class="inpact">P</span>rofile
        </h2>
        <v-row justify="center">
          <v-col
            cols="12"
            sm="10"
            md="6"
            lg="6"
          >
            <v-avatar
              class="profile"
              color="grey"
              size="300"
              tile
            >
              <v-img src="images/profile.jpg" />
            </v-avatar>
          </v-col>
          <v-col
            cols="12"
            sm="10"
            md="6"
            lg="6"
          >
            <v-simple-table
              v-if="$vuetify.breakpoint.xs || $vuetify.breakpoint.sm"
              dense
            >
              <template v-slot:default>
                <tbody>
                  <tr v-for="item in introduction" :key="item.name">
                    <td>{{ item.name }}</td>
                    <td>{{ item.value }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
            <v-simple-table
              v-if="!($vuetify.breakpoint.xs || $vuetify.breakpoint.sm)"
            >
              <template v-slot:default>
                <tbody>
                  <tr v-for="item in introduction" :key="item.name">
                    <td>{{ item.name }}</td>
                    <td>{{ item.value }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
        </v-row>
      </div>
    </div>
    <div class="block-five">
      <v-row dense justify="center">
        <v-col
          v-for="card in cards"
          :key="card.title"
          cols="12"
          sm="10"
          md="6"
          lg="6"
        >
          <v-card
            :href="card.href"
            link
            target="_blank"
          >
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title v-text="card.title" />
                <v-card-subtitle v-text="card.subtitle" />
              </div>
              <v-avatar
                class="ma-3"
                size="125"
                tile
              >
                <v-img :src="card.src" contain />
              </v-avatar>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'default',
  data () {
    return {
      introduction: [
        {
          name: 'Name：',
          value: 'Ito Akihiro'
        },
        {
          name: 'Birthday',
          value: '1989/04/17 (Aries)'
        },
        {
          name: 'Blood Type',
          value: 'O型'
        },
        {
          name: 'motto',
          value: '困難の中に機会がある(アインシュタイン)'
        },
        {
          name: 'respected',
          value: '堀江 貴文、与沢 翼'
        },
        {
          name: 'Hobby',
          value: 'アマプラ、筋トレ、野球、時々サバゲー'
        }
      ],
      cards: [
        {
          title: 'GitHub',
          subtitle: 'GitHubのアカウントです。',
          src: '/self-introduce/logos/octocat.png',
          href: 'https://github.com/itoaki'
        },
        {
          title: 'GitLab',
          subtitle: 'GitLabのアカウントです。',
          src: '/self-introduce/logos/gitlab.svg',
          href: 'https://gitlab.com/Itoaki'
        },
        {
          title: 'はてなブログ',
          subtitle: '勉強したことをなんでも書いてます。',
          src: '/self-introduce/logos/hatenablog.svg',
          href: 'https://techstation.hatenablog.com/'
        },
        {
          title: 'note',
          subtitle: '普段考えていることなどを書いてます。',
          src: '/self-introduce/logos/note.svg',
          href: 'https://note.com/itoaki0417'
        },
        {
          title: 'Qiita',
          subtitle: '作成したもののまとめ記事を書いてます。',
          src: '/self-introduce/logos/qiita.png',
          href: 'https://qiita.com/itoaki0417'
        },
        {
          title: 'Twitter',
          subtitle: 'お気軽にフォローしてください。',
          src: '/self-introduce/logos/twitter.svg',
          href: 'https://twitter.com/itoaki0417'
        },
        {
          title: 'Wantedly',
          subtitle: 'プロフィール鋭意記載中',
          src: '/self-introduce/logos/wantedly.svg',
          href: 'https://www.wantedly.com/users/127449944'
        },
        {
          title: 'Linkedin',
          subtitle: 'お友達になりましょう。',
          src: '/self-introduce/logos/linkedin.png',
          href: 'https://www.linkedin.com/in/akihiro-ito-042319116'
        }
      ]
    }
  }
}
</script>
<style>
.block {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  background: #f5f5f5;
  color: #808080;
}

.inpact {
  color: #ffd700;
  font-weight: bold;
}

.block-one {
  z-index: 100;
}

.block-two {
  background-size: cover;
  background-image: url("/self-introduce/images/background.jpg");
  color: #ffffff;
  z-index: 110;
}

.block-three {
  background: #f5f5f5;
  z-index: 120;
}

.block-five {
  width: 100%;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  background: #f5f5f5;
  background: #212E32;
  color: #ffffff;
  z-index: 140;
}
</style>
