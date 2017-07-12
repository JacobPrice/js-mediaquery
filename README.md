# js-mediaquery
Small function that simplifies executing javascript with css3 media queries.

#### Executing Javascript at certain breakpoints shouldn't be hard. I've found that my preferred way is to assign a function to listen for a css3 media query. Here is a simple function that gives quick access to that. 
```javascript
    function jsMediaQuery(mediaQuery, func) {
      let mq = window.matchMedia(`(${mediaQuery})`)
      mq.addListener(func)
      if(mq.matches) {
        func(mq)
      }
    }
```

#### Now you must write your function in a way that corresponds to how it will be assigned, so an example is as follows: 
```javascript
    function demo(mq) {
      if (mq.matches) {
        document.write('JS executed<br>')
      } else {
        document.write('mq is not matched<br>')
      }
    }
```

#### On load should the media query match the function will be executed, just as you would expect a css media query to style according to width. 

#### This example is rudimentary, but the same idea could be used to do much more complex tasks, such as load certain files only on mobile etc. 
