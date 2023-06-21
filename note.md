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

calendards and pop-ups  scenarios
we also provide packaged component capabilities like map,video and audio.
we generally manipulate DOM(the tree generated from the description of HTML)
records     conducive   applies     shown as below      scenarios       describe
    incorporates    convert the pixel   pixel ratios    floating-point operations   obtaining
```
<button bindtap="clickMe"> click me </button>
Page({ 
    clickMe: function() {
        this.setData({msg: "hello "})
    }
})
```
- Webview ==> native
- JsCore ==> native
- native =https request/ web socket=> service

deliver     threads

when the mini program is launched,the onLaunch callback of the app instance defined in app.js is executed

### export 
```js
Object.defineProperty(exports, "clearCache", {
  enumerable: true,
  get: function get() {
    return _useRequest.clearCache;
  }
})
```
- "object" is the object on which to define or modify the property.
- "property" is the name of the property to be defined or modified.
- "descriptor" is an object that contains the attributes of the property, such as value, writable, enumerable, and configurable.

object-oriented     latitude and longitude
```
<map bindmarkertap="" longitude="" latitude="" > </map>
```
geographical location
```
wx.getLocation({
  type: 'wgs84',
  success: (res) => {
    var latitude = res.latitude // Latitude
    var longitude = res.longitude // Longitude
  }
})
wx.scanCode({
  success: (res) => {
    console.log(res)
  }
})
```
collaboration   labor   involved    collaboration       synchronization
```
var _data = {
    name:"weixin"
}
// register a page.
Page({
    data: _data,
    changeName: function(e) {
        //sent data change to view
        this.setData({
            name:"00"
        })
    }
})

<!-- This is our View -->
<view> Hello {{name}}! </view>
<button bindtap="changeName"> Click me! </button>
```
scene   obtained

1. Sunday
2. Monday
3. Tuesday
4. Wednesday
5. Thursday
6. Friday
7. Saturday


1. January
2. February
3. March
4. April
5. May
6. June
7. July
8. August
9. September
10. October
11. November
12. December

2517
```js
var maximumTastiness = function(price, k) {
    price.sort((a,b) => a-b);
    let left = 0, right = price[price.length - 1] - price[0];
    while (left < right) {
        const mid = Math.floor((left + right + 1) / 2);
        if (check(price, k, mid)) {
            left = mid:
        } else {
            right = mid - 1;
        }
    }
    return left;
}

const check = (price, k, tastiness) => {
    let prev = -Number.MAX_VALUE / 2;
    let cnt = 0;
    for (const p of price) {
        if (p - prev >= tastiness) {
            cnt++;
            prev = p;
        }
    }
    return cnt >= k;
};
```
respectively    obtain   modularization
```
//app.js
App({
  onLaunch (options) {
    // Do something initial when launch.
  },
  onShow (options) {
    // Do something when show.
  },
  onHide () {
    // Do something when hide.
  },
  onError (msg) {
    console.log(msg)
  },
  globalData: 'I am global data'
})

// xxx.js
const appInstance = getApp()
console.log(appInstance.globalData) // I am global data
```
existing pages via stacks       reacts as follows
- initialization    the new page is pushed onto the stack
- opening a new     the new page is pushed onto the stack
- page redirection  the current page is popped out of the stack, and the new page is pushed onto the stack.
- page return       pages are successively popped out of the stack until the destination return page is displayed
- the switching     all the pages are popped out of the stack, and only the new tabpage is retained
- reloading         all the pages are popped out of the stack, and only the new page is retained.

developers can obtain the current page stack by using the getCurrentPages() function.

```
<navigator 
    open-type="navigateTo"
    "redirectTo"
    "navigateBack"
    "switchTab"
    "reLaunch"
/>
```
tips:
- navigateTo and redirectTo can be used to open non-tabBar pages only.
- switchTab can be used to open tabBar pages only.
- reLaunch canbe use to open any pages.
- the tabBar on the buttom of a page is determined by the page. in other words, tabBar is displayed on the bottom of all pages defined as tabBar.
- parameters used to call page routing can be obtained via onLoad in the destination page.

