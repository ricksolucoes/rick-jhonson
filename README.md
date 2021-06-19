# rick-jhonson
Middleware for parse JSON in HORSE
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
