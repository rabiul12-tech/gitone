# 1.nextapp install 

Link : https://github.com/safak/next-blog

# to install command  line 
# always use this command 

```js 
git clone --single-branch -b starter https://github.com/safak/next-blog.git .
```






# 6 React documentation

1. react install
   npx create-react-app my-app
   cd my-app
   npm start

2. package for uuid (1:24)
   npm install uuid

3. package for React Icon (2:08:06)
   Link https://react-icons.github.io/react-icons/

npm install react-icons --save

3.  2nd package for font-awesome Icon (5:04:06)
    npm install --save font-awesome

         when use the icon you must go to the section and use it

4.(02:14:58)React Bootstrap styling in React

Link:: https://react-bootstrap.netlify.app/docs/getting-started/introduction
go to the link and open component and apply
it for your project

npm install react-bootstrap bootstrap

5.(05:48:21) form with formik package
npm install formik --save
Link https://formik.org/docs/overview

6. (06:04:47) Validate form using yuk package
   npm install yup --save
   Link : https://www.npmjs.com/package/yup

7. (07:51:20) react-toastify
   npm i react-toastify
   Link :https://www.npmjs.com/package/react-toastify

8. (09:58:29) react-router
   npm i react-router-dom

9. (11:28:01) JSON server
   npm i json-server
   npx json-server -p 3001 -w database/db.json

10. for swiper js slider

11. axios install
    npm i axios

<br>
<br>
<br>

# React Icon

package for React Icon (2:08:06)
Link https://react-icons.github.io/react-icons/

npm install react-icons --save

<details>
      <summary>
        React Icon 
     </summary>

```javascript
import React from "react";
import { FaFacebookSquare } from "react-icons/fa";

const ReactIcon = () => {
  return (
    <div>
      <button>
        <FaFacebookSquare />
      </button>
    </div>
  );
};

export default ReactIcon;
```

</details>
<br>

# React Bootstrap styling in React

4.(02:14:58)React Bootstrap styling in React

. Link:: https://react-bootstrap.netlify.app/docs/getting-started/introduction
go to the link and open component and apply
it for your project

npm install react-bootstrap bootstrap

<details>
      <summary>
       React Bootstrap
     </summary>

```javascript
import React from "react";
import "bootstrap/dist/css/bootstrap.min.css";
import Form from "react-bootstrap/Form";

import Button from "react-bootstrap/Button";
const ReactBootstrap = () => {
  return (
    <div>
      <h1>Hello </h1>
      <Button> hello </Button>
    </div>
  );
};

export default ReactBootstrap;
```

</details>
<br>
<br>
<br>

# Conditional rendering

<details>
      <summary>
      Conditional rendering
     </summary>

```javascript

  import React from "react";

const HomePage = () => {
  return <div>HomePage</div>;
};

export default HomePage;



import React, { useState } from "react";
import HomePage from "./HomePage";
import LogIn from "./LogIn";

const Index = () => {
  const [isLogn, setisLogn] = useState(false);
  return (
    <div>
      {/* {isLogn ? <LogIn /> : <HomePage />} tenary oparator  */}
      {isLogn && <HomePage />} short circuit
    </div>
  );
};

export default Index;



import React from "react";

const LogIn = () => {
  return <div>LogIn</div>;
};

export default LogIn;


```

</details>

<br>
<br>
<br>

# Bubling

<details>
      <summary>
       Bubling
     </summary>

```javascript
import "./App.css";

import { useState } from "react";

const childClick = (e) => {
  console.log("child click ");
  e.stopPropagation();
};
const parentclick = () => {
  console.log(" clickparentclick ");
};

function App() {
  return (
    <div className="parent" onClick={parentclick}>
      parenct <br />
      <br />
      <button onClick={childClick}>click </button>
    </div>
  );
}

export default App;
```

</details>

<br>
<br>
<br>

# EventHandling

<details>
      <summary>
       EventHandling  
     </summary>

```javascript
import React, { useState } from "react";

const EventHandling = () => {
  const [inPut, setinPut] = useState("");
  let handleChange = (e) => {
    setinPut(e.target.value);
    console.log(e.target.value);
  };
  return (
    <div>
      <h1>EventHandling </h1>

      <input type="text" onChange={handleChange} />

      <p>{inPut}</p>
    </div>
  );
};

export default EventHandling;
```

</details>

</br>
</br>

# Get Form data

<details>
      <summary>
       Get Form data
     </summary>

```javascript
import React, { useState } from "react";

const Form = () => {
  const [name, setname] = useState("");
  const [email, setemail] = useState("");
  const [password, setpassword] = useState("");

  let handleNameChange = (e) => {
    setname(e.target.value);
  };

  let handleEmailChange = (e) => {
    setemail(e.target.value);
  };

  let handlePassChange = (e) => {
    setpassword(e.target.value);
  };
  let handleSubmit = (e) => {
    console.log("form is submit ");
    e.preventDefault();

    console.log(name, email, password);
    let userInfo = {
      name: name,
      email: email,
      password: password,
    };
    console.log(userInfo);
  };
  return (
    <div>
      <h1>Registration Form </h1>
      <form action="" onSubmit={handleSubmit}>
        <div>
          <label htmlFor="name"> name : </label>
          <input
            type="text"
            name="name"
            id="name"
            value={name}
            onChange={handleNameChange}
            required
          />
        </div>
        <div>
          <label htmlFor="email"> Email : </label>
          <input
            type="email"
            name="email"
            id="email"
            value={email}
            onChange={handleEmailChange}
            required
          />
        </div>
        <div>
          <label htmlFor="password"> Password : </label>
          <input
            type="password"
            name="password"
            id="password"
            value={password}
            onChange={handlePassChange}
            required
          />
        </div>
        <div>
          <button type="submit"> register </button>
        </div>
      </form>
    </div>
  );
};

export default Form;




import React, { useState } from "react";

const Form2 = () => {
  const [user, setUser] = useState({
    name: "",
    email: "",
    password: "",
  });
  let { name, email, password } = user;

  // >>>>>>>>>>>>>>  different handlechange <<<<<<<<<<<<
  //   let handleNameChange = (e) => {
  //     setUser({ name: e.target.value, email, password });
  //   };

  //   let handleEmailChange = (e) => {
  //     setUser({ email: e.target.value, name, password });
  //   };

  //   let handlePassChange = (e) => {
  //     setUser({ password: e.target.value, name, email });
  //   };

  // >>>>>>>>>>>>>>  one  handlechange <<<<<<<<<<<<

  //   let handleChange = (e) => {
  //     let fieldName = e.target.name;
  //     if (fieldName === "name") {
  //       setUser({ name: e.target.value, email, password });
  //     }
  //     if (fieldName === "email") {
  //       setUser({ email: e.target.value, name, password });
  //     }
  //     if (fieldName === "password") {
  //       setUser({ password: e.target.value, email, name });
  //     }
  //   };

  // >>>>>>>>>>>>>>  one  handlechange one setUser  <<<<<<<<<<<<

  let handleChange = (e) => {
    setUser({ ...user, [e.target.name]: e.target.value });
  };

  let handleSubmit = (e) => {
    console.log("form is submit ");
    e.preventDefault();

    console.log(user);
  };

  return (
    <div>
      <h1>Registration Form </h1>
      <form action="" onSubmit={handleSubmit}>
        <div>
          <label htmlFor="name"> name : </label>
          <input
            type="text"
            name="name"
            id="name"
            value={name}
            onChange={handleChange}
            required
          />
        </div>
        <div>
          <label htmlFor="email"> Email : </label>
          <input
            type="email"
            name="email"
            id="email"
            value={email}
            onChange={handleChange}
            required
          />
        </div>
        <div>
          <label htmlFor="password"> Password : </label>
          <input
            type="password"
            name="password"
            id="password"
            value={password}
            onChange={handleChange}
            required
          />
        </div>
        <div>
          <button type="submit"> register </button>
        </div>
      </form>
    </div>
  );
};

export default Form2;

```

