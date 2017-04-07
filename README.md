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


