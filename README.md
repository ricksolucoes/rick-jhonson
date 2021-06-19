# rick-jhonson
Middleware for parse JSON in HORSE
```
uses Horse, Horse.Rick-Jhonson, System.JSON;

begin
  THorse.Use(Jhonson());

  THorse.Post('/ping',
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
