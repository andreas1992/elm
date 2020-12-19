# Elm notes
* Data structures er "immutable" i elm, dvs. du kan ikke endre innholdet i de (noe som ikke gir mening å gjøre i funksjonell programmering)
* Okei nå forstår jeg det, du «partially apply», altså du utfører en metode delvis. 
    * sA s1 s2 tar inn 2 stings, men dersom du lager en nY metode/variabel, og først gir den bare sA «hei» (s1 altså), så s0 (ny metode) = sA (metode 1) «hey» (parameter 1). 
    * Så kan du etterpå gi den nye s0 metoden den andre parameteren etterpå. Så du fullfører sånn sett ikke hele metode-kallet.
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
    * Du _kan_ returnere tuple fra en funksjon, men da må alle retur-verdier være samme tuple av samme type (slik som med to ellementer i en liste). 
+ Con
    ```
    > mL = [2, 3, 4]
    [2,3,4] : List number
    > mL2 = 1 :: mL
    [1,2,3,4] : List number
    ```        
    * Man legger til en ny variabel på begynnelsen av list/string etc, omvendt av pipe operator
 + Record
    ```
    > b = {n = "bob", a = 30}
    { a = 30, n = "bob" }
    > b.n
    "bob" : String
    > b.a
    30 : number
    ```
    * Kan også lage det som en funksjon (??)
    ```
    > .n b
    "bob" : String
    ```
    * Immutable oppdatering av records
        * Da bruker du en sånn | "pipe operator"
    ```
    > rec1 = {time = 4, huh = "pm"}
    { huh = "pm", time = 4 }
    : { huh : String, time : number }

    > rec3 = {rec1 | time = 1}
    { huh = "pm", time = 1 }
    : { huh : String, time : number }
    ```
+ Type alias
    * Kan bruke til å anngi hvilke typer du må ha i en data-struktur, en record for eksempel
        * Obs: int må skrives som **I**nt..
    * Funker litt som en konstruktør
    ```
    > type alias User = {id:Int, username:String, location:String}
    > User
    <function> : Int -> String -> String -> User
    ```
    * For å opprette element av en gitt Type:
    ```
    > user1 = User 1 "elming" "NOR"
    { id = 1, location = "NOR", username = "Eelming" }
        : User
    ```
    * Dersom du ikke fyller ut hele Type definisjonen (konstruktøren) i initlialisering av en variabel, så utfører den det delvis allikevel.
    ```
    > user2 = User 3
    <function> : String -> String -> User
    ```
    * Og dersom du vil sette inn gjennværende verdier:
        * Obs: ikke noe "=" tegn mellom user2 og 2. Type parameter..
    ```
    > user2 "kultNavn" "SWE"
    { id = 3, location = "SWE", username = "kultNavn" }
        : User
    ```


