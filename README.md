## Python Fundamentals

In this checkpoint, we will work with various Python data types and try to accomplish certain tasks using some Python fundamentals. Below, we've defined a dictionary with soccer player names as keys for nested dictionaries containing information about each players age, nationality, and a list of teams they have played for.   


```python
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
player_names = list(players.keys())

print(player_names)
```

#### 2) Great! Now that we have each players name, let's use that information to create a `list` of `tuples` containing each player's name along with their nationality. 

- Ex: [('L. Messi', 'Argentina'), ('Christiano Ronaldo', 'Portugal'), ...]
- Store the list in a variable called `player_nationalities`


```python
player_nationalities = [(name, players[name]['nationality']) for name in player_names]

print(player_nationalities)
```

**3) Now, define a function called `get_players_on_team` that returns a `list` of the names of all the players who have played on a given team.** 

Your function should take two arguments: 
* a dictionary of player information
* a `string` of the team you are trying to find the players for 

**Be sure that your function has a `return` statement.**


```python
def get_players_on_team(dict_,team_name):
    player_list = []
    for player in dict_:
        if team_name in dict_[player]['teams']:
            player_list.append(player)
    return player_list

players_on_manchester_united = get_players_on_team(players,'Manchester United')
print(players_on_manchester_united)
```

    ['Cristiano Ronaldo', 'De Gea']

