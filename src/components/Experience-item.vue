<template>
  <v-card class="elevation-2">
    <v-list-item three-line>
      <v-list-item-content>
        <div class="overline mb-4">{{company.to}} - {{company.from}}</div>
        <v-list-item-title class="headline mb-1">{{company.title}}</v-list-item-title>
        <v-list-item-subtitle>{{company.name}}</v-list-item-subtitle>
        <v-list-item-subtitle>{{company.location}}</v-list-item-subtitle>
        <v-list-item-content class="line-break">{{company.description}}</v-list-item-content>
      </v-list-item-content>

      <v-list-item-avatar v-if="company.avatar" tile :size="imageSize" color="grey">
        <v-img :src="company.avatar"></v-img>
      </v-list-item-avatar>
    </v-list-item>
  </v-card>
</template>

<script>
export default {
    props:{
        company: {
            to: String,
            from: String,
            title: String,
            name: String,
            location: String,
            description: String,
            avatar: String
        }
    },
    computed: {
        imageSize: function(){
            if(this.$vuetify.breakpoint.smAndUp){
                return 80;
            } else {
                return 30;
            }
        }
    }
}
</script>