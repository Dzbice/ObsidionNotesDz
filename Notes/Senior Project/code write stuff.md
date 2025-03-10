``` python
def build_heuristic_db(state, actions, max_moves = 20, heuristic = None):
    if heuristic is None:
        heuristic = {state: 0}
    que = [(state, 0)]
    node_count = sum([len(actions) ** (x + 1) for x in range(max_moves + 1)])
    with tqdm(total=node_count, desc='Heuristic DB') as pbar:
        while True:
            if not que:
                break
            s, d = que.pop()
            if d > max_moves:
                continue
            for a in actions:
                cube = RubiksCube(state=s)
                if a[0] == 'h':
                    cube.horizontal_twist(a[1], a[2])
                elif a[0] == 'v':
                    cube.vertical_twist(a[1], a[2])
                elif a[0] == 's':
                    cube.side_twist(a[1], a[2])
                a_str = cube.stringify()
                if a_str not in heuristic or heuristic[a_str] > d + 1:
                    heuristic[a_str] = d + 1
                que.append((a_str, d+1))
                pbar.update(1)
    return heuristic
```
Starts by defining heuristic 
makes a queue with initial being solved cube
while true: it's running till it breaks itself basically
s,d: latest state and move count
if d is greater than 20 moves it'll go to next thing
for a in actions: i.e for every move it can make
	does a move to cube that was made just then
then, if cube not in the heuristic, OR the move count for the cube in the huristic 
