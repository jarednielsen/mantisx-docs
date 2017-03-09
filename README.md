# Mantis Web API

- [Mantis](http://mantisx.us-east-1.elasticbeanstalk.com/mantisx)
- Use POST

## /get-session

### Request
`user_secret_key` is length 25
```
{
	"user_pk": 2,
	"user_secret_key": "fffff...",
	"session_pks": [10, ...]
}
```

### Response
`gun_type` maps (0: pistol), (1: rifle)  
`fire_type` maps (1: live), (2: dry), (3: co2)  
`date` takes "2016-12-31-11-59-59" or "2016-12-31-11-59-59". Use seconds to avoid duplicates
`gun.make`, `gun.model`, `gun.caliber` take empty strings if no gun selected.
```
{
	"sessions": [{
		"pk": 10,
		"user_pk": 2,
		"average_score": 60.4323,
		"date": "2016-07-15-13-04-59",
		"fire_type": 1,
		"firearm": {
			"make": "glock",
			"model": "19",
			"caliber": "9mm"
		},
		"gun_type": 0,
		"right_handed": True,
		"shots": [{
			"pk": 212,
			"session_pk": 10,
			"angle": 243.3434,
			"bullseye": False,
			"deleted": False,
			"problem": "BREAKING WRIST DOWN",
			"score": 60.4323,
			"split": 0.1,
			"trigger_hold": 1.294893,
			"trigger_pull": 0.49837,
			"shot_index": 50,
			"hold_index": 0,
			"pull_index": 40,
			"pitch": [...],
			"yaw": [...]
		}],
	}, {...
	}]
}
```

## /post-session

### Request
```
{
	"secret_key": "mantis<3bookoo",
	"user_pk": 2,
	"user_secret_key": "fffff...",
	"session_count": 30,
	"sessions": [{
		"average_score": 60.4323,
		"date": "2016-07-15-13-04-59",
		"fire_type": 1,
		"firearm": {
			"make": "glock",
			"model": "19",
			"caliber": "9mm"
		},
		"gun_type": 0,
		"right_handed": True,
		"shots": [{
			"angle": 243.3434,
			"bullseye": False,
			"deleted": False,
			"problem": "BREAKING WRIST DOWN",
			"score": 60.4323,
			"split": 0.1,
			"trigger_hold": 1.294893,
			"trigger_pull": 0.49837,
			"shot_index": 50,
			"hold_index": 0,
			"pull_index": 40,
			"pitch": [...],
			"yaw": [...]
		}],
	}, {...
	}]
}
```

### Response
```
{
	'success': 'true', 
	'session_count': 30, 
	'session_pks': [3, ...]
}
```
