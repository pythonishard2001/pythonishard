from tkinter import *
import random
from tkinter import messagebox
import time
import turtle


def new_board():
    global random_no, turn
    random_no = random.sample(range(16),16)
    turn='Player A'
    blank_label.grid_forget()
    welcome_label.grid_forget()
    show_button()
    return


def show_button():
    global cell_chosen
    cell_chosen = [-1,-1]

    
    Label(game_window, width=5, bg= 'light blue'). grid(row=0, column=0)
    Button(game_window, image=blank_image,command=cell_0).grid(row=1,column=1)
    Button(game_window, image=blank_image,command=cell_1).grid(row=1,column=2)
    Button(game_window, image=blank_image,command=cell_2).grid(row=1,column=3)
    Button(game_window, image=blank_image,command=cell_3).grid(row=1,column=4)

    Button(game_window, image=blank_image,command=cell_4).grid(row=2,column=1)
    Button(game_window, image=blank_image,command=cell_5).grid(row=2,column=2)
    Button(game_window, image=blank_image,command=cell_6).grid(row=2,column=3)
    Button(game_window, image=blank_image,command=cell_7).grid(row=2,column=4)

    Button(game_window, image=blank_image,command=cell_8).grid(row=3,column=1)
    Button(game_window, image=blank_image,command=cell_9).grid(row=3,column=2)
    Button(game_window, image=blank_image,command=cell_10).grid(row=3,column=3)
    Button(game_window, image=blank_image,command=cell_11).grid(row=3,column=4)

    Button(game_window, image=blank_image,command=cell_12).grid(row=4,column=1)
    Button(game_window, image=blank_image,command=cell_13).grid(row=4,column=2)
    Button(game_window, image=blank_image,command=cell_14).grid(row=4,column=3)
    Button(game_window, image=blank_image,command=cell_15).grid(row=4,column=4)
    Label(game_window, width=5, bg='light blue').grid(row=5, column=5)
    Label(game_window, width=20, bg='light blue', font='Arial 24 bold').grid(row=6, columnspan=6)
    Label(game_window, text=turn+"'s turn", width=14, bg='light blue',font='Arial 16 bold').grid(row=7, columnspan=6)

    count =0
    for x in range(1,5):     
        for y in range(1,5):       
            if random_no[count] == 'Player A' or random_no[count] == 'Player B':            
                Label(game_window, image=(player_a if random_no[count]=='Player A' else player_b)).grid(row=x, column=y)
            else:
                if random_no.count('Player A')+random_no.count('Player B') == 14:
                    Label(game_window, image=grey_image).grid(row=x,column=y)
                


            count += 1

    if random_no.count('Player A')+random_no.count('Player B') == 14:
        Label(game_window, text='Game Over!!', width =14, bg='blue',fg='yellow',\
              font='Arial 16 bold').grid(row=7, columnspan=6)
        winner=('Player A' if random_no.count('Player A') > random_no.count('Player B') else 'Player B')
        messagebox.showinfo('Game Over', 'The winner is '+winner)
    return
    
def cell_0():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[0]]).grid(row=1,column=1)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 0
        else:
            cell_chosen[1] = 0
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_1():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[1]]).grid(row=1,column=2)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 1
        else:
            cell_chosen[1] = 1
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_2():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[2]]).grid(row=1,column=3)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 2
        else:
            cell_chosen[1] = 2
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_3():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[3]]).grid(row=1,column=4)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 3
        else:
            cell_chosen[1] = 3
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_4():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[4]]).grid(row=2,column=1)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 4
        else:
            cell_chosen[1] = 4
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_5():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[5]]).grid(row=2,column=2)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 5
        else:
            cell_chosen[1] = 5
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_6():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[6]]).grid(row=2,column=3)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 6
        else:
            cell_chosen[1] = 6
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_7():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[7]]).grid(row=2,column=4)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 7
        else:
            cell_chosen[1] = 7
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_8():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[8]]).grid(row=3,column=1)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 8
        else:
            cell_chosen[1] = 8
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_9():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[9]]).grid(row=3,column=2)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 9
        else:
            cell_chosen[1] = 9
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_10():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[10]]).grid(row=3,column=3)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 10
        else:
            cell_chosen[1] = 10
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_11():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[11]]).grid(row=3,column=4)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 11
        else:
            cell_chosen[1] = 11
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_12():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[12]]).grid(row=4,column=1)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 12
        else:
            cell_chosen[1] = 12
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_13():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[13]]).grid(row=4,column=2)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 13
        else:
            cell_chosen[1] = 13
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_14():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[14]]).grid(row=4,column=3)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 14
        else:
            cell_chosen[1] = 14
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return

def cell_15():
    if -1 in cell_chosen:
        Label(game_window, image=cell_image[random_no[15]]).grid(row=4,column=4)
        if cell_chosen[0] == -1:
            cell_chosen[0] = 15
        else:
            cell_chosen[1] = 15
            check_match()
    else:
        messagebox.showwarning('Player', 'To continue,please click the button at the bottom.')
    return


