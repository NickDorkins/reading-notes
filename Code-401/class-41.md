# Class 41: React 4

## [Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)


- We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
- Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.

1. First, we’ll create a page called [id].js under pages/posts. Pages that begin with [ and end with ] are [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes) in Next.js.

1. In pages/posts/[id].js, we’ll write code that will render a post page — just like other pages we’ve created

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
} 
```

1. Now, We’ll export an async function called getStaticPaths from this page. In this function, we need to return a list of possible values for id.

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}
```

Finally, we need to implement getStaticProps again - this time, to fetch necessary data for the blog post with a given id. getStaticProps is given params, which contains id (because the file name is [id].js).

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```
























## [Next.js - Deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)

## [Optional - Next.js 10 is here](https://www.youtube.com/watch?v=JWCS5IdECVI)

## [Next.js - Static File Serving](https://nextjs.org/docs/basic-features/static-file-serving)
