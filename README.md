# Stanford_CS224W_Project
CS224W Project at Stanford University - Social Network Analytics

## Data Wranling 

### action_proto
Raw data 

### edgeattr
```sql
SELECT
  a.player_name,
  b.player_name,
  b.wins-a.wins AS delta_wins 
FROM [action_proto] as a
JOIN [action_proto] as b
  ON a.game_id = b.game_id
WHERE 
a.player_name!=b.player_name
```
### edgesplayers
```sql
SELECT
  a.player_name,
  b.player_name
FROM [action_proto] as a
JOIN [action_proto] as b
  ON a.game_id = b.game_id
WHERE 
a.player_name!=b.player_name
```
### nodes_tot_wins
```sql
SELECT
  player_name,
  SUM(wins) as wins,
FROM [actions_table]
WHERE wins>0
GROUP BY player_name
```


### nodes_tot_loss
```sql
SELECT
  player_name,
  SUM(wins) as loss,
FROM [actions_table]
WHERE wins<0
GROUP BY player_name
```

### nodes_net_wins
```sql
SELECT
  player_name,
  SUM(wins) as wins,
FROM [actions_table]
GROUP BY player_name
```

