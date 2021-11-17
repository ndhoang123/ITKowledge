# Javascript
## ES6:
1. **Let, const**:
    - It is used to definition for variable.
    - The difference between let, const and var is:
        + `Assignment`: Const cannot assign the value. Otherwise, const and let can be.
        + `Scope`: **var** can **use** in the *parent/children/outside block*. Otherwise, **const, and let** just **use** in *inside block*.
        + `Hoisting`: It defines the ability of shifting variable declaration to the top.
            + **Var** can **use it**. **Block and const** cannot.
    - We can change the value of object being assigned by the const value. Can change each of value in object, not change all object in one time. Do the same with the array.
2. **Arrow function**:
    - Definition: `const nameoffunction = (param) => {}`
    - After the arrow, we can directly return the value without the {} symbol. If we use the {} symbol, the compiler will understand we using the block and must have **return keyword** inside the block.
    - Arrow function **cannot** use **this keyword**.
3. **Backslash(\ )**:
    - It uses to print all words inside the symbol "".
    Ex: \'a\' => the web print 'a';
4. **Template string in es6**:
    - It is ` `${}` `symbol.
5. Number:

| Method      | Description |
| ----------- | ----------- |
| Number.parseFloat()      | Convert the value to float|
| Number.parseInt()   | Convert the value to int|

# Jquery:
- All function in jquery starting with $.
- Use `.css()` to change css.
- Use `.prop()` to adjust the properties of elements.
- Use `.html()` to change the text between the start and end tags of an element.
- Use `.text()` to alter text without adding tags.
- Use `.remove()` to remove the element.
- Ues `.appendTo()` to select HTML elements and append them to another element. Use `.clone()` to coppy element.

# React:
1. JSX
    - JSX is a convenient tool to write readable HTML within JavaScript.
    - The JSX must **declare with parent element**(here, `the div element`). If it doesnt contain the parent, it will cause the bug.
    - All HTML attributes and event references in JSX become camelCase.
    - In JSX, it is no longer to use **class** word. Instead, they use **className**.
2. ReactDOM:
    - ReactDOM offers a simple method to render React elements to the DOM.
    - Syntax: `ReactDOM.render(componentToRender, targetNode)`
        + With: 1st arg: The React component or element rendering.
        + 2rd arg: DOM node that you want to render the component to.
3. Create React component:
    1. Stateless Functional Component:
        - It uses to create a React component.
        - Stateless component as one that can receive data and render it, but does not manage or track changes to that data.
    2. ES6 class:
        - Must extends the React.Component class, that you can use the lifecycle and React hook.
        - Use super in constructor.
    - To render a component as a child in a React component, you include the component name written as a custom HTML tag in the JSX.
4. Render:
    - You can render JSX elements, stateless functional components, and ES6 class components within other components
    - Render a class component:
    `ReactDOM.render(<ComponentToRender />, targetNode).`
5. Assign value:
    - You can assign default value by adding `NameOfComponent.defaultProps = { location: 'San Francisco' }`
6. PropsType:
    - Use `PropsType` to verify that components receive props of the correct type.
7. Access props:
    - In ES6 class, use keyword `this.props`.
    - In FP, use `props`.
8. Lifecycle:
    - Several special methods that provide opportunities to perform actions at specific points in the lifecycle of a component. It is called lifecycle methods.