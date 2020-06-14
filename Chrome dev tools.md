# edit Page dfirectelly in the browser :

toggle mode on off : 
```javascript
document.designMode = "on"
document.designMode = "off"
```

# monitor events

if you select an element in the dev tool it will be $0 
then you can feed it by : 
```javascript
  monitorEvents($0)
```
to turn it off 
```javascript
unmonitorEvents($0)
```

# Eager evaluation 

you can tooggle this option in the console tab inside the gear icon on the right 
by checking this option "Eager evaluation" you can see the command result in the consol before it get executed


