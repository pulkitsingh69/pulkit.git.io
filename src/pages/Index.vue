<template>
  <Layout>
    <Hero />
    <FeaturedPost :projects="$page.projects.edges" />
    <LatestArticles :articles="$page.articles.edges" />
    <!-- <CallToAction /> -->
  </Layout>
</template>

<page-query>
query {
  projects: allProjects (limit: 5) {
    edges{
      node{
        id
        title
        thumbnail 
        path
      }
    }
  },
  articles: allArticles (limit: 3){
    edges {
      node {
        id
        title
        thumbnail
        date (format: "DD MMM YYYY")
        path
        timeToRead
      }
    }
  }
}
</page-query>


<script>
import Hero from "@/components/Hero";
import FeaturedPost from "@/components/FeaturedPost";
import LatestArticles from "@/components/LatestArticles";
export default {
  metaInfo: {
    title: "Welcome",
    content: "John Doe",
  },
  components: {
    Hero,
    FeaturedPost,
    LatestArticles,
  },
};
</script>

<style>
</style>
