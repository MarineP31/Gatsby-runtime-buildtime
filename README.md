<!-- AUTO-GENERATED-CONTENT:START (STARTER) -->
<p align="center">
  <a href="https://www.gatsbyjs.org">
    <img alt="Gatsby" src="https://www.gatsbyjs.org/monogram.svg" width="60" />
  </a>
</p>
<h1 align="center">
  Build time and client runtime data fetching Gatsby's blog
</h1>

This starter ships with the main Gatsby configuration files you might need to get up and running blazing fast with the blazing fast app generator for React.

_Want to learn more about build time and client runtime data fetching[official documentation](https://www.gatsbyjs.org/docs/data-fetching/)._

## 🚀 Quick start

1.  **Install**

    Install all dependencies.

    ```shell
    yarn install
    ```

## 🔨 Buildtime query

1.  **gatsby-source-graphql**

    Install gatsby-source-graphql

    ```shell
    yarn add gatsby-source-graphql
    ```

2.  **Configure gatsby-source-graphql**

    Create configuration into `gatsby-config.js`

    ```shell
    {
      resolve: `gatsby-source-graphql`,
      options: {
        fieldName: `cms`,
        url: `https://api-euwest.graphcms.com/v1/cjjr1at6d0xb801c3scjrm0l0/master`,
        typeName: `GraphCMS`,
        refetchInterval: 60,
      },
    },
    ```

3.  **Create buildtime query into your component**

    You can create a new query inside your component :

    ```shell
    export const pageQuery = graphql`
    query {
    site {
      siteMetadata {
        title
      }
    }
    cms {
      blogPosts(where: { status: PUBLISHED }, orderBy: createdAt_DESC) {
        title
        createdAt
        slug
      }
    }
    ...
    ```

## 🏃‍♀️Runtime query

1.  **Create runtime query into your component**

    To create runtime query, you just have to use react state and useEffect hooks :

    ```shell
    const [starsCount, setStarsCount] = useState(0)
    useEffect(() => {
    // get data from GitHub api
    fetch(`https://api.github.com/repos/gatsbyjs/gatsby`)
      .then(response => response.json()) // parse JSON from request
      .then(resultData => {
        setStarsCount(resultData.stargazers_count)
      }) // set data for the number of stars
    }, [])
    ```

2.  **Start your project**

    Your site is now running at `http://localhost:8000`!

    _Note: You'll also see a second link: _`http://localhost:8000/___graphql`_. This is a tool you can use to experiment with querying your data. Learn more about using this tool in the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-five/#introducing-graphiql)._

    Open the `my-blog-starter` directory in your code editor of choice and edit `src/pages/index.js`. Save your changes and the browser will update in real time!

<!-- AUTO-GENERATED-CONTENT:END -->