ecology     cater   dimension unit
### generic data types

```
fn largest<T>(list: &[T]) -> &T {
```
trait   comparisons
### idea
https://3.jetbra.in/

capturing   declaration
831模拟
```js
const country = ["", "+*-", "+**-", "+***-"];

var maskPII = function(s) {
    const at = s.indexOf("@");
    if (at > 0) {
        s = s.toLowerCase();
        return (s[0] + "*****" + s.substring(at -1)).toLowerCase();
    }
    let sb = "";
    for (let i = 0; i < s.length; i++) {
        const c = s.charAt(i);
        if ('0' <= c && c <= '9') {
            sb += c;
        }
    }
    s = sb.toString();
    return counry[s.length - 10] + "***-***-" + s.subtring(s.length - 4);
}
```
###  powershell
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe


postcss

2460直接模拟
```js
var applyOperations = function(nums) {
    let n = nums.length;
    let j = 0;
    for (let i = 0; i < n; i++) {
        if (i + 1 < n && nums[i] == nums[i + 1] ) {
            nums[i] *= 2;
            nums[i+1] = 0;
        }
        if (nums[i] != 0) {
            [nums[i], nums[j]] = [nums[j], nums[i]];
            j++;
        }
    }
    return nums;
};
```
about unionID mechanism

unionID can be used to distinguish user uniqueness      asymptotic      encounter       further     1036    1069    non-1069    app-parameter       facilitate      open-type
coupons(including general cards)
standardized    idiosyncratic   CommonJS and AMD.ES     iife-style scripts
```
# compile to a <script> containing a self-executing function ('iife')
```
generics
#### a major part of software engineering is building components that not only have well-defined and consistent APIs,but are also reusable  
```
    function identity<Type>(arg: Type): Type {
        return arg;
    }
```
e.g. 例如   i.e.即，也  
- pass all of the arguments, including the type argument, to the function
```
let ouput = identity<string>("mystring");
    let output: string
```
- use type argument inference--that is, we want the compiler to set the value of Type for us automatically bassed on the type of the argument we pass in:
```
let ouput = identity("mystring");
    let output : string
```
```
function loggingIdentity<Type>(arg: Type[]): Type[] {
  console.log(arg.length);
  return arg;
}

function loggingIdentity<Type>(arg: Array<Type>): Array<Type> {
  console.log(arg.length); // Array has a .length, so no more error
  return arg;
}
```
vulnerabilities     verification    etc. 等等       parallel    briefly     serially
```
interface GenericIdentityFn<Tyoe> {
    (arg: Type): Type;
}

function identity<Type>(arg: Type): Type {
    return arg;
}

let myIdentity: GenericIdentityFn<number> = identity;
```
corrsponding    aspects
```
class GenericNumber<NumType> {
    zeroValue: NumType;
    add: (x:NumType, y: NumType) => NumType;
}
let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function (x, y) {
    return x + y;
}
console.log(stringNumberic.add(stringNumeric.zeroValue, "test"));
```
accidentally grabbing   deemed optional   succinct

### creating types from types
- generics -types which take parameters
- keyof type operator -using the keyof operator to create new types
- typeof type operator -using the typeof operator to create new types
- indexed access types -using type['a'] syntax to access a subset of a type
- conditional types -types which act like if statements in the type system
- mapped types -creating types by mapping each property in an existing type
- template literal types -mapped types which change properties via template literal strings

