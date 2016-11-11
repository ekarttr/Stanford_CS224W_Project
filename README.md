# Stanford_CS224W_Project
CS224W Project at Stanford University - Social Network Analytics


#Data Wranling 

SELECT
  a.player_name,
  b.player_name,
  b.wins-a.wins AS delta_wins 
FROM [google-platform-demo:test1_kt.actions] as a
JOIN [google-platform-demo:test1_kt.actions] as b
  ON a.game_id = b.game_id
WHERE 
a.player_name!=b.player_name


SELECT
  player_name,
  SUM(wins) as loss,
FROM [actions_table]
WHERE wins<0
GROUP BY player_name 

