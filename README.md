## Python Fundamentals

In this checkpoint, we will work with various Python data types and try to accomplish certain tasks using some Python fundamentals. Below, we've defined a dictionary with soccer player names as keys for nested dictionaries containing information about each players age, nationality, and a list of teams they have played for.   


```python
#Ignore this code used to generate tests

from test_scripts.test_class import Test
test = Test()
```


```python
#Run the code below with no changes
players = {
    'L. Messi': {
        'age': 31,
        'nationality': 'Argentina',
        'teams': ['Barcelona']
    },
    'Cristiano Ronaldo': {
        'age': 33,
        'nationality': 'Portugal',
        'teams': ['Juventus', 'Real Madrid', 'Manchester United']
    },
    'Neymar Jr': {
        'age': 26,
        'nationality': 'Brazil',
        'teams': ['Santos', 'Barcelona', 'Paris Saint-German']
    },
    'De Gea': {
        'age': 27,
        'nationality': 'Spain',
        'teams': ['Atletico Madrid', 'Manchester United']
    },
    'K. De Bruyne': {
        'age': 27,
        'nationality': 'Belgium',
        'teams': ['Chelsea', 'Manchester City']
    }
}
```

#### 1) Create a `list` of all the keys in the `players` dictionary. 
- Use python's documentation on dictionaries for help if needed. 
- Store the list of player names in a variable called `player_names` to use in the next question.
- Print out `player_names` to make sure your code returns what you think it does!


```python
# Copy this starter code below to use in your answer
# Look at what is printed by the print statement to check your work!

player_names = None

print(player_names)
```


```python
### BEGIN SOLUTION

player_names = list(players.keys())

player_names.sort()

print(player_names)

test.save(player_names, 'player_names')
test.save(len(player_names), 'len_player_names')



### END SOLUTION
```

    ['Cristiano Ronaldo', 'De Gea', 'K. De Bruyne', 'L. Messi', 'Neymar Jr']



```python
### BEGIN HIDDEN TESTS

player_names.sort()

test.run_test(
    len(player_names), 
    'len_player_names', 
    "looks like you had the wrong number of names?"
)

test.run_test(
    player_names, 
    'player_names', 
    "looks like you had the wrong 5 names?"
)

### END HIDDEN TESTS
```

#### 2) Great! Now that we have each players name, let's use that information to create a `list` of `tuples` containing each player's name along with their nationality. 

- Ex: [('L. Messi', 'Argentina'), ('Christiano Ronaldo', 'Portugal'), ...]
- Store the list in a variable called `player_nationalities`


```python
# Copy this starter code below to use in your answer

player_nationalities = None


print(player_nationalities)
```


```python
### BEGIN SOLUTION

player_nationalities = [(name, players[name]['nationality']) for name in player_names]

#sort by first tuple (name)
player_nationalities.sort(key = lambda x: x[0])

print(player_nationalities)


test.save(player_nationalities, 'player_nationalities')
test.save(len(player_nationalities), 'len_player_nationalities')



### END SOLUTION
```

    [('Cristiano Ronaldo', 'Portugal'), ('De Gea', 'Spain'), ('K. De Bruyne', 'Belgium'), ('L. Messi', 'Argentina'), ('Neymar Jr', 'Brazil')]



```python
### BEGIN HIDDEN TESTS

#sort by first tuple (name)
try:
    player_nationalities.sort(key = lambda x: x[0])

except error:
    raise AssertionError ("looks like you didn't have a list of tuples?")


test.run_test(len(player_nationalities), 
              'len_player_nationalities', 
              "looks like you had the wrong number of players?"
             )

test.run_test(player_nationalities, 
              'player_nationalities', 
              "looks like you had the wrong 5 tuples?"
             )

### END HIDDEN TESTS
```

**3) Now, define a function called `get_players_on_team` that returns a `list` of the names of all the players who have played on a given team.** 

Your function should take two arguments: 
* a dictionary of player information
* a `string` of the team you are trying to find the players for 

**Be sure that your function has a `return` statement.**


```python
# Copy and run the code below after your answer 
# Make sure it prints what you think you coded!

players_on_manchester_united = get_players_on_team(players,'Manchester United')
print(players_on_manchester_united)
   
```


```python
### BEGIN SOLUTION

def get_players_on_team(dict_,team_name):
    player_list = []
    for player in dict_:
        if team_name in dict_[player]['teams']:
            player_list.append(player)
    return player_list

players_on_manchester_united = get_players_on_team(players,'Manchester United')
print(players_on_manchester_united)

players_on_manchester_united.sort()

test.save(players_on_manchester_united, "man_u_players")
test.save(len(players_on_manchester_united), "len_man_u")



### END SOLUTION
```

    ['Cristiano Ronaldo', 'De Gea']



```python
### BEGIN HIDDEN TESTS

try:
    players_on_manchester_united.sort()
    
except error:
    raise AssertionError ("looks like you didn't have the right type of output for your function?")


test.run_test(len(players_on_manchester_united), 
              "len_man_u",
              "looks like you had the wrong number of players?"
             )
    
test.run_test(players_on_manchester_united, 
              "man_u_players",
              "looks like you had the wrong players?"
             )

### END HIDDEN TESTS
```


```python

```