</details>

<br>
<br>

# Data transfer

<details>
      <summary>
       Data lifting 
     </summary>

```javascript
import React from "react";

const Child_To_Parent = (props) => {
  let data = " i am child element ";
  props.onChildData(data);
  return (
    <div>
      <h1>{props.data}</h1>
    </div>
  );
};

export default Child_To_Parent;

// <<<<<<<<<<<<<<<<<<<<<  App.js code >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

// import React, { useState } from "react";

// import "./App.css";
// import Child_To_Parent from "./components/8.Data_TRANSFER_CHILD_TO_PARENT/1.DataLifTing/Child_To_Parent";

// const App = () => {
//   let data = "i am come from app parent ";

//   let handleChildData = (childData) => {
//     console.log("App:" + childData);
//   };
//   return (
//     <div>
//       <Child_To_Parent data={data} onChildData={handleChildData} />
//     </div>
//   );
// };

// export default App;
```

</details>

<br>
<br>

# More data lifting

<details>
      <summary>
       More data lifting
     </summary>

```javascript
import React, { useState } from "react";

import "./App.css";
import NewToDo from "./NewToDo";
import Todo from "./Todo";

const App = () => {
  let data = "i am come from app parent ";

  let handleChildData = (childData) => {
    console.log("App:" + childData);
  };
  return (
    <div>
      <NewToDo onChildData={handleChildData} />
      <Todo data={data} />
    </div>
  );
};

export default App;


import React from "react";

const NewToDo = (props) => {
  let data = " i am child element ";
  props.onChildData({ title: "helo in  am a child onbject " });

  return <div>NewToDo</div>;
};




export default NewToDo;

import React from "react";

const Todo = (props) => {
  return (
    <div>
      <h1>{props.data} </h1>
    </div>
  );
};

export default Todo;


```

</details>
<br>
<br>

# Todo app

<details>
      <summary>
        Todo app
     </summary>

```javascript
import React, { useState } from "react";
import Todos from "./Todos";
import NewTodo from "./NewTodo";

let dummyToDos = ["make dinner", "wash car ", "go party "];
const Home = () => {
  const [todos, settodos] = useState(dummyToDos);

  let handleNewTodo = (newTodo) => {
    settodos([...todos, newTodo]);
  };

  return (
    <div>
      <NewTodo onTodo={handleNewTodo} />
      <Todos todos={todos} />
    </div>
  );
};

export default Home;

// <<<<<<<<<<<<<<< App.js >>>>>>>>>>>>>>>>>>>>>

// import React, { useState } from "react";

// import "./App.css";
// import Home from "./components/8.Data_TRANSFER_CHILD_TO_PARENT/3.TodoApp/Home";

// const App = () => {
//   return (
//     <div>
//       <Home />
//     </div>
//   );
// };

// export default App;



import React, { useState } from "react";

const NewTodo = (props) => {
  const [todo, setTodo] = useState("");
  let handleInputChange = (e) => {
    setTodo(e.target.value);
  };
  let handleSubmit = (e) => {
    e.preventDefault();
    props.onTodo(todo);
  };

  return (
    <div>
      <form action="" onSubmit={handleSubmit}>
        <label htmlFor="todo">New Todo : </label>
        <input type="text" name="todo" id="todo" onChange={handleInputChange} />
        <button>add todo </button>
      </form>
    </div>
  );
};

export default NewTodo;


import React from "react";

const Todo = (props) => {
  return (
    <div>
      <p>{props.todo}</p>
    </div>
  );
};

export default Todo;




import React from "react";
import Todo from "./Todo";

const Todos = (props) => {
  console.log(props.todos);
  return (
    <div>
      {props.todos.map((todo, index) => (
        <Todo key={index} todo={todo} />
      ))}
    </div>
  );
};

export default Todos;


```

</details>

<br>
<br>

# Todo app project

<details>
      <summary>
      Todo app project
     </summary>

```javascript
import React, { useState } from "react";
import Todos from "../4.ToDoAppProject/Todos";
import NewTodo from "./NewTodo";
import { v4 as uuidv4 } from "uuid";
let dummyToDos = [
  {
    id: 1,
    title: "todo title 1",
    desc: "todo1 descriptio is here ...",
  },

  {
    id: 2,
    title: "todo title 2",
    desc: "todo2 descriptio is here ...",
  },

  {
    id: 3,
    title: "todo title 3",
    desc: "todo3 descriptio is here ...",
  },
];
const Home = () => {
  const [todos, setTodos] = useState([]);

  let handleNewTodo = (todo) => {
    setTodos((prevTodo) => {
      return [...prevTodo, { id: uuidv4(), todo }];
    });
  };
  let handleRemoveToDo = (id) => {
    setTodos((prevTodo) => {
      let filtertodo = prevTodo.filter((todo) => todo.id !== id);
      return filtertodo;
    });
  };
  return (
    <div>
      <NewTodo onTodo={handleNewTodo} />
      <Todos todos={todos} onRemoveTodo={handleRemoveToDo} />
    </div>
  );
};

export default Home;

// <<<<<<<<<<<<<<<App.js >>>>>>>>>>>>>>>>>>>>>
// import React, { useState } from "react";

// import "./App.css";
// import Home from "./components/8.Data_TRANSFER_CHILD_TO_PARENT/4.ToDoAppProject/Home";

// const App = () => {
//   return (
//     <div>
//       <Home />
//     </div>
//   );
// };

// export default App;




import React, { useState } from "react";

const NewTodo = (props) => {
  const [todo, setTodo] = useState({
    title: "",
    desc: "",
  });
  let { title, desc } = todo;
  let handleInputChange = (e) => {
    let name = e.target.name;
    setTodo((oldTodo) => {
      return { ...oldTodo, [name]: e.target.value };
    });
  };
  let handleSubmit = (e) => {
    e.preventDefault();
    console.log(todo);
    props.onTodo(todo);
    setTodo({
      title: "",
      desc: "",
    });
  };

  return (
    <div>
      <form action="" onSubmit={handleSubmit}>
        <label htmlFor="title">Title : </label>
        <input
          type="text"
          name="title"
          id="title"
          value={title}
          onChange={handleInputChange}
        />

        <label htmlFor="desc">Description : </label>
        <input
          type="text"
          name="desc"
          id="desc"
          value={desc}
          onChange={handleInputChange}
        />

        <button type="submit">add todo </button>
      </form>
    </div>
  );
};

export default NewTodo;




import React from "react";

const Todo = (props) => {
  let { title, desc } = props.todo;

  let { id } = props;

  let handleClick = (id) => {
    props.onRemoveTodo(id);
  };
  return (
    <div>
      <article>
        <div>
          <h2>{title}</h2>
          <p>{desc}</p>
        </div>
        <div>
          <button
            onClick={() => {
              handleClick(id);
            }}
          >
            {" "}
            <i className="fa fa-trash fa-2x"></i>
          </button>
        </div>
      </article>
    </div>
  );
};

export default Todo;




import React from "react";
import Todo from "./Todo";

const Todos = (props) => {
  return (
    <div>
      {props.todos.map((todo, index) => (
        <Todo
          key={todo.id}
          todo={todo.todo}
          id={todo.id}
          onRemoveTodo={props.onRemoveTodo}
        />
      ))}
    </div>
  );
};

export default Todos;


```

</details>

<br>
<br>

# Form validation

# user Formik

