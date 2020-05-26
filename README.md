# Detectando url em um texto com Javascript

Função que detecta se um link foi passando dentro de um texto.

```javascript
function urlify(text) {
    //var urlRegex = /(((https?:\/\/)|(www\.))[^\s]+)/g;
    //var urlRegex = /(https?:\/\/[^\s]+)/g;
    var urlRegex = /[-a-zA-Z0-9@:%_\+.~#?&//=]{2,256}\.[a-z]{2,4}\b(\/[-a-zA-Z0-9@:%_\+.~#?&//=]*)?/gi;
    return text.replace(urlRegex, function (url, b, c) {
        var url2 = (c == 'www.') ? 'http://' + url : url;
        return '<a href="' + url2 + '" target="_blank">' + url + '</a>';
    })
}
```
