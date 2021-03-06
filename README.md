# cbp-vue-toastr

> This is master branch cbp-vue-toastr which works only with **Vue 2.x**. cbp-vue-toastr@**latest**

### With npm & babel

*Add the Toast into the package.json. #for vue **2.x***

    npm install cbp-vue-toastr --save

*Add the toast in application and register component.*

    // import Toastr
    import Toastr from 'cbp-vue-toastr';
    // import toastr less file: need webpack less-loader
    require('cbp-vue-toastr/src/vue-toastr.less');
    // Register vue component
    Vue.component('cbp-vue-toastr',Toastr);

*Add component html: for vue **2.x***

    <cbp-vue-toastr ref="toastr"></cbp-vue-toastr>

*Now you can manage toastr* 

    this.$root.$refs.toastr.e("ERRROR MESSAGE");
    this.$root.$refs.toastr.s("SUCCESS MESSAGE");

### without npm

https://github.com/voogryk/cbp-vue-toastr

### Development Setup

``` bash
# install deps
npm install

# serve examples at http://localhost:8080/
npm run dev
# build  dist/vue-toastr.js dist/vue-toastr.css
npm run build
# build for production min version. dist/vue-toastr.min.js dist/vue-toastr.min.css
npm run build_min
# build for production js+css combine. dist/vue-toastr.combine.min.js
npm run build_combine
# clear All builds.. rm -rf dist/*
npm run clear
#Build all. npm run build && npm run build_min && npm run build_combine
npm run buildAll
```

## Doc # Overwrite Settings

#### Change Default Toast Timeout
```
this.$refs.toastr.defaultTimeout = 3000; // default timeout : 5000
```
#### Change Default Toast ProgressBar
```
this.$refs.toastr.defaultProgressBar = false; // default active : true
```
#### Change Default Toast Type
```
this.$refs.toastr.defaultType = "error"; // default type : success
```
#### Change Default Position
```
this.$refs.toastr.defaultPosition = "toast-bottom-left" // default position: toast-top-right
```
#### Change Default Close On Mouse Hover
```
this.$refs.toastr.defaultCloseOnHover = false // default close on hover: true
```

## Doc # method
#### New Error Type Toast Message
```
this.$refs.toastr.e("this.$refs.toastr.e message", "Error");
```
#### New Success Type Toast Message
```
this.$refs.toastr.s("this.$refs.toastr.s message");
```
#### New Warning Type Toast Message
```
this.$refs.toastr.w("this.$refs.toastr.w message", "Warning");
```
#### New Information Type Toast Message
```
this.$refs.toastr.i("this.$refs.toastr.i message", "Information");
```
#### Remove Toast Messages by type.
```
this.$refs.toastr.removeByType("error"); // error, warning, success, info
```
#### New Toast Message with default options.
```
this.$refs.toastr.Add("Working on the default options");
```
#### New Toast Message with options.
```
this.$root.$refs.toastr.Add({
    title: "Easy Toast", // Toast Title
    msg: "Hi", // Message
    clickClose: false, // Click Close Disable
    timeout: 0, // Remember defaultTimeout is 5 sec..
    position: "toast-top-full-width", // Toast Position.
    type: "error" // Toast type
});
```
## Doc # Options
```
{
        title: "Toast Title",
        msg: "Toast Msg", 
        position: Toast position string can be  'toast-top-right', 'toast-bottom-right', 'toast-bottom-left', 'toast-top-left', 'toast-top-full-width', 'toast-bottom-full-width', 'toast-top-center', 'toast-bottom-center' ; default toast-top-right
        type: Toast type can be : info,warning,error,success ; default success
        timeout: Toast Timeout for auto close can be integer ; default 5000
        progressbar: Progress Bar option need timeout. can be boolean; default true
        closeOnHover: On mouse over stop timeout can be boolean; default true
        clickClose: On click toast close can be boolean; default false
        onCreated: On created toast event can be function
        onClicked: On clicked toast event can be function
        onClosed: On closed toast event can be function
        onMouseOver: On mouse over toast event can be function
        onMouseOut: On mouse over toast event can be function
}
```
