[<h1>ExpNo 7 : Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game</h1> 
<h3>Name:   RAASHITH RUHULLA R  </h3>
<h3>Register Number:    2305002018      </h3>
<H3>Aim:</H3>
<p>
Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game
</p>
<h1>GOALS of Alpha-Beta Pruning in MiniMax Search Algorithm</h1>

<h3>Improve the decision-making efficiency of the computer player by reducing the number of evaluated nodes in the game tree.</h3>
<h3>Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning and the Minimax algorithm with Python Code.</h3>
<h1>IMPLEMENTATION</h1>

The project involves developing a Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning with the Minimax algorithm. Using this algorithm, the computer player analyzes the game state, evaluates possible moves, and selects the optimal action based on the anticipated outcomes.

<h1>The Minimax algorithm</h1>

recursively evaluates all possible moves and their potential outcomes, creating a game tree.

<h1>Alpha-Beta pruning</h1>

Alpha–Beta (𝛼−𝛽) algorithm is actually an improved minimax using a heuristic. It stops evaluating a move when it makes sure that it’s worse than a previously examined move. Such moves need not to be evaluated further.

When added to a simple minimax algorithm, it gives the same output but cuts off certain branches that can’t possibly affect the final decision — dramatically improving the performance

## PROGRAM
```python
import time
b=[['.']*3 for _ in range(3)]
turn='X'

def show():[print('|'.join(r))for r in b];print()
def win():
    for i in range(3):
        if b[i][0]==b[i][1]==b[i][2] != '.':return b[i][0]
        if b[0][i]==b[1][i]==b[2][i] != '.':return b[0][i]
    if b[0][0]==b[1][1]==b[2][2] != '.':return b[0][0]
    if b[0][2]==b[1][1]==b[2][0] != '.':return b[0][2]
    return '.' if all(b[i][j]!='.'for i in range(3)for j in range(3))else None

def maxv(a,beta):
    r=win()
    if r=='X':return -1,0,0
    if r=='O':return 1,0,0
    if r=='.':return 0,0,0
    v=-2;x=y=0
    for i in range(3):
        for j in range(3):
            if b[i][j]=='.':
                b[i][j]='O';m,_,_=minv(a,beta);b[i][j]='.'
                if m>v:v,x,y=m,i,j
                if v>=beta:return v,x,y
                a=max(a,v)
    return v,x,y

def minv(a,beta):
    r=win()
    if r=='X':return -1,0,0
    if r=='O':return 1,0,0
    if r=='.':return 0,0,0
    v=2;x=y=0
    for i in range(3):
        for j in range(3):
            if b[i][j]=='.':
                b[i][j]='X';m,_,_=maxv(a,beta);b[i][j]='.'
                if m<v:v,x,y=m,i,j
                if v<=a:return v,x,y
                beta=min(beta,v)
    return v,x,y

while 1:
    show();r=win()
    if r:print('X wins!'if r=='X'else'O wins!'if r=='O'else'Tie!');break
    if turn=='X':
        t=time.time();_,x,y=minv(-2,2)
        print(f"Eval:{round(time.time()-t,4)}s Move:X={x},Y={y}")
        x,y=int(input("X:")),int(input("Y:"))
        if 0<=x<3and 0<=y<3and b[x][y]=='.':b[x][y]='X';turn='O'
        else:print("Invalid!")
    else:_,x,y=maxv(-2,2);b[x][y]='O';turn='X'
```
<hr>
<h2>Sample Input and Output:</h2>
<img width="500" height="397" alt="image" src="https://github.com/user-attachments/assets/192582e6-e3f4-4593-92c6-a5e0750afed7" />
<img width="440" height="294" alt="image" src="https://github.com/user-attachments/assets/bac6cb24-1fc3-4e26-8545-7f8d8932df3f" />
<img width="487" height="340" alt="image" src="https://github.com/user-attachments/assets/f5a93055-9b81-494a-a672-340114bb43cb" />




## RESULT
We have successfully implemented Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game.
](https://github.com/ksrekha3/EX-6-Implement-Mini-Max-Search-Algorithm/blob/main/README.md)