5.(05:48:21) form with formik package
npm install formik --save
Link https://formik.org/docs/overview

<details>
      <summary>
      user Formik
     </summary>

```javascript
import React, { useState } from "react";
import { Formik, useFormik } from "formik";
const SignUp = () => {
  const formik = useFormik({
    initialValues: { name: "", email: "", password: "" },
    onSubmit: (values, { resetForm }) => {
      console.log(values);
      resetForm({ values: "" });
    },
  });

  return (
    <div>
      <h2>use formik signup </h2>
      <form action="" onSubmit={formik.handleSubmit}>
        <label htmlFor="name"> Name: </label>
        <input
          type="text"
          name="name"
          id="name"
          value={formik.values.name}
          onChange={formik.handleChange}
        />

        <label htmlFor="email"> Email: </label>
        <input
          type="text"
          name="email"
          id="email"
          value={formik.values.email}
          onChange={formik.handleChange}
        />

        <label htmlFor="password"> password: </label>
        <input
          type="password"
          name="password"
          id="password"
          value={formik.values.password}
          onChange={formik.handleChange}
        />
        <button type="submit">Sign Up </button>
      </form>
    </div>
  );
};

export default SignUp;
```

</details>

<br>
<br>

# 6. (06:04:47) Validate form using yuk package

npm install yup --save
Link : https://www.npmjs.com/package/yup

<details>
      <summary>
        using yuk
     </summary>

```javascript
import React, { useState } from "react";

const SignUp = () => {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
  let handleNameChange = (e) => {
    setName(e.target.value);
  };
  let handleEmailChange = (e) => {
    setEmail(e.target.value);
  };
  let handlePasswordChange = (e) => {
    setPassword(e.target.value);
  };

  let handleSubmit = (e) => {
    e.preventDefault();
    let newUser = {
      name,
      email,
      password,
    };
    console.log(newUser);
  };
  return (
    <div>
      <h2>use signup </h2>
      <form action="" onSubmit={handleSubmit}>
        <label htmlFor="name"> Name: </label>
        <input
          type="text"
          name="name"
          id="name"
          value={name}
          onChange={handleNameChange}
        />

        <label htmlFor="email"> Email: </label>
        <input
          type="text"
          name="email"
          id="email"
          value={email}
          onChange={handleEmailChange}
        />

        <label htmlFor="password"> password: </label>
        <input
          type="text"
          name="password"
          id="password"
          value={password}
          onChange={handlePasswordChange}
        />
        <button type="submit">Sign Up </button>
      </form>
    </div>
  );
};

export default SignUp;
```

</details>

# StateToggle

<details>
      <summary>
       StateToggle
     </summary>

```javascript
import React, { useState } from "react";

const Toggle = () => {
  const [toggle, setToggle] = useState(true);

  return (
    <div style={{ margin: "2rem", backgroundColor: "pink", padding: "2rem" }}>
      {toggle && (
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dicta,</p>
      )}

      <div style={{ textAlign: "center" }}>
        <button
          onClick={() => {
            setToggle(!toggle);
          }}
        >
          {toggle ? "Hide " : "Show"}
        </button>
      </div>
    </div>
  );
};

export default Toggle;
```

</details>

<br>
<br>

# React Toastyfy

7. (07:51:20) react-toastify
   npm i react-toastify
   Link :https://www.npmjs.com/package/react-toastify

<details>
      <summary>
       React Toastyfy
     </summary>

```javascript
import React from "react";
import { ToastContainer, toast } from "react-toastify";
import "react-toastify/dist/ReactToastify.css";
const TosTiFy = () => {
  const notify = () => toast("Wow so easy!");

  let deleteTodo = () => toast("delete todo ");
  return (
    <div>
      <h1>todo app</h1>
      <button onClick={notify}>Notify!</button>
      <button onClick={deleteTodo}>delete todo </button>
      <ToastContainer />
    </div>
  );
};

export default TosTiFy;
```

</details>
<br>
<br>

# DynamicStyle

<details>
      <summary>
       DynamicStyle
     </summary>

```javascript
import React from "react";

const DynamicStyle = () => {
  //   let error = false;
  let error = true;
  return (
    <div>
      <h1
        style={{
          color: error ? "red" : "green",
          backgroundColor: error ? "black" : "red",
        }}
      >
        wellcom
      </h1>
    </div>
  );
};

export default DynamicStyle;





import React, { useState, useEffect } from "react";
import "./DynamicStyle2.css";
const DynamicStyle2 = () => {
  const [name, setname] = useState("");
  const [validInput, setvalidInput] = useState(false);

  useEffect(() => {
    if (name.length < 2) {
      setvalidInput(false);
    } else {
      setvalidInput(true);
    }
  }, [name]);
  let handlechange = (e) => {
    setname(e.target.value);
  };
  return (
    <div>
      <h1>DynamicStyle2</h1>
      {/* <input
        type="text"
        value={name}
        onChange={handlechange}
        style={{ backgroundColor: validInput ? "green" : "red" }}
      /> */}

      {/* <input
        type="text"
        value={name}
        onChange={handlechange}
        className={` ${validInput ? "valid" : "invalid"}`}
      /> */}

      <input
        type="text"
        value={name}
        onChange={handlechange}
        className={` ${validInput && "valid"}`}
      />
    </div>
  );
};

export default DynamicStyle2;

```

</details>

<br>
<br>

# Fragment

<details>
      <summary>
        # Fragment
     </summary>

```javascript
import React from "react";

const Column = () => {
  return (
    <>
      <td>Rabiul </td>
      <td>30 years old </td>
    </>
  );
};

export default Column;

import React from "react";
import Column from "./Column";

const Table = () => {
  return (
    <div>
      {" "}
      <table>
        <tr>
          <Column />
        </tr>
        <tr>
          <Column />
        </tr>
        <tr>
          <Column />
        </tr>
      </table>
    </div>
  );
};

export default Table;



import React, { Fragment } from "react";

const Fragment1 = () => {
  return (
    <div>
      <h1> Fragment1</h1>
      <>
        <h1> empty fragment </h1>
        <p>hello fragment </p>
      </>
      <Fragment>
        <h1>fragment </h1>
        <p>hello fragment </p>
      </Fragment>

      <React.Fragment>
        <h1>React.Fragment </h1>
        <p>hello fragment </p>
      </React.Fragment>
    </div>
  );
};

export default Fragment1;

```

</details>

<br>
<br>

# React prototype

<details>
      <summary>
        React prototype 
     </summary>

```javascript
import React, { useState } from "react";
import UserComponent from "./UserComponent";

// ProTypes -check data types of props

const User = () => {
  const [userName, setuserName] = useState("jo bidan ");

  const [userId, setuserId] = useState("1021");

  return (
    <div>
      <UserComponent userName={userName} userId={userId} />
    </div>
  );
};

export default User;


// import React from "react";
// import PropTypes from "prop-types";

// console.log(PropTypes);
// const UserComponent = (props) => {
//   return (
//     <div>
//       <h1>{props.userName}</h1>
//       <h1>{props.userId}</h1>
//     </div>
//   );
// };
// UserComponent.PropTypes = {
//   userName: PropTypes.string,
//   userId: PropTypes.number,
// };

// UserComponent.defaultProps = {};
// export default UserComponent;

import React from "react";
import PropTypes from "prop-types";

const UserComponent = (props) => {
  return (
    <div>
      <h1>{props.userName}</h1>
      <h1>{props.userId}</h1>
    </div>
  );
};

UserComponent.propTypes = {
  userName: PropTypes.string,
  userId: PropTypes.number,
};

UserComponent.defaultProps = {};

export default UserComponent;

```

</details>

<br>
<br>

# React Router

# dynamic routing

<details>
      <summary>
       dynamic routing
     </summary>

