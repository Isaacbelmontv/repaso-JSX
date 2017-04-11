# repaso-JSX


**Ejemplo de un documentyo de render de react**

```
var React = require('react');
var ReactDOM = require('react-dom');

var MyComponentClass = React.createClass({
  render: function () {
    return <h1>Hello world</h1>;
  }
});

ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);    
```

**Pasando instrucciones a un objeto**
```
var React = require('react');
var ReactDOM = require('react-dom');

var MyComponentClass = React.createClass({
  render: function () {
    return <h1>Hello world</h1>;
  }
});

ReactDOM.render(
	<MyComponentClass />, 
	document.getElementById('app')
);
```

**Ejemplo usando variables de objetos**
```
var React = require('react');
var ReactDOM = require('react-dom');

var redPanda = {
  src: 'http://bit.ly/1U92LL3',
  alt: 'Red Panda',
  width:  '200px'
};

var RedPanda = React.createClass({
  render: function () {
    return (
      <div>
        <h1>Cute Red Panda</h1>
        <img 
          src={redPanda.src} 
          alt={redPanda.alt} 
          width={redPanda.width} />
      </div>
    );
  }
});

ReactDOM.render(
  <RedPanda />,
  document.getElementById('app')
);
```

**Otro ejemplo mas**
```
var React = require('react');
var ReactDOM = require('react-dom');

var owl = {
  title: "Excellent Owl",
  src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-owl.jpg"
};

// Component class starts here:
var RedPanda = React.createClass({
  render: function () {
    return (
      <div>
        <h1>{owl.title}</h1>
        <img 
          src={owl.src} 
          alt={owl.title} 
         />
      </div>
        );
      }
});

ReactDOM.render(
  <Owl />,
  document.getElementById('app')
);
```


**Otro ejemplo pasando variables**
```
var React = require('react');
var ReactDOM = require('react-dom');

var friends = [
  {
    title: "Yummmmmmm",
    src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-monkeyweirdo.jpg"
  },
  {
    title: "Hey Guys!  Wait Up!",
    src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-earnestfrog.jpg"
  },
  {
    title: "Yikes",
    src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-alpaca.jpg"
  }
];

// New component class starts here:
var Friend = React.createClass({
  render: function () {
          var friend = friends[2];
		return (
    <div>
        <h1>{friend.title}</h1>
        <img src={friend.src}/>
    </div>
		);
      }
});

ReactDOM.render(
  <Friend />,
  document.getElementById('app')
);
```

**Ejemplo de un if y else**
```
var React = require('react');
var ReactDOM = require('react-dom');

var fiftyFifty = Math.random() < 0.5;

// React.createClass call begins here:
var TonightsPlan = React.createClass({
  render: function () {
    var place = fiftyFifty ? 'out' : 'to bed';
    return <h1>Tonight I'm going {place} WOOO</h1>;
  }
});

ReactDOM.render(
  <TonightsPlan />,
  document.getElementById('app')
);
```

**Otro ejemplo pasando variables**


```
var React = require('react');
var ReactDOM = require('react-dom');

var MyName = React.createClass({
	// name property goes here:
name: 'whatever-your-name-is-goes-here',
  render: function () {
    return <h1>My name is {this.name}.</h1>;
  }
});

ReactDOM.render(<MyName />, document.getElementById('app'));
```

**Generando botones con alerta**


```
var React = require('react');
var ReactDOM = require('react-dom');

var Button = React.createClass({
  scream: function () {
    alert('AAAAAAAAHHH!!!!!');
  },

  render: function () {
    return <button onClick={this.scream} >AAAAAH!</button>;
  }
});

ReactDOM.render(
  <Button />,
  document.getElementById('app')
);
```


**Invocando el uso de otras funciones**

```
var React = require('react');
var ReactDOM = require('react-dom');
var NavBar = require('./NavBar.js');

var ProfilePage = React.createClass({
  render: function () {
    return (
      <div>
         <NavBar />
        <h1>All About Me!</h1>
        <p>I like movies and blah blah blah blah blah</p>
        <img src="https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-monkeyselfie.jpg" />
      </div>
    );
  }
});
```

**Imprimiendo en el react**

```
var React = require('react');
var ReactDOM = require('react-dom');

var PropsDisplayer = React.createClass({
  render: function () {
  	var stringProps = JSON.stringify(this.props);

    return (
      <div>
        <h1>CHECK OUT MY PROPS OBJECT</h1>
        <h2>{stringProps}</h2>
      </div>
    );
  }
});

// ReactDOM.render goes here:
ReactDOM.render(
  <PropsDisplayer myProp="Hello" />,
  document.getElementById('app')
);  
```

**Imprimiendo variables del react**

```
var React = require('react');
var ReactDOM = require('react-dom');

var Greeting = React.createClass({
  render: function () {
    return <h1>Hi there, {this.props.firstName}!
</h1>;
  }
});

// ReactDOM.render goes here:
ReactDOM.render(
  <Greeting firstName='IsaacBelmont C;' />, 
  document.getElementById('app')
);
```

**usando el this state**

```
var React = require('react');
var ReactDOM = require('react-dom');

var App = React.createClass({
  getInitialState: function () {
    return { title: 'Best App' };
  },
  
  render: function () {
    return (
      <h1>
        {this.state.title}
      </h1>
    );
  }
});

ReactDOM.render(
  <App />,
  document.getElementById('app')
);
```

**Ejemplo de un cambio de variables usando el set**


```
var React = require('react');
var ReactDOM = require('react-dom');
var Child = require('./Child');

var Parent = React.createClass({
  getInitialState: function () {
    return { name: 'Frarthur' };
  },
  
  changeName: function (newName) {
    this.setState({
      name: newName
    });
  },

  render: function () {
    return (
    	<Child 
    		name={this.state.name} 
        onChange={this.changeName} />
    );
  }
});

ReactDOM.render(
	<Parent />, 
	document.getElementById('app')
);
```

**Usando dos variables**


```
var React = require('react');
var ReactDOM = require('react-dom');
var styles = {
  background: 'lightblue',
  color:      'darkred'
};

var styleMe = <h1 style={styles}>Please style me!  I am so bland!</h1>;

ReactDOM.render(
	styleMe, 
	document.getElementById('app')
);
```


