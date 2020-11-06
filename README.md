React Programming
JSX, the parser with new HTML property System
1. className instead of class
2. htmlFor instead of for attribute
3. Events
    - onChange, onClick, etc
4. property systems same as HTML
    - value
====================================================================
React Important Packages
1. react
    - Provides the React Object Model
        - Component, the base class for React Components
        - Hooks, the functions to define React Object Programming
            - useState(), userEffect(), useContext(), useReducer(), etc.
2. react-dom
    - Used to define the rednering of the React App, using Virtual DOM
        - ReactDom
            - the 'render()' method to load and ender the component.

3. installing CLI
    npm install -g create-react-app
4. Creating React aplication
    create-react-app <NAME-OF-THE-APPLICATION>   
5. CReate a package.json with ready default settings using
    - npm init -y
6. dependencies section of package.json contains all dependencies for Runtime (during execution in browser)  
    - npm install -save <PACKAGE-NAME>      
7. devDependencies section
    - contains dependencies while developing the application
    - npm install --save-dev <PACKAGE-NAME>
8. The scripts section of package.json  
    - contains / defines commans to 
        - build
        - test
        - debug
        - run
      applications  
====================================================================React Programming Concepts
- ES 6, Modern JavaScript or High-Level JavaScript
    - Class
    - Template String, new syntax for string concatination
    - Arraow Operators, =>, uses as a replacement for 'Call-Back' fucntions
    - Object Methods
    - New Array Methods
        - sort()/reverse()/find()/filter(), etc
    - New String methods    
    - New Collections
        - Set<T> and Map<T>   
    - Modules
        - This is a mechanism of code-splitting
            - Write code in separate .js files where the js file will export type (class,interface, function, constant) from file as module
                - the 'export' keyword
            - other .js file will import the type as module      
                - the 'import' keyword
- Transpile the ES 6 into Browser Compatible JavaScript
    - Transpilation
        - Transformed Compilation
        - Compiled Transforms
    - ES 6 --> Transpilers(?) --> ES 3 (Browser Specific) JavaScript Code
    - Transpilers
        - Babel
        - Tracure            
====================================================================React Component
1. Class Component, traditional to React Applciation
    - Pure ES 6 born concept
    - Derived from 'Component' base class of 'react' package
2. Functional Components, specially used from React 16.0
    - Provides the functional programming experience like standard JavaScript.
====================================================================React Class Component
- Component<P,S> Base class
    - P, the 'props' object
        - An immutable object, thst will be used to pass data from parent component to child component.
        - e.g.
            this.props.<property-name>
                - property-name
                    - The property of which value passed from parent to child OR across components
    - S, the 'state' object    
        - The mutable object, that represents the local data of the component.
        - Once the compnent is unloaded (unmounted) the state will be void
        - This is the JSON object, declared in the constructor
        - This can be bound to HTML elements inside the component   
        - Once state properties are bound with HTML elements, then can be updated using 'this.setState()' method 
        - *** Since React.js uses One-Directional-Data-Flow, to update state, the HTML element must subscribe to event 
Exercise 1: Create a Calculator like windows calculator  (Today) 
Exercise 2: Create a reusable Table which will be used as DataGrid. The selected row values from the table for the products will be shown in ProductFormComponent. This Table will habe props properties as  (Today)
    - canDelete (Today)
        - will generate the Delete button for each row, to delete record from parent  
    - canSort
        - will render the data in table in stored order based on the SortKey value
    - SoryKey   
        - The key on which the table will be sorted   
===================================================================================
1. How to perform External AJAX Calls?
- ES 6, the Promise object, reposnsible to manage all async operations
    - Wrapper written over all Async operations e.g. AJAX
    - Provides a subscription model to the caller so that called will be informed about the response.
- Using the 'fetch' object
    - uses 'Promise' object to provide subscription
    - get /post /put /delete
- USe the axios object    
    - the 'axios' package
    - npm install --save axios
        - exports the 'axios' object
        - HTTP method for get/post/put/delete
            - can receive JSON / XML / TEXT / BLOB / ArrayBuffer

2. How to implement the form-validation?
- HTML 5 DataValidation
    - required
    - min / max
    - minLenth / maxLength
    - pattern
- Implement the validators explicitely for the application

Day 2: Exercise
1. Complete Form COmponent that is using HttpService to perform CRUD operations on REST API

2. (Mandatory) --> 60 mins max
Validate the Product Form based on following rules
    - ProductId must be unique, the field level validation
    - Product Name must start from Upper Case Character, Field Level Validation
    - The Category NAme and Manufacturer Name must be selected, Filed level
    - Validations for Price
        - Electronics, should not be less than 2000
        - Electrical, should not be less than 50
        - Food, should not be less than 5
    - All entries are mandatory, modify the Product Form Component that will show
        red star (*) indicating that the field value is mandatory  or  Red border
    - Create a Validation Summary Component, that will show all validation messages at the bottom on the page, the validation message should be removed form summary when user enters valid data  




