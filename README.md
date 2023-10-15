# scientific-calculator


    from tkinter import *
    import math
    root=Tk()
    root.geometry("400x570")
    root.title("Calculator")
    root.configure(bg='black')
    root.wm_iconbitmap("calculator.png")
    
    def click(event):
        global scvalue
        text=event.widget.cget("text")
        if text=="=":
            try:
                if scvalue.get().isdigit():
                    value=int(scvalue.get())
                else:
                    value=eval(screen.get())
                scvalue.set(value)
                screen.update()
            except:
                operation=screen.get()
                tri=operation[:3]
                val=float(operation[4:-1])
                if tri=="sin":
                    value=math.sin(val)
                elif tri == "sin":
                    value = math.sin(val)
                elif tri == "cos":
                    value = math.cos(val)
                elif tri == "tan":
                    value = math.tan(val)
                elif tri == "log":
                    value = math.log(val)
                scvalue.set(value)
                screen.update()
        elif text == "Sciti":
            root.geometry("500x570")
            b= Button(f, text="sin", padx=7, pady=2, font="lucida 15 bold",bg="bisque3",fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
            b = Button(f1, text="cos", padx=18, pady=15, font="lucida 15 bold",bg="bisque3",fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
            b= Button(f2, text="tan", padx=18, pady=15, font="lucida 15 bold",bg="bisque3",fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
            b = Button(f3, text="log", padx=18, pady=15, font="lucida 15 bold",bg="bisque3",fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
            b = Button(f4, text="(", padx=4.5, pady=2, font="lucida 15 bold", bg="bisque3", fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
            b = Button(f4, text=")", padx=4.5, pady=2, font="lucida 15 bold", bg="bisque3", fg="black")
            b.pack(side=LEFT, padx=10, ipady=5)
            b.bind("<Button-1>", click)
    
        elif text == "C":
            scvalue.set("")
            screen.update()
        else:
            scvalue.set(scvalue.get()+text)
            screen.update()
    
    
    scvalue=StringVar()
    scvalue.set("")
    screen=Entry(root, textvar=scvalue,font="lucida 45 bold")
    screen.pack(fill=X,ipadx=15,pady=15,padx=15)
    
    f=Frame(root,bg="black")
    
    b9=Button(f,text="  /  ",padx=7,pady=2,font="lucida 15 bold")
    b9.pack(side=LEFT,padx=10,ipady=5)
    b9.bind("<Button-1>",click)
    b8=Button(f,text="  *  ",padx=7,pady=2,font="lucida 15 bold")
    b8.pack(side=LEFT,padx=10,ipady=5)
    b8.bind("<Button-1>",click)
    b7=Button(f,text="C",padx=7,pady=2,font="lucida 15 bold",bg="red")
    b7.pack(side=LEFT,padx=10,ipady=5)
    b7.bind("<Button-1>",click)
    b24=Button(f,text="Sciti",padx=7,pady=2,font="lucida 15 bold",bg="goldenrod")
    b24.pack(side=LEFT,padx=10,ipady=5)
    b24.bind("<Button-1>",click)
    
    f.pack(pady=10 )
    f1=Frame(root,bg="black")
    
    b9=Button(f1,text="9",padx=18,pady=15,font="lucida 15 bold")
    b9.pack(side=LEFT,padx=10,ipady=5)
    b9.bind("<Button-1>",click)
    b8=Button(f1,text="8",padx=18,pady=15,font="lucida 15 bold")
    b8.pack(side=LEFT,padx=10,ipady=5)
    b8.bind("<Button-1>",click)
    b7=Button(f1,text="7",padx=18,pady=15,font="lucida 15 bold")
    b7.pack(side=LEFT,padx=10,ipady=5)
    b7.bind("<Button-1>",click)
    b=Button(f1,text="+",padx=18,pady=15,font="lucida 15 bold")
    b.pack(side=LEFT,padx=10,ipady=5)
    b.bind("<Button-1>",click)
    
    f1.pack(pady=10)
    
    f2=Frame(root,bg="black")
    
    b6=Button(f2,text="4",padx=18,pady=15,font="lucida 15 bold")
    b6.pack(side=LEFT,padx=10,ipady=5)
    b6.bind("<Button-1>",click)
    b5=Button(f2,text="5",padx=18,pady=15,font="lucida 15 bold")
    b5.pack(side=LEFT,padx=10,ipady=5)
    b5.bind("<Button-1>",click)
    b4=Button(f2,text="6",padx=18,pady=15,font="lucida 15 bold")
    b4.pack(side=LEFT,padx=10,ipady=5)
    b4.bind("<Button-1>",click)
    b=Button(f2,text="-",padx=18,pady=15,font="lucida 15 bold")
    b.pack(side=LEFT,padx=10,ipady=5)
    b4.bind("<Button-1>",click)
    f2.pack(pady=10)
    
    f3=Frame(root,bg="black")
    
    b2=Button(f3,text="1",padx=18,pady=15,font="lucida 15 bold")
    b2.pack(side=LEFT,padx=15,ipady=5)
    b2.bind("<Button-1>",click)
    b2=Button(f3,text="2",padx=18,pady=15,font="lucida 15 bold")
    b2.pack(side=LEFT,padx=15,ipady=5)
    b2.bind("<Button-1>",click)
    b1=Button(f3,text="3",padx=18,pady=15,font="lucida 15 bold")
    b1.pack(side=LEFT,padx=15,ipady=5)
    b1.bind("<Button-1>",click)
    f3.pack(pady=10)
    
    f4=Frame(root,bg="black")
    b0=Button(f4,text="0",padx=35,pady=5,font="lucida 15 bold")
    b0.pack(side=LEFT,padx=10,ipady=5)
    b0.bind("<Button-1>",click)
    b=Button(f4,text=".",padx=10,pady=5,font="lucida 15 bold")
    b.pack(side=LEFT,padx=15,ipady=5)
    b.bind("<Button-1>",click)
    b=Button(f4,text="=",padx=30,pady=5,font="lucida 15 bold",bg="green")
    b.pack(side=LEFT,padx=10,ipady=5)
    b.bind("<Button-1>",click)
    
    f4.pack(pady=10)
    
    root.mainloop()
