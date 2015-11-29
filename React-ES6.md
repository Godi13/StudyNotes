关于React-router

```js
import React from 'react';
import ReactDOM from 'react-dom';
import { Router, Route, Link, IndexRoute, Redirect } from 'react-router';
import './styles/main.scss';

class App extends React.Component {
  componentDidMount() {
    console.log('App did mount');
  }

  componentWillReceiveProps() {
    console.log('App will receive props');
  }

  componentDidUpdate() {
    console.log('App did update');
  }

  render() {
    return (
      <div>
        <div>
          <Link to="/" className="item">首页</Link>
          <Link to="/tv" className="item" query={{orderBy: 'date'}}>电视</Link>
        </div>
        {this.props.children}
      </div>
    )
  }
}

class TV extends React.Component {
  constructor(props) {
    super(props);

    let { query } = this.props.location;

    console.log(query);
  }

  componentDidMount() {
    console.log('TV did mount');
  }

  render() {
    return (
      <div>
        {this.props.children}
      </div>
    )
  }
}

class Show extends React.Component {
  constructor(props) {
    super(props);

    console.log(this.props.params);
  }

  render() {
    return (
      <h1>节目 {this.props.params.id} </h1>
    )
  }
}

class Home extends React.Component {
  componentDidMount() {
    console.log('Home did mount');
  }

  componentWillUnmount() {
    console.log('Home will unmount');
  }

  render() {
    return (
      <div>首页内容</div>
    )
  }
}

class ShowIndex extends React.Component {
  render() {
    return (
        <div>电视节目列表</div>
    )
  }
}

function handleEnter() {
  console.log('进入');
}

function handleLeave() {
  console.log('离开');
}

ReactDOM.render((
  <Router>
    <Route path="/" component={App}>
      <IndexRoute component={Home} />
      <Route path="/tv" component={TV}>
        <IndexRoute component={ShowIndex} />
        <Route path="/shows/:id" component={Show} onEnter={handleEnter} onLeave={handleLeave}/>
        <Redirect from="shows/:id" to="/shows/:id" />
      </Route>
    </Route>
  </Router>
),document.getElementById('root'));
```
