start:
TextWindow.Clear()
round2 = 10
round = 0
number2 = Math.GetRandomNumber(100)
TextWindow.Title = "guess my numder"
TextWindow.ForegroundColor = "red"
TextWindow.WriteLine("guess my number")
TextWindow.ForegroundColor = "gray"
TextWindow.WriteLine("")
TextWindow.Writeline("my number is less than 100")
TextWindow.WriteLine(" you have "+ round2+ "rounds")
begin:
TextWindow.Write("what's my number?")
number=TextWindow.ReadNumber()
if number=number2 then
    TextWindow.WriteLine("you won")
    TextWindow.WriteLine("would you play again y/n")
    playagain=TextWindow.Read()
    if playagain="y" then
        GoTo start
    Else
        Program.End()
    EndIf
Else
    if number<number2 then
        TextWindow.WriteLine("too small")
    else
        TextWindow.WriteLine("too large")
    EndIf
    if (round2-round)-1<1 then
        round3="rounds"
    else 
        round3="round"
    EndIf
    TextWindow.WriteLine("you have"+((round2-round)-1)+" "+ round3+"left")
EndIf

if round < round2 then
    GoTo begin
Else
    TextWindow.WriteLine("you have run out of rounds")
    TextWindow.WriteLine("would you like to play again y/n")
    if playagain ="y" then
    GoTo start
    else
        Program.End()
        EndIf
EndIf