```javascript
export const blogsData = [
  {
    id: 1,
    title: "Html",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 2,
    title: "CSS",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 3,
    title: "Javascript",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 4,
    title: "PHP",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 5,
    title: "Python",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
];

// <<<<<<<<<<<<<<<<<<< dynamic routing <<<<<<<<<<<<<<<<<<<<<<<
// import React, { useState } from "react";

// import { BrowserRouter, Routes, Route } from "react-router-dom";

// import "./App.css";
// import ReactRouter from "./components/16.ReactRouter/ReactRouter";
// import Contact from "./components/16.ReactRouter/Contact";

// import Vlog from "./components/16.ReactRouter/Vlog";
// import Blog from "./components/16.ReactRouter/Blog";
// import Error from "./components/16.ReactRouter/Error";
// import Navbar from "./components/16.ReactRouter/0.Part2NavStyle/Navbar";
// const App = () => {
//   return (
//     <BrowserRouter>
//       <Navbar />
//       <Routes>
//         <Route path="/" element={<ReactRouter />}></Route>
//         <Route path="/contact" element={<Contact />}></Route>
//         <Route path="/blog" element={<Vlog />}></Route>
//         <Route path="/blog/:title" element={<Blog />}></Route>
//         <Route path="*" element={<Error />}></Route>
//       </Routes>
//     </BrowserRouter>
//   );
// };

// export default App;
```

</details>
<br>
<br>

# useLocation

<details>
      <summary>
        useLocation
     </summary>

```javascript
import React, { useState, useEffect } from "react";
import { useParams, useLocation } from "react-router-dom";
import { blogsData } from "../1.DynamicRouting/data";
const Blog = () => {
  const { title } = useParams();
  const location = useLocation();
  console.log(location);

  return (
    <div>
      <h1>{title}</h1>
      <p>{location.state.desc.slice(0, 500)} </p>
      <p>{location.state.desc.slice(501, 900)} </p>
    </div>
  );
};

export default Blog;

// <<<<<<<<<<<<<<<<<<<<<< app .js >>>>>>>>>>>>>>>>>>

// import React, { useState } from "react";

// import { BrowserRouter, Routes, Route } from "react-router-dom";

// import "./App.css";
// import ReactRouter from "./components/16.ReactRouter/ReactRouter";
// import Contact from "./components/16.ReactRouter/Contact";

// import Vlog from "./components/16.ReactRouter/Vlog";
// import Blog from "./components/16.ReactRouter/2.UseLcation/Blog";
// import Error from "./components/16.ReactRouter/Error";
// import Navbar from "./components/16.ReactRouter/0.Part2NavStyle/Navbar";
// const App = () => {
//   return (
//     <BrowserRouter>
//       <Navbar />
//       <Routes>
//         <Route path="/" element={<ReactRouter />}></Route>
//         <Route path="/contact" element={<Contact />}></Route>
//         <Route path="/blog" element={<Vlog />}></Route>
//         <Route path="/blog/:title" element={<Blog />}></Route>
//         <Route path="*" element={<Error />}></Route>
//       </Routes>
//     </BrowserRouter>
//   );
// };

// export default App;
```

</details>

<br>
<br>

# Query parameters

<details>
      <summary>
      Query parameters
     </summary>

```javascript
import React, { useState } from "react";
import { Placeholder } from "react-bootstrap";
import { useParams, useSearchParams } from "react-router-dom";
const User = () => {
  //   const { userid } = useParams();
  const [searchParam, setSearchParams] = useSearchParams();
  console.log(searchParam.get("id"));
  const [name, setname] = useState("");
  const [age, setAge] = useState("");

  let handlesubmit = (e) => {
    e.preventDefault();
    setSearchParams({ name: name, age: age });
  };

  return (
    <div>
      {/* <h1>{userid} </h1> */}
      {/* http://localhost:3000/user?id=500&age=30&name=Rabiul

      */}
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          value={name}
          placeholder="name"
          onChange={(e) => {
            setname(e.target.value);
          }}
        />
        <input
          type="text"
          value={age}
          placeholder="age"
          onChange={(e) => {
            setAge(e.target.value);
          }}
        />
        <button type="submit">find User</button>
      </form>
      <h1>{searchParam.get("id")} </h1>
      <h1>{searchParam.get("age")} </h1>
      <h1>{searchParam.get("name")} </h1>
    </div>
  );
};

export default User;

// import React, { useState } from "react";

// import { BrowserRouter, Routes, Route } from "react-router-dom";

// import "./App.css";
// import ReactRouter from "./components/16.ReactRouter/3.QueryParameter/ReactRouter";
// import Contact from "./components/16.ReactRouter/3.QueryParameter/Contact";

// import Vlog from "./components/16.ReactRouter/3.QueryParameter/Vlog";
// import Blog from "./components/16.ReactRouter/3.QueryParameter/Blog";
// import Error from "./components/16.ReactRouter/3.QueryParameter/Error";
// import Navbar from "./components/16.ReactRouter/0.Part2NavStyle/Navbar";
// import User from "./components/16.ReactRouter/3.QueryParameter/User";
// const App = () => {
//   return (
//     <BrowserRouter>
//       <Navbar />
//       <Routes>
//         <Route path="/" element={<ReactRouter />}></Route>
//         <Route path="/contact" element={<Contact />}></Route>
//         <Route path="/blog" element={<Vlog />}></Route>
//         <Route path="/blog/:title" element={<Blog />}></Route>
//         <Route path="*" element={<Error />}></Route>
//         {/* <Route path="/user/:userid" element={<User />}></Route> // route parameter  */}
//         <Route path="/user" element={<User />}></Route>{" "}
//         {/* query paramweter  */}
//       </Routes>
//     </BrowserRouter>
//   );
// };

// export default App;



import React, { useState, useEffect } from "react";
import { useParams, useLocation } from "react-router-dom";
import { blogsData } from "../1.DynamicRouting/data";
const Blog = () => {
  const { title } = useParams();
  const location = useLocation();
  console.log(location);

  return (
    <div>
      <h1>{title}</h1>
      <p>{location.state.desc.slice(0, 500)} </p>
      <p>{location.state.desc.slice(501, 900)} </p>
    </div>
  );
};

export default Blog;


import React from "react";
import { useNavigate } from "react-router-dom";

const Contact = () => {
  const navigate = useNavigate();
  return (
    <div>
      <h1>Contact page </h1>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      {/* redirect  */}

      <button
        onClick={() => {
          navigate("/");
        }}
      >
        Go to the home page{" "}
      </button>
    </div>
  );
};

export default Contact;


export const blogsData = [
  {
    id: 1,
    title: "Html",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 2,
    title: "CSS",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 3,
    title: "Javascript",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 4,
    title: "PHP",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
  {
    id: 5,
    title: "Python",
    desc: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
        `,
  },
];

// <<<<<<<<<<<<<<<<<<< dynamic routing <<<<<<<<<<<<<<<<<<<<<<<
// import React, { useState } from "react";

// import { BrowserRouter, Routes, Route } from "react-router-dom";

// import "./App.css";
// import ReactRouter from "./components/16.ReactRouter/ReactRouter";
// import Contact from "./components/16.ReactRouter/Contact";

// import Vlog from "./components/16.ReactRouter/Vlog";
// import Blog from "./components/16.ReactRouter/Blog";
// import Error from "./components/16.ReactRouter/Error";
// import Navbar from "./components/16.ReactRouter/0.Part2NavStyle/Navbar";
// const App = () => {
//   return (
//     <BrowserRouter>
//       <Navbar />
//       <Routes>
//         <Route path="/" element={<ReactRouter />}></Route>
//         <Route path="/contact" element={<Contact />}></Route>
//         <Route path="/blog" element={<Vlog />}></Route>
//         <Route path="/blog/:title" element={<Blog />}></Route>
//         <Route path="*" element={<Error />}></Route>
//       </Routes>
//     </BrowserRouter>
//   );
// };

