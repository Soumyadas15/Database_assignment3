 1. Fetch all users name from database.
```sql
  SELECT name FROM users;
```

 2. Fetch all tweets of user by user id most recent tweets first.
```sql
  SELECT tweetContent FROM tweets
  WHERE postedBy = 1 ORDER BY createdAt DESC;
```

 3. Fetch like count of particular tweet by tweet id.
```sql
  SELECT COUNT(*) AS likeCount FROM likes
  WHERE tweetId = 1;
```

 4. Fetch retweet count of particular tweet by tweet id.
```sql
  SELECT COUNT(*) AS retwetCount FROM retweets
  WHERE tweetId = 1;
```

 5. Fetch comment count of particular tweet by tweet id.
```sql
  SELECT COUNT(*) AS commentCount FROM tweets
  WHERE isComment = TRUE AND commentOnTweetId = 3;
```

 6. Fetch all users' names who have retweeted a particular tweet by tweet id.
```sql
  SELECT u.name FROM users u
  JOIN retweets r 
  ON u.id = r.userId 
  WHERE r.tweetId = 1;
```
 7. Fetch all commented tweet’s content for particular tweet by tweet id.
```sql
  SELECT t.tweetContest FROM tweets t 
  WHERE t.isComment = TRUE 
  AND t.commentOnTwetId = 1;
```

 8. Fetch user’s timeline (All tweets from users whom I am following with tweet content and user name who has tweeted it)
```sql
  SELECT u.name, t.tweetContent FROM tweets t 
  JOIN users u
  ON t.postedBy = u.id JOIN user_followers uf 
  ON uf.followeID = t.postedBy
  WHERE uf.folowerId = 1 
  ORDER BY t.createdAt DESC;
```
#