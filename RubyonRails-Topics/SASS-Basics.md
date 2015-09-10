#Syntactically Awesome Stylesheets (SASS)

###SASS Basics

####Nesting

You have the ability to nest CSS componets together

For examples:

**CSS**

*class selector*

```css

.classname {
  text-align: center;
}

.classname h1 {
  margin-bottom: 10px;
}

```

**SASS**
```css
  
  .classname {
  text-align: center;
  h1 {
    margin-bottom: 10px;
  }
}
  
  
  
```



**CSS**

*id selector*

```css


#idname {
  float: left;
  margin-right: 10px;
  font-size: 1.7em;
  color: #f8f8f8;
  text-transform: uppercase;
  letter-spacing: -1px;
  padding-top: 9px;
  font-weight: bold;
}

#idname:hover {
  color: #f8f8f8;
  text-decoration: none;
}

```

**SASS**

When you have an id or class associated with an attribute such as *hover* we introduce the ampersand character **&** this will be added to the id selector in order for it to be nested.

```css
#idname {
  float: left;
  margin-right: 10px;
  font-size: 1.7em;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: -1px;
  padding-top: 9px;
  font-weight: bold;
  &:hover {
    color: #fff;
    text-decoration: none;
  }
}

```


####Variables

Variables can be used to limit the usage of repeated code.

**CSS**
```css

.classname{

 color: #FF0000;
}

#idname {

 color: #FF0000;

}

element1 {
 
  color: #FF0000;
}

element2 {
 
  color: #0101DF;
}

```

**SASS**

```SASS

$blue: #0101DF;
$red: #FF0000;

.classname{

 color: $blue;
}

#idname {

 color: $red;

}

element1 {
 
  color: $red;
}

element2 {
 
  color: $blue;
}


```