the keyof operator takes an object type and produces a string or numeric literal union of  its keys
```
type Point = {x: number; y: number};
type P = keyof Point;
```
if the type has a string or number index signature, keyof will return those types instead
```
type Arrayish = {[n: number]: unknown};
type A = keyof Arrayish;
// type A = number

type Mapish = {[k: string]: boolean};
type M = keyof Mapish;
// type M = string | number
```
coerced
```
let s = "ssss";
let n: typeof s;
// let n: string

type Predicate = (x: unknown) => boolean;
type K = ReturnType<Predicate>
// type K = boolean

function f() {
    return {x: 10, y: 3};
}
type P = ReturnType<typeof f>;
// type P = {
    x: number;
    y: number;
}
```
subtly  boilerplate
https://www.typescriptlang.org/docs/handbook/2/objects.html
```
class Point {
    x: number;
    y: number;
}
const pt = new Point();
pt.x = 0;
pt.y = 0;
```
strictPropertyInitialization
```
class GoodGreeter {
    name: sting;

    constructor() {
        this.name = "hhhhh";
    }
}
```
definite assignment assertion operator !:
```
class OKGreeter {
    // Not initialized, but no error
    name!: string;
}
```
readonly
Fields may be prefixed with the readonly modifier. this prevents assignments to the field outside of the constructor.
``` 
class Greeter {
    readonly name: string = "wwww";

    constructor(otherName?: string) {
        if (
```
super()
accessors
- if get exists but no set, the property is automatically readonly
- if the type of the setter parameter is not specified, it is inferred from the return type of the getter
- Getters and setters must have the same Member Visibility.

index Signatures
```
 [s: string]: boolean | ((s: string) => boolean);
```
class heritage      implement multiple interfaces       cautions
- implements clauses
- extends clauses

Member Visibility
- public
- protected
- private

fields
static members
 `#count` is a private instance field that was introduced in TypeScript 3.8
instantiated
```ts
function myPromise(): Promise<string> {
    return new Promise((resolve, reject) => {
```
generic classes
```
class Box<Type> {
  contents: Type;
  constructor(value: Type) {
    this.contents = value;
  }
}
 
const b = new Box("hello!");
// const b: Box<string>
```
static members cannot reference class type parameters.  
types are always fully erased
The static members of a generic class can never refer to the class's type parameters.

peculiar
this is indeed unusual
### arrow functions
if you have a function that will often be called in a way that loses its this context, it can make sense to use an arrow function property instead of a method definition:
```
class MyClass {
    name = "mmmm";
    getName = () => {
        return this.name;
    };
}
const c = new MyClass();
const g = c.getName;
...
```
terminology     throughout      hierarchical
url segment: part of the url path delimited by slashes
url path: part of the url that comes after the domain(composed of segments)

app router built on react server components 
alongside   incremental adoption    priority    nested routes       colocation      publically addressable      optimization

unlike the pages dierectory which uses client-side routing, the app router uses server-centric routing to align with server components and data fetching on the server

resembling      payload in an in-memory client-side cache       invalidation    certain cases       previously
partial rendering       sibling routes      preserved       cause       transferred     patterns    intercepting    represents      accessible

