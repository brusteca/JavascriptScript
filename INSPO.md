```
searchRequest = CreateObject("roUrlTransfer")
searchRequest.SetURL("http://api.example.com/services/rest/getPhotos")
response = ParseJson(searchRequest.GetToString())
For Each photo In response.photos
        GetImage(photo.title, photo.url)
End For
```

https://docs.brightsign.biz/plugins/servlet/mobile?contentId=984543#content/view/984543

What will `CreateObject("String")` do?
