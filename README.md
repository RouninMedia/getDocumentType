# getDocumentType
A front-end function in JavaScript (and a server-side counterpart function in PHP) which confirms the **Document Type** as `HTML` or `SVG`.

_____

## PHP Version

```php
function getDocumentType ($Document_URL) {
	
  $Document_Headers = get_headers($Document_URL);

  foreach($Document_Headers as $Index => $Header) {
	
   if (substr($Header, 0, 13) === 'Content-Type:') {

      return explode(';', explode(' ', $Header)[1])[0];
    }
  }
}

getDocumentType('https://'.$_SERVER['HTTP_HOST'].$_SERVER['PHP_SELF']);
```
_____

## JavaScript Version

```js
document.querySelector(':root').nodeName;
```