def check_match():
    global turn
    image_chosen = [random_no[cell_chosen[0] ] , random_no[cell_chosen[1] ] ]
    image_chosen.sort()

    if image_chosen in match:
        random_no[cell_chosen[0] ] = random_no[cell_chosen[1] ] = turn
        messagebox.showinfo('Nice', 'Horray! As a reward, you can continue the game.')
        show_button()
    else:
        turn = ('Player B' if turn == 'Player A' else 'Player A')             
        Button(game_window, text='Click here to continue', width=20, bg='blue', fg='yellow', \
           font='Arial 16 bold', command=show_button).grid(row=6, columnspan=6)
    return


def how_to_play():
    help_window = Tk()
    help_window.title('Help') # This creates the title of the help windows
    help_window.geometry('850x400')
    help_window.resizable(False, False)
    help_window.configure(background= 'light blue')
    help_window.iconbitmap('14.ico')

    play_message = '''
    1.  Please select New Game from the Game menu.
    2.  Please select any two of the cells. Points are awarded to players according to their matched pairs.
    3.  All the shown images will be in randomized order on the chosen cells.
    4.  Click the "Click here to continue" button to continue the game.
    5.  A message box will pop out if you have chosen two same image cells and close the message box. 
    6.  Player with correct pair image will be awarded to play one more round.
    7.  The game will automatically take turn if player failed to match correct pair.
    8.  Players' name will be shown on their matched pair for the entire game.
    9.  The game will end once 14 cells show respective players' name.
    10.The player with higher point will be the winner.
    '''
    
    Label(help_window, width=3, bg='light blue').grid(row=0, column=0)
    Label(help_window, text='How to play', width=12, bg= 'light blue', fg='black',\
              font='Arial 24 bold').grid(row=1, columnspan=3, sticky=W)
    Label(help_window, text= play_message, font='Arial 12 bold', justify=LEFT). grid(row=2, column=1)
    Label(help_window, width=3, bg='light blue').grid(row=3, column=2)
    Button(help_window, text='Reutrn to game', width=20, bg='Steelblue2', fg='mint cream', \
               font='Arial 16 bold', command=help_window.destroy).grid(row=4, column=1, sticky=S)    
    return

def about_this_game():
    title = 'HI'
    content = '''
    
    Author: HI
    Date: 2021 Nov'''
    messagebox.showinfo(title, content)
    return


#Main body of the program
game_window = Tk()
game_window.title('HI') # This creates the title of the windows
game_window.geometry('620x680')
game_window.resizable(False, False)
game_window.configure(background= 'light blue')
game_window.iconbitmap('14.ico')

top_menu =Menu()
game_window.config(menu=top_menu)
game_menu = Menu(tearoff=False)
help_menu = Menu(tearoff=False)

top_menu.add_cascade(label="Game", menu=game_menu)
top_menu.add_cascade(label="Help", menu=help_menu)

game_menu.add_command(label="New Game",command=new_board)
game_menu.add_command(label="Exit",command=game_window.destroy)

help_menu.add_command(label="How to play",command=how_to_play)
help_menu.add_command(label="About this game",command=about_this_game)



cell_image = [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]
cell_image[0]=cell_image[1]=PhotoImage(file='1.png')
cell_image[2]=cell_image[3]=PhotoImage(file='2.png')
cell_image[4]=cell_image[5]=PhotoImage(file='3.png')
cell_image[6]=cell_image[7]=PhotoImage(file='4.png')
cell_image[8]=cell_image[9]=PhotoImage(file='5.png')
cell_image[10]=cell_image[11]=PhotoImage(file='6.png')
cell_image[12]=cell_image[13]=PhotoImage(file='7.png')
cell_image[14]=cell_image[15]=PhotoImage(file='8.png')

blank_image=PhotoImage(file= '9.png')
grey_image=PhotoImage(file='10.png')
player_a=PhotoImage(file='11.png')
player_b=PhotoImage(file='12.png')

match = [ [0,1], [2,3], [4,5], [6,7], [8,9], [10,11], [12,13], [14,15] ]

blank_label=Label(game_window, width=10,height=10,bg='light blue')
blank_label.grid(row=0, column=0)

welcome_label=Label(game_window,fg='black', bg='light blue', font='Arial 16 bold',\
text="Welcome to the game of 'find the Pair'\nPlease choose Game --> New Game to start")
welcome_label.grid(row=1, column=1)

#Timer
window = turtle.Screen()
window.tracer(0)

player = turtle.Turtle()
timer_text = turtle.Turtle()

start = time.time()
while time.time() - start < 5:
    player.forward(1)
    player.left(1)
    timer_text.clear()
    timer_text.write(int(time.time() - start), font=("Courier", 30))

    window.update()

turtle.done()

game_window.mainloop()