// export default App;



import React from "react";

const Error = () => {
  return (
    <div>
      <h1>Page not found </h1>
    </div>
  );
};

export default Error;



import React from "react";

const ReactRouter = () => {
  return (
    <div>
      <h1>Home page </h1>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
    </div>
  );
};

export default ReactRouter;



import React, { useState } from "react";
import { blogsData } from "./data";
import { Link, NavLink } from "react-router-dom";
const Vlog = () => {
  const [blogs, setblogs] = useState(blogsData);

  let truncateString = (str, num) => {
    if (str.length > num) {
      return str.slice(0, num) + " ... ";
    } else {
      return str;
    }
  };
  return (
    <div>
      <h1>Blog page </h1>
      <section>
        {blogs.map((blog) => {
          let { id, title, desc } = blog;
          return (
            <article key={id}>
              <h3>{title}</h3>
              <p>{truncateString(desc, 100)}</p>
              <Link to={title} state={{ id, title, desc }}>
                {" "}
                Learn More{" "}
              </Link>
            </article>
          );
        })}
      </section>
    </div>
  );
};

export default Vlog;


```

</details>

</br></br>

# Prtect Routing

<details>
      <summary>
        Prtect Routing 
     </summary>

```javascript
import React, { useState, useEffect } from "react";
import { useParams } from "react-router-dom";
import { blogsData } from "./1.DynamicRouting/data";
const Blog = () => {
  const { title } = useParams();
  const [bodyData, setbodyData] = useState("");

  useEffect(() => {
    const blogData = blogsData.filter((blog) => blog.title === title);
    setbodyData(blogData[0].desc);
  });
  return (
    <div>
      <h1>{title}</h1>
      <p>{bodyData.slice(0, 500)} </p>
      <p>{bodyData.slice(501, 900)} </p>
    </div>
  );
};

export default Blog;



import React from "react";
import { useNavigate } from "react-router-dom";

const Contact = () => {
  const navigate = useNavigate();
  return (
    <div>
      <h1>Contact page </h1>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      {/* redirect  */}

      <button
        onClick={() => {
          navigate("/");
        }}
      >
        Go to the home page{" "}
      </button>
    </div>
  );
};

export default Contact;



import React from "react";

const Error = () => {
  return (
    <div>
      <h1>Page not found </h1>
    </div>
  );
};

export default Error;



import React from "react";

const ReactRouter = () => {
  return (
    <div>
      <h1>Home page </h1>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt</p>
    </div>
  );
};

export default ReactRouter;




import React, { useState } from "react";
import { blogsData } from "./1.DynamicRouting/data";
import { Link, NavLink } from "react-router-dom";
const Vlog = () => {
  const [blogs, setblogs] = useState(blogsData);

  let truncateString = (str, num) => {
    if (str.length > num) {
      return str.slice(0, num) + " ... ";
    } else {
      return str;
    }
  };
  return (
    <div>
      <h1>Blog page </h1>
      <section>
        {blogs.map((blog) => {
          let { id, title, desc } = blog;
          return (
            <article key={id}>
              <h3>{title}</h3>
              <p>{truncateString(desc, 100)}</p>
              <Link to={title} state={{ id, title, desc }}>
                {" "}
                Learn More{" "}
              </Link>
            </article>
          );
        })}
      </section>
    </div>
  );
};

export default Vlog;


```

</details>

<br> 
<br>

# JSON server

9.(11:28:01) JSON server
npm i json-server
npx json-server -p 3001 -w database/db.json

<details>
      <summary>
        JSON server
     </summary>

```javascript
{
  "users": [
    {
      "id": 1,
      "name": "John Doe",
      "email": "john.doe@example.com"
    },
    {
      "id": 2,
      "name": "Jane Smith",
      "email": "jane.smith@example.com"
    },
    {
      "id": 3,
      "name": "Bob Johnson",
      "email": "bob.johnson@example.com"
    },
    {
      "id": 4,
      "name": "Takael  Johnson",
      "email": "Takael.johnson@example.com"
    }
  ]
}


import React, { useEffect, useState } from "react";

import "./App.css";
import axios from "axios";

const App = () => {
  const [user, setuser] = useState([]);

  const getAllUsers = async () => {
    const response = await axios.get("http://localhost:3001/users");
    setuser(response.data);
  };

  useEffect(() => {
    getAllUsers();
  }, []);
  return (
    <div>
      <h1>
        {user.map((use) => {
          return (
            <article key={use.id}>
              <h2>{use.name}</h2>
              <h2>{use.email}</h2>
            </article>
          );
        })}
      </h1>
    </div>
  );
};

export default App;

```

</details>

<br>
<br>

# Custom Hooks

<details>
      <summary>
        Custom Hooks
     </summary>

```javascript
import React, { useEffect, useState } from "react";
import useFetch from "./useFetch";

const CusTomHooks = () => {
  const { data, loading, error } = useFetch(
    "https://jsonplaceholder.typicode.com/todos"
  );
  const loadingMessage = <p>todo is loading </p>;
  const erroegMessage = <p>{error} </p>;

  let todoElement =
    data &&
    data.map((todo) => {
      return <p key={todo.id}>{todo.title}</p>;
    });

  return (
    <div>
      <h1> DataFetch</h1>
      {error && erroegMessage}
      {loading && loadingMessage}
      {todoElement}
    </div>
  );
};

export default CusTomHooks;


import React, { useEffect, useState } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);

  const [loading, setloading] = useState(true);
  const [error, seterror] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((response) => {
        if (!response.ok) {
          throw Error("Fetching is not successful ");
        } else {
          return response.json();
        }
      })
      .then((data) => {
        setData(data);
        setloading(false);
        seterror(false);
      })
      .catch((error) => {
        seterror(error.message);
        setloading(false);
      });
  }, [url]);

  return { data, loading, error };
};

export default useFetch;

```

</details>

</br>
</br>
</br>

# useReducer

<details>
      <summary>
        useReducer
     </summary>

```javascript
import React, { useReducer, useState } from "react";

// books , modalText , isModalOpen
// add book - modalText
// remove  book - modalText

let booksData = [
  {
    id: 1,
    name: "pather pachali",
  },
  {
    id: 2,
    name: "mater moina ",
  },
  {
    id: 3,
    name: " hari porter ",
  },
];

const Modal = ({ modalText }) => {
  return <p>{modalText}</p>;
};

const UseReducer = () => {
  const [books, setbooks] = useState(booksData);
  const [ismodalOpen, setIsmodalOpen] = useState(false);
  const [modalText, setmodalText] = useState("");

  const [bookName, setbookName] = useState("");
  let handlesubmit = (e) => {
    e.preventDefault();

    setbooks((prev) => {
      let newbook = { id: new Date().getTime().toString(), name: bookName };
      return [...prev, newbook];
    });
    setIsmodalOpen(true);
    setmodalText("modal text is add ");
  };
  const removeBook = (id) => {
    let fiterbook = books.filter((book) => book.id !== id);
    setbooks(fiterbook);
  };
  return (
    <div>
      <h1>Book List </h1>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          value={bookName}
          onChange={(e) => setbookName(e.target.value)}
        />
        <button type="submit"> submit</button>
      </form>
      {ismodalOpen && <Modal modalText={modalText} />}

      {books.map((book) => {
        let { id, name } = book;
        return (
          <li>
            {name}
            <button onClick={() => removeBook(id)}>remove </button>
          </li>
        );
      })}
    </div>
  );
};

