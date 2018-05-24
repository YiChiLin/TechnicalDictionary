# MVC 5

### Global.asax
- Project一起來會最先跑這個

### App_Start
- Application 一起來時，放一些設定


### ModelState.IsValid
- MVC內建功能，驗證form傳進來的value是有符合規則的



# API
### IHttpActionResult
- 回傳Http Status
- Ex: 
``` csharp
    public IHttpActionResult Create(){
        return Ok();        
    }
```
