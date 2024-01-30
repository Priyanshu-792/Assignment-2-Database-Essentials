# Twitter Sample Database
<img src="Assignment 2 Twitter Sample Database.png">
### Users Table
This table stores information about users in the system. Users can update their personal details like email and mobile number.

| Column Name   | Data Type    | Description                        |
|---------------|--------------|------------------------------------|
| user_id       | integer      | Primary key uniquely identifying a user. |
| name          | varchar      | Name of the user.                  |
| email         | varchar      | Email address of the user.         |
| phone_number  | varchar      | Phone number of the user.          |
| created_at    | datetime     | Timestamp indicating user creation.|
| updated_at    | datetime     | Timestamp indicating last update of user data.|

### Tweets Table
This table records tweets posted by users along with related information.

| Column Name      | Data Type    | Description                            |
|------------------|--------------|----------------------------------------|
| tweet_id         | integer      | Primary key uniquely identifying a tweet. |
| comment_id       | integer      | Foreign key referencing another tweet if this is a comment. |
| user_id          | integer      | Foreign key referencing the user who posted the tweet. |
| tweet_content    | text         | Content of the tweet.                  |
| commented_content| text         | Content of the commented tweet if this is a comment. |
| parent_tweet_id  | integer      | Foreign key referencing the original tweet if this is a comment. |
| created_at       | datetime     | Timestamp indicating tweet creation.  |

### Likes Table
This table records likes on tweets and retweets by users.

| Column Name   | Data Type    | Description                                       |
|---------------|--------------|---------------------------------------------------|
| like_id       | integer      | Primary key uniquely identifying a like action.  |
| tweet_id      | integer      | Foreign key referencing the liked tweet.         |
| retweet_id    | integer      | Foreign key referencing the retweeted tweet.     |
| user_id       | integer      | Foreign key referencing the user who liked.      |
| created_at    | datetime     | Timestamp indicating when the like action occurred. |

### Retweets Table
This table records retweets made by users.

| Column Name       | Data Type    | Description                                            |
|-------------------|--------------|--------------------------------------------------------|
| retweet_id        | integer      | Primary key uniquely identifying a retweet action.    |
| original_tweet_id | integer      | Foreign key referencing the original tweet being retweeted. |
| user_id           | integer      | Foreign key referencing the user who retweeted.       |
| created_at        | datetime     | Timestamp indicating when the retweet action occurred.|

### Follows_datas Table
This table records user following relationships.

| Column Name       | Data Type    | Description                                            |
|-------------------|--------------|--------------------------------------------------------|
| follow_id         | integer      | Primary key uniquely identifying a follow action.     |
| follower_user_id  | integer      | Foreign key referencing the user who is following.    |
| following_user_id | integer      | Foreign key referencing the user who is being followed. |
| created_at        | datetime     | Timestamp indicating when the follow action occurred. |
