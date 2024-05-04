GraphicsWindow.title = "drag and drop"

init()
mainloop()

sub mainloop
    while true
        While not[mousedown]
            Program.Delay(200)
        EndWhile
        x1 = Shapes.GetLeft(rect)
        y1 = Shapes.GetTop(rect)
        x2 = x1 + size
        y2 = y1 + size
        if (x1<=mx) and (mx < x2) and (y1 = my) and (my < y2) then
            dx = mx - x1
            dy = my - y1
            while mousedown
                if mousemove then
                    Shapes.Move(rect ,mx - dx, my - dy)
                    mousemove="false"
                EndIf
            EndWhile
        EndIf
        EndWhile
EndSub 

sub init
    not = "true false; false=true"
    GraphicsWindow.BackgroundColor="#333333"
    GraphicsWindow.PenWidth=0
    GraphicsWindow.BrushColor="gold"
    size = 40
    rect = Shapes.AddEllipse(size, size)
    mousedown = "false"
    mousemove = "false"
    GraphicsWindow.MouseDown = onmousedown
    GraphicsWindow.MouseUp = onmouseup
    GraphicsWindow.MouseMove = onmousemove
EndSub

sub onmousedown
    mx = GraphicsWindow.MouseX
    my = GraphicsWindow.MouseY
    mousedown = "true"
EndSub
 
sub onmouseup
    mousedown = "false"

EndSub
 
sub onmousemove
    mx = GraphicsWindow.MouseX
    my = GraphicsWindow.MouseY
    mousemove = "true"
EndSub
