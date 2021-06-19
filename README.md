# rick-jhonson
Middleware for parse JSON in HORSE

Está e uma adaptação de https://github.com/HashLoad/jhonson, versão 1.1.1 adicionado a possibilidade de utilizar o Patch nas requisições.
```
uses Horse, Horse.Rick.Jhonson, System.JSON;

begin
  THorse.Use(RickJhonson());

  THorse
    .Post('/ping',
      procedure(Req: THorseRequest; Res: THorseResponse; Next: TProc)
      var
        LBody: TJSONObject;
      begin
        LBody := Req.Body<TJSONObject>;
        Res.Send<TJSONObject>(LBody);
      end)
    
    .Put('/ping',
      procedure(Req: THorseRequest; Res: THorseResponse; Next: TProc)
      var
        LBody: TJSONObject;
      begin
        LBody := Req.Body<TJSONObject>;
        Res.Send<TJSONObject>(LBody);
      end)
    
    .Patch('/ping',
      procedure(Req: THorseRequest; Res: THorseResponse; Next: TProc)
      var
        LBody: TJSONObject;
      begin
        LBody := Req.Body<TJSONObject>;
        Res.Send<TJSONObject>(LBody);
      end);

  THorse.Listen(9000);
end;
```