https://apiapptrainingnewapp.azurewebsites.net/api/Products
========================================================================================================

React.js Advanced Topics , Phase II

1. Using Higher-Order-Component
2. Error Boundreis
    - The ErrorBoundary will not executed properly if the React project is ceated using 'create-react-app' CLI, the reason is the 'react-scripts' will override the Error Boundary and will render 'iframe' that is showing an error message.
    - deactivate the iframe rendering by setting 
        iframe{display:none} in app.css or the css created by you. 
3. React Hooks with Functional Components
    - An approach to create component using JavaScript functions, instead of class.
        - How to define State?
            - React Hooks, 'useState()' to define state properties
            - mutable
        - How to define Props?
            - 'props' as it is, as a parameter to function component
            - do not use 'this.props', just use 'props' 
            - immutable
        - How to share data across components?
            - React Hooks, useContext()
            - The useContext() is the React.Context object, that is used
            to define a scope aka context of values to be send across components.
            - React.Context, defines context using 'createContext()' method
                - e.g. const myContext = createContext(INITIAL-VALUE)
                - the 'Provider' object, used to provide conetxt object to a specifc component
                    - e.g.
                        <myContext.Provider value={DATA-TO-BE-PASSED-FROM-PARENT}>
                          <ChildComponent/>
                        </myContext.Provider>
        - How to manage Lifecycle?
            - componentDidMount() and componentWillUnmount() is replaced by a single React Hooks, 'useEffect()'
                - Always acessed as 'functional component' level as like other Hooks.
                - useEffect is executed for each change in state.
                - useEffect accepts a 'depednency array' this will be a condition for useEffect to perform operation 'only once' irrespective of the state changes.
        - How to make Ajax calls? 
            - use useEffect() if the call is made during the functional component mounting.
        - How to implement SPA?
            - Using react-router-dom
        - How to implement validations?
            - same as forms validation with explicit validation methods like class component
        - If data is shared across all children in DOM then use 'props' else for shaing data to a spceific child component then use 'context' using useContext() hooks.    
    - What is still not supored in functional components and hence in hooks?
        - No Error Boundry
        - Instead use try..catch block
4. Single Page Application (SPA) Development
    - Route Table
        - Record of all Navigation URLs on the client
        - Uses a URL based query to execute the URL Expression and start navigation
    - Router
        - Uses teh Route Table to complete the navigation 'on-client-side'
    - External Libraries for Routing
        - react-router-dom
            - Route, the define the route table
            - Switch, contains the route table and perform query execution based on 'links' 
            - Link, the route Expression requested by URL
            - Redirect, to execute the lnk based redirection
            - BrowserRouter, the component that will load and initiate Routing for React SPA
                - Provides the rendering and lifecycle managemnet for all components. 

React.js Phase III
1. React with State Management using Redux
    - Action Creators and Action Methods
        - The method that accepts the payload (input parameter) from component and return following
            - type: Output action (mandatory)
            - payload: the output parameter (optional) 
    - Reducer functions
        - pure function that accepts state as input and returns state as output 
    - Store Creation
        - Store is created using 'createStore()' method taht accepts 'reducer' object
    - Class Components
        - Share data across the components using
            - using mapStateToProps() function, the state (data) from store  will be provided to class coponents using props.
            - using mapDispatchToProps() function, the event raised on component will be dispateched to action methods so that the reducer function will update the store and updated data will be made availabe to components using props.
    - functional components using Hooks
        - useSelector(), used instead of mapStateToProps()      
            - used to read state from store and provide it to the functional component.
        - useDispatch(), used instead of   mapDispatchToProps()
            - once event is raised on UI, the action will be dispatched  
    - Packages
        - npm install --save redux react-redux
            - redux , the REDUX object model
                - The 'createStore()' method to create store
                - combineReducres(), method to manage all reducers in a single instance
            - react-redux
                - The 'Providrs', the component that will be sued to manage lifecycle of React-Redux application by managing the 'store' subscription for all components
                - The 'useSelector()' and 'useDispatch()' hooks to read data from store and dispatching actions respectively.
                - The connect() method to map component wilth store (used only in case of class components, replaced by useSelector and useDispatch for functional components)                 
2. Server-Side Rendering, next.js
3. Routing Features
4. React Deployment
    - Docker Deployment (Recommended)
    - Web Application
5. Integration with the third party Libraries
    - bootstrap
    - D3    

=======================================================================================================
(Mandatory Exercise)CReate a Single Page Application for Performing CRUD operations on Products. (Use the ProductComponent created in earlier exercises. CReate Product and Edit Product has same UI). USe Class COmpponents.

(Mandatory Exercise): Complere the POST SAGA Operations using Class and Functional Components