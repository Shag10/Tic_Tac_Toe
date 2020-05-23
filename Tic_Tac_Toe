board=[' ' for x in range(10)]
def insert(l,pos):
    global board
    board[pos]=l
def free_space(pos):
    return board[pos]==' '
def pboard(borad):
    print('   |   |')
    print(' ' + board[1] + ' | ' + board[2] + ' | ' + board[3])
    print('   |   |')
    print('-----------')
    print('   |   |')
    print(' ' + board[4] + ' | ' + board[5] + ' | ' + board[6])
    print('-----------')
    print('   |   |')
    print(' ' + board[7] + ' | ' + board[8] + ' | ' + board[9])
    print('   |   |')
    
def win(tic,le):
    return (tic[1]==le and tic[2]==le and tic[3]==le) or (tic[4]==le and tic[5]==le and tic[6]==le) or (tic[7]==le and tic[8]==le and tic[9]==le) or (tic[1]==le and tic[4]==le and tic[7]==le) or (tic[2]==le and tic[5]==le and tic[8]==le) or (tic[3]==le and tic[6]==le and tic[9]==le) or (tic[1]==le and tic[5]==le and tic[9]==le) or (tic[3]==le and tic[5]==le and tic[7]==le)
def player():
    r=True
    while r:
        m=input("Select a position to place 'X' (1-9): ")
        try:
            m=int(m)
            if m>0 and m<10:
                if free_space(m):
                    r=False
                    insert('X',m)
                else:
                    print("Sorry, space is occupied")
            else:
                print("Please type valid number from '1-9'")
        except:
            print("Please type a number :(")
def comp():
    possMove=[x for x,l in enumerate(board) if l==' ' and x!=0]
    m=0
    for let in ['O','X']:
        for i in possMove:
            boardc=board[:]
            boardc[i]=let
            if win(boardc,let):
                m=i
                return m
    corner=[]
    for i in possMove:
        if i in [1,3,7,9]:
            corner.append(i)
    if len(corner)>0:
        m=random(corner)
        return m
    if 5 in possMove:
        m=5
        return m
    edge=[]
    for i in possMove:
        if i in [2,4,6,8]:
            edge.append(i)
    if len(edge)>0:
        m=random(edge)
    return m
def random(li):
    import random
    ln=len(li)
    r=random.randrange(0,ln)
    return li[r]
def board_full(board):
    if board.count(' ')>1:
        return False
    else:
        return True
def main():
    print("Tic Tac Toe for you!!!!")
    pboard(board)
    while not(board_full(board)):
        if not(win(board,'O')):
            player()
            pboard(board)
        else:
            print("Sorry, Computer Win :o!! Better Luck Next Time:)")
            break
        if not(win(board,'X')):
            m=comp()
            if m==0:
                print("Draw!")
            else:
                insert('O',m)
                print("Computer placed 'O' in position %d"%m)
                pboard(board)
        else:
            print("Hurray!! You Won:):):) !! Congratulations ;)")
            break
    if board_full(board):
        print("Draw")
        
main()
while True:
    ans=input("Do you want to play again? (Y/N)")
    if ans.lower()=='y' or ans.lower=='yes':
        board=[' ' for x in range(10)]
        print("-------------------")
        main()
    else:
        break