export default UseReducer;

export const reducer = (state, action) => {
  // action.type action.payload

  if (action.type === "ADD") {
    const allBooks = [...state.books, action.payload];
    return {
      ...state,
      books: allBooks,
      ismodalOpen: true,
      modalText: "Book is added ",
    };
  }
  if (action.type === "REMOVE") {
    const filterBooks = [...state.books].filter(
      (book) => book.id !== action.payload
    );
    return {
      ...state,
      books: filterBooks,
      ismodalOpen: true,
      modalText: "Book is removed ",
    };
  }

  return state;
};



import React, { useReducer, useState } from "react";
import { reducer } from "./reducer";
let booksData = [
  {
    id: 1,
    name: "pather pachali",
  },
  {
    id: 2,
    name: "mater moina ",
  },
  {
    id: 3,
    name: " hari porter ",
  },
];

const Modal = ({ modalText }) => {
  return <p>{modalText}</p>;
};
const initialState = {
  books: booksData,
  ismodalOpen: false,
  modalText: "",
};
const UseReducer1 = () => {
  const [bookState, dispatch] = useReducer(reducer, initialState);

  const [bookName, setbookName] = useState("");
  let handlesubmit = (e) => {
    e.preventDefault();
    let newbook = { id: new Date().getTime().toString(), name: bookName };

    dispatch({ type: "ADD", payload: newbook });
  };

  let removeBook = (id) => {
    // remove book

    dispatch({ type: "REMOVE", payload: id });
  };

  return (
    <div>
      <h1>Book List </h1>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          value={bookName}
          onChange={(e) => setbookName(e.target.value)}
        />
        <button type="submit"> submit</button>
      </form>
      {bookState && <Modal modalText={bookState.modalText} />}

      {bookState.books.map((book) => {
        let { id, name } = book;
        return (
          <li>
            {name}{" "}
            <button
              onClick={() => {
                removeBook(id);
              }}
            >
              remove{" "}
            </button>
          </li>
        );
      })}
    </div>
  );
};

export default UseReducer1;

```

</details>

<br>
<br>

# useContext

<details>
      <summary>
        part 1 Basic 
     </summary>

```javascript
import React, { useState } from "react";
import Component2 from "./Component2";
import { userContext } from "./UserContext";

const Component1 = () => {
  const [user, setuser] = useState({
    id: 101,
    name: "todo list",
  });
  const [text, setText] = useState("helo this is a text");
  return (
    <div>
      <userContext.Provider value={{ user, text }}>
        <Component2 />
      </userContext.Provider>
    </div>
  );
};

export default Component1;

//  <userContext.Provider value={user}>
//       <Component2 />
//     </userContext.Provider>

// Component1  > Component2 > Component3 > Component4

// import React from "react";
// import Component1 from "./components/6.Hooks/6.useContext/Component1";

// const App = () => {
//   return (
//     <div>
//       <Component1 />
//     </div>
//   );
// };

// export default App;


import React from "react";
import Component3 from "./Component3";

const Component2 = () => {
  return (
    <div>
      <Component3 />
    </div>
  );
};

export default Component2;


import React from "react";
import Component4 from "./Component4";
const Component3 = () => {
  return (
    <div>
      <Component4 />
    </div>
  );
};

export default Component3;

import React, { useContext } from "react";
import { userContext } from "./UserContext";
const Component4 = () => {
  // const user = useContext(userContext);
  const { user, text } = useContext(userContext);

  console.log(text);
  return (
    <div>
      Component4
      <h1>{text}</h1>
      <p>{user.id}</p>
      <p>{user.name}</p>
    </div>
  );
};

export default Component4;

import React, { useState } from "react";

export const userContext = React.createContext();

// provider consumer

//step :1 create context
// step 2: wrap childs wiht context provider
// step 3: state access useContext hook

```

</details>

# part 2

<details>
      <summary>
      Part 2 
     </summary>

```javascript
import React, { useState } from "react";

export const userContext = React.createContext();

// provider consumer

//step :1 create context
// step 2: wrap childs wiht context provider
// step 3: state access useContext hook
```

</details>

<br>
<br>

## Normal usermanagement

<details>
      <summary>
        Normal usermanagement
     </summary>

```javascript
// App.js;

import React, { useState } from "react";

import Users from "./component/userContext/2.UserManagement/Users";
import "./App.css";
import NewUsers from "./component/userContext/2.UserManagement/NewUsers";
const App = () => {
  const [users, setusers] = useState([
    { id: 1, username: "valadir putin " },
    { id: 2, username: "md arodan  " },
  ]);

  let deleteUser = (id) => {
    let filteruser = users.filter((user) => user.id !== id);
    setusers(filteruser);
  };
  let handleNewuser = (newuser) => {
    setusers((preuser) => [...preuser, newuser]);
  };
  return (
    <div>
      <NewUsers handleNewuser={handleNewuser} />
      <Users users={users} deleteUser={deleteUser} />
    </div>
  );
};

export default App;


import React, { useState } from "react";

const NewUsers = ({ handleNewuser }) => {
  const [username, setusername] = useState("");

  const handleuerChange = (e) => {
    setusername(e.target.value);
  };
  const handlesubmit = (e) => {
    e.preventDefault();
    let newuser = { id: new Date().getTime().toString(), username: username };

    handleNewuser(newuser);
    setusername("");
  };
  return (
    <div>
      <h2>user registreation </h2>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          name="username"
          value={username}
          onChange={handleuerChange}
        />
        <button type="submit">add user </button>
      </form>
    </div>
  );
};

export default NewUsers;


import React from "react";

const User = ({ user, deleteUser }) => {
  let { id, username } = user;
  let handleclick = (id) => {
    deleteUser(id);
  };
  return (
    <div>
      <article className="user">
        <p> {id}</p>
        <h2>{username}</h2>
        <button
          onClick={() => {
            handleclick(id);
          }}
        >
          delete{" "}
        </button>
      </article>
    </div>
  );
};

export default User;



import React from "react";
import User from "./User";
import "../../../App.css";
const Users = ({ users, deleteUser }) => {
  return (
    <div>
      <section className="grid">
        {users.map((user) => (
          <User key={user.id} user={user} deleteUser={deleteUser} />
        ))}
      </section>
    </div>
  );
};

export default Users;



```

</details>
<br>
<br>

# useContext userManagement

<details>
      <summary>
      First   useContext
     </summary>

```javascript
// App.js;

import React, { useState } from "react";
import { userContext } from "./component/userContext/UserContext";
import Users from "./component/userContext/2.UserManagement/Users";
import "./App.css";
import NewUsers from "./component/userContext/2.UserManagement/NewUsers";
const App = () => {
  const [users, setusers] = useState([
    { id: 1, username: "valadir putin " },
    { id: 2, username: "md arodan" },
  ]);

  let deleteUser = (id) => {
    let filteruser = users.filter((user) => user.id !== id);
    setusers(filteruser);
  };
  let handleNewuser = (newuser) => {
    setusers((preuser) => [...preuser, newuser]);
  };

  return (
    <userContext.Provider value={{ users, setusers }}>
      <NewUsers />
      <Users users={users} deleteUser={deleteUser} />
    </userContext.Provider>
  );
};

export default App;


import React, { useState, useContext } from "react";
import { userContext } from "../UserContext";

const NewUsers = () => {
  const { users, setusers } = useContext(userContext);

  const [username, setusername] = useState("");

  const handleuerChange = (e) => {
    setusername(e.target.value);
  };
  const handlesubmit = (e) => {
    e.preventDefault();
    let newuser = { id: new Date().getTime().toString(), username: username };

    setusers((preuser) => [...preuser, newuser]);
    setusername("");
  };
  return (
    <div>
      <h2>user registreation </h2>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          name="username"
          value={username}
          onChange={handleuerChange}
        />
        <button type="submit">add user </button>
      </form>
    </div>
  );
};

