# Cascading Style Sheet
CSS is how you apply styling to web elements. These styling options are typically key/value pairs that inform the browser how to stylize the element. Most CSS styles are responsive to the viewport in the browser: for instance, if you center some text, no matter how wide or narrow you make the viewport the browser will do its best to keep the text content centered.

One of the helpful features of CSS is the "cascading" feature: styling the is applied to parent elements is applied to descendant elements

## Inline Styling
You can apply CSS to an element by directly setting the styling properties of the element within the "style" attribute. While useful for one-off styling needs or quick edits it is typically not recommended for general styling

## Internal Styling
To better organize your styling you can create a style element in your header and use CSS selectors to target one or more elements in the body of your page with styling. 

Be careful when you have a combination of internal and inline styling: any inline styling will override the internal styling you specify

## External Styling
You can separate your styling from your html by storing it inside of a .css file and linking that file in your web page. Keep in mind that external styling has the lowest level of priority for styling: any internal or inline styling will override the properties you set in your external style sheet