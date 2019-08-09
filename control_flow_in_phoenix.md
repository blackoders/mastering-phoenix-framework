## Why do we still need `view` file though it usually end up with empty lines of code?
The views in Phoenix helps us to render templates. For every request we need to send a response. 

If we end up reading the file from `templates` folder and sending response, then it costs more in time. 
For every request we need to read a file. It is costly in time.

**Phoenix** is smart enough to handle this. During the compile time, it looks for any `eex` files inside the 
`templates` folder and generates respective `render` function in the respective `view` file. 

So, everytime you make a request, we are actually calling a `render`function written by **Phoenix** for us 
if not present in the `view` during compile time.

So, the **function calls** are faster than **file read operations**.

Ofcourse, we can write `render` function in view but if your response content grows, the function appearance would be weird. 
So, we need to keep them seperate and tidy and leave **Phoenix** to mess with it. 