export default NewUsers;



import React, { useState, useContext } from "react";
import { userContext } from "../UserContext";

const User = ({ user }) => {
  const { users, setusers } = useContext(userContext);
  let { id, username } = user;

  let handleclick = (id) => {
    let filteruser = users.filter((user) => user.id !== id);
    setusers(filteruser);
  };
  return (
    <div>
      <article className="user">
        <p> {id}</p>
        <h2>{username}</h2>
        <button
          onClick={() => {
            handleclick(id);
          }}
        >
          delete{" "}
        </button>
      </article>
    </div>
  );
};

export default User;

import React, { createContext } from "react";

export const userContext = React.createContext({});



import React, { useState, useContext } from "react";
import { userContext } from "../UserContext";
import User from "./User";
import "../../../App.css";
const Users = () => {
  const { users, setusers } = useContext(userContext);
  return (
    <div>
      <section className="grid">
        {users.map((user) => (
          <User key={user.id} user={user} />
        ))}
      </section>
    </div>
  );
};

export default Users;

```

</details>

<br>
<br>

# Custom Hooks

<details>
      <summary>
        Custom Hooks
     </summary>

```javascript
import React, { useContext } from "react";
import { userContext } from "../../UserContext";

export const useUserContext = () => {
  return useContext(userContext);
};

// App.js;

import React, { useState } from "react";
import UsersProvider from "./component/userContext/UserContext";
import Users from "./component/userContext/2.UserManagement/Users";
import "./App.css";
import NewUsers from "./component/userContext/2.UserManagement/NewUsers";
const App = () => {
  return (
    <UsersProvider>
      <NewUsers />
      <Users />
    </UsersProvider>
  );
};

export default App;


import React, { useState } from "react";

import { useUserContext } from "./CustomHook/userUserContext";

const NewUsers = () => {
  const { users, setusers } = useUserContext();

  const [username, setusername] = useState("");

  const handleuerChange = (e) => {
    setusername(e.target.value);
  };
  const handlesubmit = (e) => {
    e.preventDefault();
    let newuser = { id: new Date().getTime().toString(), username: username };

    setusers((preuser) => [...preuser, newuser]);
    setusername("");
  };
  return (
    <div>
      <h2>user registreation </h2>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          name="username"
          value={username}
          onChange={handleuerChange}
        />
        <button type="submit">add user </button>
      </form>
    </div>
  );
};

export default NewUsers;




import React, { useState } from "react";
import { useUserContext } from "./CustomHook/userUserContext";

const User = ({ user }) => {
  const { users, setusers } = useUserContext();
  let { id, username } = user;

  let handleclick = (id) => {
    let filteruser = users.filter((user) => user.id !== id);
    setusers(filteruser);
  };
  return (
    <div>
      <article className="user">
        <p> {id}</p>
        <h2>{username}</h2>
        <button
          onClick={() => {
            handleclick(id);
          }}
        >
          delete{" "}
        </button>
      </article>
    </div>
  );
};

export default User;



import React, { createContext, useState } from "react";

export const userContext = React.createContext({});

const UsersProvider = ({ children }) => {
  const [users, setusers] = useState([
    { id: 1, username: "valadir putin " },
    { id: 2, username: "md arodan" },
  ]);

  return (
    <userContext.Provider value={{ users, setusers }}>
      {children}
    </userContext.Provider>
  );
};

export default UsersProvider;


import React, { useState } from "react";

import User from "./User";
import "../../../App.css";
import { useUserContext } from "./CustomHook/userUserContext";
const Users = () => {
  const { users, setusers } = useUserContext();

  return (
    <div>
      <section className="grid">
        {users.map((user) => (
          <User key={user.id} user={user} />
        ))}
      </section>
    </div>
  );
};

export default Users;


```

</details>

<br>
<br>

# useReducer + useContext

# 1.useReducer + useContext

<details>
      <summary>
      folder   context
     </summary>

```javascript
import React, { createContext, useState, useReducer } from "react";
import { initialstate, reducer } from "./reducer/usersReducer";

export const userContext = React.createContext({});

const UsersProvider = ({ children }) => {
  const [users, setusers] = useState([]);

  const [state, dispatch] = useReducer(reducer, initialstate);

  return (
    <userContext.Provider value={{ state, dispatch }}>
      {children}
    </userContext.Provider>
  );
};

export default UsersProvider;
```

</details>
<br>
<details>
      <summary>
      folder   customhooks 
     </summary>

```javascript
import React, { useContext } from "react";
import { userContext } from "../../UserContext";

export const useUserContext = () => {
  return useContext(userContext);
};
```

</details>

<br>
<details>
      <summary>
      folder   reducer  
     </summary>

```javascript
export const initialstate = {
  users: [
    { id: 1, username: "valadir putin" },
    { id: 2, username: "md arodan" },
  ],
};

export const reducer = (state, action) => {
  switch (action.type) {
    case "ADD":
      let allbooks = [...state.users, action.payload];
      return {
        ...state,
        users: allbooks,
      };

    case "DELETE":
      let filterbook = [
        ...state.users.filter((user) => user.id !== action.payload),
      ];
      return {
        ...state,
        users: filterbook,
      };

    default:
      return state;
  }
};
```

</details>

<br>

<details>
      <summary>
      all files 
     </summary>

```javascript
// App.js;

import React, { useState } from "react";
import UsersProvider from "./component/userContext/UserContext";
import Users from "./component/userContext/2.UserManagement/Users";
import "./App.css";
import NewUsers from "./component/userContext/2.UserManagement/NewUsers";
const App = () => {
  return (
    <UsersProvider>
      <NewUsers />
      <Users />
    </UsersProvider>
  );
};

export default App;


import React, { useState } from "react";

import { useUserContext } from "./CustomHook/userUserContext";

const NewUsers = () => {
  const { state, dispatch } = useUserContext();

  const [username, setusername] = useState("");

  const handleuerChange = (e) => {
    setusername(e.target.value);
  };
  const handlesubmit = (e) => {
    e.preventDefault();
    let newuser = { id: new Date().getTime().toString(), username: username };

    dispatch({ type: "ADD", payload: newuser });
    setusername("");
  };
  return (
    <div>
      <h2>user registreation </h2>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          name="username"
          value={username}
          onChange={handleuerChange}
        />
        <button type="submit">add user </button>
      </form>
    </div>
  );
};

export default NewUsers;



import React, { useState } from "react";
import { useUserContext } from "./CustomHook/userUserContext";

const User = ({ user }) => {
  const { state, dispatch } = useUserContext();
  let { id, username } = user;

  let handleclick = (id) => {
    dispatch({ type: "DELETE", payload: id });
  };
  return (
    <div>
      <article className="user">
        <p> {id}</p>
        <h2>{username}</h2>
        <button
          onClick={() => {
            handleclick(id);
          }}
        >
          delete{" "}
        </button>
      </article>
    </div>
  );
};

export default User;


import React, { useState } from "react";

import User from "./User";
import "../../../App.css";
import { useUserContext } from "./CustomHook/userUserContext";

const Users = () => {
  const { state, dispatch } = useUserContext();

  return (
    <div>
      <section className="grid">
        {state.users.map((user) => (
          <User key={user.id} user={user} />
        ))}
      </section>
    </div>
  );
};

export default Users;


```

</details>
<br>
<br>

# 2 useReducer + useContext

<details>
      <summary>
      folder   context
     </summary>

```javascript
import React, { createContext, useState, useReducer } from "react";
import { initialstate, reducer } from "./reducer/usersReducer";

