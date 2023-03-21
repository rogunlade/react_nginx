# react_nginx@@ -0,0 +1,17 @@
server {

  listen 80;

  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    try_files $uri /index.html =404;
  }

  error_page   500 502 503 504  /50x.html;

  location = /50x.html {
    root   /usr/share/nginx/html;
  }
}

const url = "http://rogunlade.eastus.cloudapp.azure.com:80/hello/world";
    fetch(url)
    .then(response => response.json())
    .then(json => this.setState({ posts: json }))
	@@ -18,21 +18,26 @@ class App extends Component {
  render() {
    const { posts } = this.state;
    return (
      <div className="container">
        <div className="jumbotron">
          <h1 className="display-4">Blog posts</h1>
        </div>
        {posts.map((post) => (
          <div className="card" key={post.name}>
            <div className="card-header">
              #{post.name} {post.age}
            </div>
            <div className="card-body">
              <p className="card-text">{post.name}</p>
            </div>
          </div>
