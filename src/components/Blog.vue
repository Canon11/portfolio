<template>
  <div class="my-5">
    <div class="display-2 font-weight-regular font-italic text-sm-center">New Blog</div>
    <v-layout row justify-space-around class="mt-4">
      <v-flex sm3 v-for="(blog, i) in blogs" :key="i">
        <v-card>
          <v-img :src="blog.image" height="200px"></v-img>

          <v-card-title primary-title>
            <div>
              <div class="headline">{{ blog.title }}</div>
            </div>
          </v-card-title>

          <v-card-actions>
            <v-btn flat color="purple" :href="blog.source" target="_blank">Explore</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  data: () => ({
    show: false,
    blogs: [
      {
        title:
          "AWSソリューションアーキテクトアソシエイトの勉強範囲まとめ(2019年3月)",
        description: "desc1",
        image:
          "https://murattyblog.com/wp-content/uploads/2019/03/eyecatch.039.png",
        source: "https://murattyblog.com/aws_saa_study"
      },
      {
        title: "Atom卒業!? MacでVSCodeを使ってみた3つの感想",
        description: "desc1",
        image:
          "https://murattyblog.com/wp-content/uploads/2019/02/eyecatch.038.png",
        source: "https://murattyblog.com/vscode_install"
      },
      {
        title: "AWSソリューションアーキテクトアソシエイトに合格しました！",
        description: "desc1",
        image:
          "https://murattyblog.com/wp-content/uploads/2019/02/eyecatch.037.png",
        source: "https://murattyblog.com/aws_saa"
      }
    ]
  })
};
</script>
