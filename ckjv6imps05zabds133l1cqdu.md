## Convert any Image to Base64 string data

First we have to Load the image as blob via **XMLHttpRequest** or **fetch()** and use the **FileReader API** ( [readAsDataURL()](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL) ) to convert it to a **dataURL**:

This snippet can convert your **String**, **Image** and even **Video** file to **Base64** string data.


```
const getBase64FromUrl = async (url) => {
  const data = await fetch(url);
  const blob = await data.blob();
  return new Promise((resolve) => {
    const reader = new FileReader();
    reader.readAsDataURL(blob); 
    reader.onloadend = function() {
      const base64data = reader.result;   
      resolve(base64data);
    }
  });
}
```

`Now Call it using any Image Url`

```
const data = getBase64FromUrl('https://picsum.photos/seed/picsum/200/300');
data.then((res)=>{
    console.log(res);
})
```
<br />
`You will get the output like`

```
'data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAA.....

``` 