export const userContext = React.createContext({});

const UsersProvider = ({ children }) => {
  const [users, setusers] = useState([]);

  const [state, dispatch] = useReducer(reducer, initialstate);

  const value = {
    users: state.users,
    addUser: (newuser) => {
      dispatch({ type: "ADD", payload: newuser });
    },
    deleteUser: (id) => {
      dispatch({ type: "DELETE", payload: id });
    },
  };

  return <userContext.Provider value={value}>{children}</userContext.Provider>;
};

export default UsersProvider;
```

</details>
<br>
<details>
      <summary>
      folder   customhooks 
     </summary>

```javascript
import React, { useContext } from "react";
import { userContext } from "../../UserContext";

export const useUserContext = () => {
  return useContext(userContext);
};
```

</details>

<br>
<details>
      <summary>
      folder   reducer  
     </summary>

```javascript
export const initialstate = {
  users: [
    { id: 1, username: "valadir putin" },
    { id: 2, username: "md arodan" },
  ],
};

export const reducer = (state, action) => {
  switch (action.type) {
    case "ADD":
      let allbooks = [...state.users, action.payload];
      return {
        ...state,
        users: allbooks,
      };

    case "DELETE":
      let filterbook = [
        ...state.users.filter((user) => user.id !== action.payload),
      ];
      return {
        ...state,
        users: filterbook,
      };

    default:
      return state;
  }
};
```

</details>

<br>

<details>
      <summary>
      all files 
     </summary>

```javascript
// App.js;

import React, { useState } from "react";
import UsersProvider from "./component/userContext/UserContext";
import Users from "./component/userContext/2.UserManagement/Users";
import "./App.css";
import NewUsers from "./component/userContext/2.UserManagement/NewUsers";
const App = () => {
  return (
    <UsersProvider>
      <NewUsers />
      <Users />
    </UsersProvider>
  );
};

export default App;



import React, { useState } from "react";

import { useUserContext } from "./CustomHook/userUserContext";

const NewUsers = () => {
  const { users, addUser, deleteUser } = useUserContext();

  const [username, setusername] = useState("");

  const handleuerChange = (e) => {
    setusername(e.target.value);
  };
  const handlesubmit = (e) => {
    e.preventDefault();
    let newuser = { id: new Date().getTime().toString(), username: username };

    addUser(newuser);
    setusername("");
  };
  return (
    <div>
      <h2>user registreation </h2>
      <form action="" onSubmit={handlesubmit}>
        <input
          type="text"
          name="username"
          value={username}
          onChange={handleuerChange}
        />
        <button type="submit">add user </button>
      </form>
    </div>
  );
};

export default NewUsers;





import React, { useState } from "react";
import { useUserContext } from "./CustomHook/userUserContext";

const User = ({ user }) => {
  const { users, addUser, deleteUser } = useUserContext();
  let { id, username } = user;

  let handleclick = (id) => {
    deleteUser(id);
  };
  return (
    <div>
      <article className="user">
        <p> {id}</p>
        <h2>{username}</h2>
        <button
          onClick={() => {
            handleclick(id);
          }}
        >
          delete{" "}
        </button>
      </article>
    </div>
  );
};

export default User;



import React, { useState } from "react";

import User from "./User";
import "../../../App.css";
import { useUserContext } from "./CustomHook/userUserContext";

const Users = () => {
  const { users, addUser, deleteUser } = useUserContext();

  return (
    <div>
      <section className="grid">
        {users.map((user) => (
          <User key={user.id} user={user} />
        ))}
      </section>
    </div>
  );
};

export default Users;

```

</details>

<br>

<br>

# useRef Hooks 
<details>
      <summary>
  UserForm
     </summary>

```javascript
import React, { useRef } from "react";

const UserForm = () => {
  let userNameRef = useRef();
  let passwordRef = useRef();

  let handleSubmit = (e) => {
    e.preventDefault();

    let us = userNameRef.current.value;
    let pass = passwordRef.current.value;
    console.log({ us, pass });
  };
  return (
    <div>
      <h1> UserForm </h1>

      <form action="" onSubmit={handleSubmit}>
        <div className="form-field">
          <label htmlFor="userName">UserName :</label>
          <input type="text" id="userName" ref={userNameRef} />
        </div>

        <div className="form-field">
          <label htmlFor="password">Password :</label>
          <input type="password" id="password" ref={passwordRef} />
        </div>
        <button type="submit">Registerd </button>
      </form>
    </div>
  );
};

export default UserForm;

```

</details>
<br>
<br>

# useEffect Hooks 
<details>
      <summary>
        UseEffectExample
     </summary>

```javascript
import React, { useState, useEffect } from "react";

const UseEffectExample = () => {
  const [count, setcount] = useState(0);

  const [isLoading, setisLoading] = useState(false);

  useEffect(() => {
    console.log("useEffect ");
  }, [count]);

  return (
    <div>
      {console.log("rendering ")}
      <h1>Count : {count} </h1>
      <button onClick={() => setcount((pre) => pre + 1)}>increment </button>
      <button onClick={() => setisLoading(!isLoading)}>increment </button>
    </div>
  );
};

export default UseEffectExample;

```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>

<br>

## DataFetch 
<details>
      <summary>
        DataFetch 
     </summary>

```javascript
import React, { useEffect, useState } from "react";

const DataFetch = () => {
  const [todos, settodos] = useState(null);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/todos")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        settodos(data);
      });
  }, []);

  let todoElement =
    todos &&
    todos.map((todo) => {
      return <p key={todo.id}>{todo.title}</p>;
    });

  return (
    <div>
      <h1> DataFetch</h1>
      {todoElement}
    </div>
  );
};

export default DataFetch;

```

</details>
<br>

## part2 
<details>
      <summary>
      DataFetch  ErrorHandling
     </summary>

```javascript
import React, { useEffect, useState } from "react";
const loadingMessage = <p>todo is loading </p>;

const DataFetch = () => {
  const [todos, settodos] = useState(null);

  const [loading, setloading] = useState(true);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/todos")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        settodos(data);
        setloading(false);
      });
  }, []);

  let todoElement =
    todos &&
    todos.map((todo) => {
      return <p key={todo.id}>{todo.title}</p>;
    });

  return (
    <div>
      <h1> DataFetch</h1>
      {loading && loadingMessage}
      {todoElement}
    </div>
  );
};

export default DataFetch;


import React, { useEffect, useState } from "react";
const loadingMessage = <p>todo is loading </p>;
const ErrorHandling = () => {
  const [todos, settodos] = useState(null);

  const [loading, setloading] = useState(true);
  const [error, seterror] = useState(null);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/todo")
      .then((response) => {
        if (!response.ok) {
          throw Error("Fetching is not successful ");
        } else {
          return response.json();
        }
      })
      .then((data) => {
        settodos(data);
        setloading(false);
        seterror(false);
      })
      .catch((error) => {
        seterror(error.message);
        setloading(false);
      });
  }, []);

  let todoElement =
    todos &&
    todos.map((todo) => {
      return <p key={todo.id}>{todo.title}</p>;
    });

  return (
    <div>
      <h1> DataFetch</h1>
      {error && <p> {error} </p>}
      {loading && loadingMessage}
      {todoElement}
    </div>
  );
};

export default ErrorHandling;

```

</details>

<br> 
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>

<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>

<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>

<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>

<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>
<details>
      <summary>
        hello
     </summary>

```javascript
import React from "react";

const Expensive = () => {
  console.log("expensive compenent rendered!");

  let total = 0;
  for (let i = 0; i < 1000000000; i++) {
    total += i;
  }

  return <div>Expensive</div>;
};

export default Expensive;
```

</details>




