#### Cargo

#### TOML(Tom's Obvious, Minimal Language) format
which is Cargo's configuration format

condition

#### provide if with a Boolean as its condition

divisible   clutter  incompatible
```rs
fn main() {
    let condition = true;

    let number = if condition { 5 } else { "six" };

    println!("The value of number is: {number}");
}
```
```
$ cargo run
   Compiling branches v0.1.0 (file:///projects/branches)
error[E0308]: `if` and `else` have incompatible types
 --> src/main.rs:4:44
  |
4 |     let number = if condition { 5 } else { "six" };
  |                                 -          ^^^^^ expected integer, found `&str`
  |                                 |
  |                                 expected because of this

For more information about this error, try `rustc --explain E0308`.
error: could not compile `branches` due to previous error

```
The expression in the if block evaluates to an integer, and the expression in the else block

#### repeating code with loop
```
fn main() {
    loop {
        println!("again!")
    }
}
```
keyboard shortcut ctrl-c to interrupt a program that is stuck in a continual loop.

#### returning values from loops
```
fn main() {
    let mut counter = 0;
    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2;
        }
    };
    println!("The result is {result}");
}
```
#### conditional loops with while 
```
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }
    
    println!("liftoff!!!");
}
```

looping through a collection with for
```
fn main() {
    let a = [10, 20, 30, 40, 50];
    let mut index = 0;

    while index < 5 {
        println!("the value is: {} ", a[index]);
        index += 1;
    }
}
```
```
fn main() {
    let a = [10, 20, 30, 40, 50];
    for element in a {
        println!("the value is: {element}");
    }
}
```
eliminated
```
fn main() {
    for number in (1..4).rev() {
        println!("{number}!");
    }
    println!("LIFTOFF!!!");
}
```
allocating  allocate

### The expression 0 <= x <= 2 is syntactically valid in JavaScript and it will execute without syntax errors.
```js
if (0 <= x && x <= 2) {
  // code to execute if x is between 0 and 2, inclusive
}
```
### Ownership
memory is managed through a system of ownership with a set of rules that the compiler checks

efficient   relation    preparation     structured
### The stack
 The stack stores values in the order it gets them and removes the values in the opposite order. This is referred to as last in, first out.

 plate  pile

 All data stored on the stack must have a known, fixed size. Data with an unknown size at compile time or a size that might change must be stored on the heap instead.

### The heap
The memory allocator finds an empty spot in the heap that is big enough, marks it as being in use, and returns a pointer, which is the address of that location.

comparatively   accessing   contemporary processors

### quick key
win + e open dir
alt + d to url  ||  ctrl + L / F4
### about unique
session\_cookie=str(uuid4())
```py
app.add_middleware(SessionMiddleware, secret_key="web_gui", same_site="strict", session_cookie=str(uuid4()))
```
boilerplate     concise     illustrate  trivially   literal     double colon ::     mutated
```rs 
let mut s = String::from("hello");
s.push_str(", world!");
println!("{}", s);
```
unfortunately   implementation  garbage collector(GC)   explicitly  exactly 

the GC keeps track of and cleans up memory

correctly   deallocating
### Resource Acquisition Is Initialization (RAII)
profound     one-size-fits-all      expertise   integrated      bulk rename utility     unexpected      interact    assume  guaranteed      ampersand symbol &      dereference     instead of      borrowing  
### mutable references
```
fn main() {
    let mut s = String::from("hello");

    change(&mut s);
}

fn change(some_string: &mut String) {
    some_string.push_str(", world");
}
```
signature   mechanism
### Dangling References
contrast    disregard
## The Slice Type
straightforward     variety     graphical user interface (GUI)
#### use pwd get path
demonstrate     rect    rectangle       signature       chose
struct  impl    enumerations    variants    concise idiom   available   subset  pattern matching
### if let
crate

### componentWillMount()
after onload,the page component is triggered before rendering to Taro's virtual DOM.
### componentDidMount()
triggered after the page component is renderd to taro's virtual Dom

obtained    manipulate
```js
export default class Test extends React.Component {
    el = createRef()

    componentDidMount () {
        console.log(this.el.current)
    }

    render () {
        return (
            <View id="only" ref={this.el} />
        )
    }
}
```
to get the real mini program rendering layer node, you need to call the API used to get the DOM in the mini program during the onReady lifecycle.
```
onReady() {
    Taro.createSelectorQuery().select("#only")
        .boundingClientRect()
        .exec(res => console.log(res))
    }
```
### entry component
every taro application needs an entry component to register the appliction. the default entry file is app.js in the directory.

in the entry component we can set the global state or access the lifecycle of the mini program entry instance.

```jsx
const store = configStore()
class App extends Component{
    componentDidMount(){}
    onLaunch(){}
    componentDidShow(){}
    componentDidHide(){}
    render(){
        return (
            <Provider store={store}>
                {this.props.children}
            </Provider>
        )
    }
}
```

```jsx
const store = configStore()
function App (props) {
    // all react hooks can be used
    useEffect(() => {})
    // onShow
    useDidShow(() => {})
    // onHide
    useDidHide(() => {})
    return (
        <Provider store={store}>
            {props.children}
        </Provider>
    )
}
```
corressponding      rogram

### page components
```
// onPullDownRefresh, except for componentDidShow/componentDidHide
// all page lifecycle function names correspond to mini program
onPullDownRefresh(){}
// Taro implements custom React Hooks for all mini program page lifecycles to support
usePullDownRefresh(() => {})
```
onReachBottom(): listen to the user pull-up bottoming event.

synchronization

onPageScroll(Object):listening to user swipe page events

onAddToFavorites(Object):listen to the user's click on the "Favorites"button int the upper-right corner of the menu and customize the contents of the favorites.

onShareAppMessage(Object):listen to the user's behavior when they click on the forward button (Button component openType='share') or the "Forward" button int the top-right menu,and customize the forwarding content.

Attention:
- when onShareAppMessage is not triggered,please set enableShareAppMessage:true in the page config
- only if this event handler is defined,the "Forward"button will be displayed in the upper right menu

onResize(Object):triggered when the mini program screen is rotated

corresponding   re-rendered     foreground
```
setState(prevState => {
// 也可以使用 Object.assign
return {...prevState, ...updatedValues};
});
```
### lazy initial state
```
const [state, setState] = useState(() => {
  const initialState = someExpensiveComputation(props);
  return initialState;
});
```
```
useEffect(didUpdate);
```
```
useEffect(() => {
  const subscription = props.source.subscribe();
  return () => {
    // clear effect
    subscription.unsubscribe();
  };
});
```
to avoid memory leaks, the cleanup function will be executed before the component is unmounted
### the execution time of effect
it's different from componentDidMount and componentDidUpdate, taro will execute the effect callback function at the next macrotask after the completion of setData,and the function passed to useEffect will be called delayed. this makes it suitable for a lot of common side effects scenarios, such as setting up subscriptions and event handing, so ti should't to execute render and update in functions.

scenarios   subscription    overkill    scenarios   recreated       repeatedly      approach    alternative     seamless    elivering excellent     optimizing      insufficiency   threads     suffixed

- floating-point
- arrays enclosed in square brackets
- objects enclosed in curly brackets
- null

html describes the structure of the page,css determines the appearance of the page,js defines the interaction between the page and the user.

wxml is the equivalent of html
