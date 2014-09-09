gulp-xmlpoke
============

Gulp port of grunt-xmlpoke


## Simple replacement

````
gulp.src('/path/to/file.xml')
    .pipe(xmlpoke({
      replacements : [{
          xpath : "//foo"        
        , value: "bar"
       }]
     }))
    .pipe(gulp.dest('/path/to/dest/file.xml'));
````

### Replacing with a function

````
gulp.src('/path/to/file.xml')
    .pipe(xmlpoke({
      replacements : [{
          xpath : "//foo"        
        , value : function(node) { 
          var nodeValue = node.firstChild.data;          
          return nodeValue + "Bar";
       }]
     }))
    .pipe(gulp.dest('/path/to/dest/file.xml'));
````

## Using Namespaces

````
gulp.src('/path/to/file.xml')
    .pipe(xmlpoke({
      replacements : [{
          xpath : "//foo:bar"
        , namespaces : {"foo" : "http://schemas.example.com/foo.xsd"}
        , value: "bar"
       }]
     }))
    .pipe(gulp.dest('/path/to/dest/file.xml'));
````