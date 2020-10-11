## Render any JSON data in tree view

**Creating Collapsible Tree Structures from JSON into HTML in JavaScript**
<br>

So we will be using the `Render Json` library.

```
<!--  Include a script tag in your HTML Page-->
<script 
src="https://cdn.rawgit.com/caldwell/renderjson/master/renderjson.js"></script>

<!-- Element where the list will be created -->
<div id="container"></div>

<script>
    // The JSON Object that you want to render
 var data = {
   "data": { "Name": "Priyanka Gupta",
             "url": "http://www.ipriyanka.com"
   },
    "Education": {
  	"Graduation": "BCA",
    	"Master": "MCA"
   },
  "Rank": 1,
  "id": 50
   };

  document.getElementById("container").appendChild(renderjson(data));
</script>
```
 Render JSON doesn't include any CSS for the list, so it's up to you to define the styles. We use the below rules to render structure with colors and a dark background 

```
<style>
	#container {
	text-shadow: none;
	background: #303030;
	padding: 1em;
}
.renderjson a {
	text-decoration: none;
}
.renderjson .disclosure {
	color: crimson;
	font-size: 150%;
}
.renderjson .syntax {
	color: grey;
}
.renderjson .string {
	color: red;
}
.renderjson .number {
	color: cyan;
}
.renderjson .boolean {
	color: plum;
}
.renderjson .key {
	color: lightblue;
}
.renderjson .keyword {
	color: lightgoldenrodyellow;
}
.renderjson .object.syntax {
	color: lightseagreen;
}
.renderjson .array.syntax {
	color: lightsalmon;
}
</style>
``` 



OUTPUT :

```
//Click on the plus icon to expand it
⊕{4 items}
```
``` 
//After clicking plus icon
⊖{
    "data": ⊕{3 items},
    "Education": ⊕{2 items},
    "Rank": 1,
    "id": 50
}
``` 

```
//Amazing view #well structured 
⊖{
    "data": ⊖{
        "FirstName": "Priyanka",
        "LastName": "Gupta",
        "url": "http://www.ipriyanka.com"
    },
    "Education": ⊖{
        "Graduation": "BCA",
        "Master": "MCA"
    },
    "Rank": 1,
    "id": 50
}
``` 