a layout is ui that is shared between multiple [ages.On navigation,layouts preserve state, remian insteractive, and do not re-render

no time like the present

#### common syntax
private access is just to this class, protected allows to subclass. Only used for type chcking, publick is the default. 


exclamation mark (!)
convetions      automatically dedupe the requests without affecting performance
built-in SEO support        metadata        interpolation       determine   implicitly  converted       parentheses
#### swift
write the value in parentheses, and write a backslash(\) before the parentheses

- experiment
use \() to include a floating-point calculation in a string and to include someone's name in a greeting.


use three double quotation marks (""") for strings that take up multiple lines


create arrays and dictionaries using brakets([]), and access their elements by writing the index or key in brackets
```
var fruits = ["stawberries", "limes", "tangerines"]
fruits[1] = "grapes"

var occupations = [
    "malcolm": "captain",
    "kayless": "mechanic"
]
occupations["jayne"] = "public relations"

let emptyArray:[String] = []
let emptyDictionary:[String: Float] = [:]
```
#### use for-in, while, and repeat-while to make loops

You can use if and let together to work with values that might be missing. These values are represented as optionals. An optional value either contains a value or contains nil to indicate that a value is missing. Write a question mark (?) after the type of a value to mark the value as optional.
```
var optionalString: String? = "Hello"
print(optionalString == nil)
// Prints "false"

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}   
```
Another way to handle optional values is to provide a default value using the ?? operator. If the optional value is missing, the default value is used instead.
```
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"

```
unwrap      pattern
```
var n = 2
while n < 100 {
    n *= 2
}
print(n)
// Prints "128"


var m = 2
repeat {
    m *= 2
} while m < 100
print(m)
// Prints "128"
```
Use ..< to make a range that omits its upper value, and use ... to make a range that includes both values
```
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// Prints "6"
```
partitioning    affecting   enabling
#### docker hub
- 1
docker run -it -p 100:3000 yakgpt/yakgpt:latest


- 2
```
docker pull yidadaa/chatgpt-next-web

docker run -d -p 3000:3000 \
   -e OPENAI_API_KEY="sk-xxxx" \
   -e CODE="your-password" \
   yidadaa/chatgpt-next-web
```


https://github.com/gitbito/CLI

elapsedTime

don't write sparate overloads that differ only on callback arity


experiment      underscore _    arrow ->  integer arrow  string arrow

functions are actually a special case of closures: blocks of code that can be called later. the code in a closure has access to things like variables and functions that were available in the scope where the closure was created, even if the closure is in a different scope when it's executed -- you saw an example of this already with nested functions. you can write a closure without a name by surrounding code with braces({}). use in to separate the arguments and return type from the body
```
numbers.map({number: Int) -> Int in 
    let result = 3 * number
    return result
}）
```

Experiment

Rewrite the closure to return zero for all odd numbers.

You have several options for writing closures more concisely. When a closure’s type is already known, such as the callback for a delegate, you can omit the type of its parameters, its return type, or both. Single statement closures implicitly return the value of their only statement.
```
let mappedNumbers = numbers.map({ number in 3 * number })
pri费用报销_form_23_5nt(mappedNumbers)
// Prints "[60, 57, 21, 36]"
```

You can refer to parameters by number instead of by name — this approach is especially useful in very short closures. A closure passed as the last argument to a function can appear immediately after the parentheses. When a closure is the only argument to a function, you can omit the parentheses entirely.
```
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// Prints "[20, 19, 12, 7]"
```
distinguish     semicolons      assign to   initial     separated       desired     parentheses     backslash(\) 
take up multiple lines      brackets([])    braces{}   three double quotation marks (""")    question mark (?)

concisely   delegate
use dot syntax to access the properties  and methods of the instance

hierarchy

get angry   get upset   get annoyed     get irritated       get worried  he's getting on = he's getting old
get stuck   get ready   get interesting
i get the impression = it seems to me       to get vaccinated = to receive a vaccine
extremely interesting       incredibly interesting      tremendously useful     particularly useful     dead good


#### JSON
JSON.stringify(p, null, 4)


1262
```
var maxSumDivThree = function(nums) {
    const v =[[], [], []];
    for (const num of nums) {
        v[num % 3].push(num);
    }
    v[1].sort((a,b) => b -a);
    v[2].sort((a,b) => b -a);

    let ans = 0;
    const lb = v[1].length;
    const lc = v[2].length;
    for (let cntb = lb - 2; cntb <= lb; ++cntb) {
        if (cntb >= 0) {
            for (let cntc = lc - 2; cntc <= lc; ++cntc) {
                if (cntc >=0 && (cntb -cntc) % 3 === 0) {
                    ans = Math.max(ans, getSum(v[1], 0, cntb)
                }
            }
        }
    }
    return ans + getSum(v[0], 0, v[0].length);
};

const getSum = (list, start, end) => {
    let sum = 0;
    for (let i = start; i < end; ++i) {
        sum += list[i];
    }
    return sum;
}

### redis
```
json.set nms:connection:192.168.1.211:830:uup1 $ ""
```
```
json.get nms:connection:192.168.1.211:830:uup1
```
