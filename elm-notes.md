* Okei nå forstår jeg det, du «partially apply», altså du utfører en metode delvis. sA s1 s2 tar inn 2 stings, men dersom du lager en nY metode/variabel, og først gir den bare sA «hei» (s1 altså), så s0 (ny metode) = sA (metode 1) «hey» (parameter 1). Så kan du etterpå gi den nye s0 metoden den andre parameteren etterpå. Så du fullfører sånn sett ikke hele metode-kallet.
+ `sA "hello" (sC "wo" "rld") `
+ `5 |> sN 3`
    * Pipe operator
    * Result = 8;
    * Putter det på slutten
    * Du kan chaine slike pipes
    *   ```
        > sA s1 s2 = s1 ++ " " ++ s2
        <function> : String -> String -> String
        > "hey" |> sA "there"
        "there hey" : String`
        ```

+ `if 1 < 2 then "less" else "more"`
    * Man MÅ ha med else, og også «then»
+ Tuple
    ```
      > (True, 4, "bob")
      (True,4,"bob") : ( Bool, number, String )
    ```    
    * I en liste MÅ de være like i alle liste-verdiene
        * `[("a", 1), ("b", 2)]`
