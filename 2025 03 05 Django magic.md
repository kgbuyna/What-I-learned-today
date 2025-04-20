1. Mediator design pattern 
	Reducing dependency between components by each component interacting through the mediator object. Mediator design make those components reusable because there is no relation with other components  in other words using it somewhere else have no impact on others. 
2. Connection pool.
	This is several connections made to database server. To avoid the overhead , making new connection to the database on every request. It also allows the application to make multiple , simultaneous connection with database. Django database server manages those connections.
3. Multithreading and multiprocessing
	Multithreading is good for heavy IO operation while multiprocessing for CPU heavy operation.  Multithreading is concurrent while multiprocessing is parallel. 
4. Mixin class pattern
	If one feature is used in many classes,  Create the class for this feature or if it is optional feature. 
5. Raw query exectuted in ORM of the Django
```
In [2]: tweet = Tweet.objects.get(id=8)  
In [3]: from django.db import connection  
In [4]: connection.queries  
Out[4]:[{'sql': 'SELECT "tweeter_tweet"."id", "tweeter_tweet"."user_id", "tweeter_tweet"."text", "tweeter_tweet"."timestamp" FROM "tweeter_tweet" WHERE "tweeter_tweet"."id" = 8',    'time': '0.001'}]
```
