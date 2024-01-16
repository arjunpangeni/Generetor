This is a password generator project .We can generate password with different options like it's length and includes numbers,characters or not .At the end , we can copy the generated password in the clipboard .

During this project,I enhance the knowledge about optimization of code using useCallback .

## Here is things that i have learned about useCallback hook .

usecallback hook is a react hook that lets you cache a function defination between re-renders until it's dependencies changes.

-usecallback should be use at the top level of our component ,we can't call it inside loops or condition,if we need that extract a new component and pass state as a props .

-React will returns only our function(not call)bacak to us during te initial render .
-on next render React will retrun same function unless the dependencies have not changed.than store it for next render.

uses:

## skipping re-rendering of components

when we optimize rendering performance, sometimes we need to cache the function that we pass to child component,

example -: we have a parent component 'A' having child 'B' .we pass a function as props to the child 'B' .At every renders of parent component it will re-renders all the children .we can use Memo hook to skip the re-render of child component until the props hasn't change.But in this example we pass a function as props .In every re-render function will change(always creates a different function ) results the change in props and children will also re-render .so there is no meaning of wraping child component with Memo.This is where useCallback comes in handy by chaching that function .

## Updating state from a memoized callback

At every state change , the component will be re-rendered , we can change state with in the memoized callback with out any dependecies .can remove that dependency by passing an updater function instead

## Preventing an Effect from firing too often

In this project , onchanging variables ( length , charaters and number are allowed or not) the usecallback hook prevent to envoke the useeffect hook for sideeffect.

# optimizing the custom hooks
