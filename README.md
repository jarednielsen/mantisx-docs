# Mantis Web API

- [mantisx.us-east-1.elasticbeanstalk.com/mantisx]Mantis
- Use POST

## /get-session

### Request
```
{
	"user_pk": 2,
	"user_secret_key": "fffff..."(len 25),
	"session_pks": [10, ...]
}
```

### Response
```
{
	"sessions": [{
		"user_pk": 2,
		"session_pk": 10,
		"average_score": 60.4323,
		"problem": "",
		"handedness": "right",
		"date": "2016-07-15-13-04",
		"fire_type": 2,
		"shots": [{
			"angle": 243.3434,
			"score": 60.4323,
			"problem": "BREAKING WRIST DOWN",
			"split": 0,
			"pitch": [...],
			"trigger_hold": 1.294893,
			"handedness": "right",
			"trigger_pull": 0.49837,
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
		"problem": "",
		"handedness": "right",
		"date": "2016-07-15-13-04" OR "2016-07-15-13-04-59",
		"fire_type": 1, (1->live, 2->dry, 3->co2)
		"gun_type": 0, (0->pistol, 1->rifle)
		"firearm": {
			"make": "glock",
			"model": "19",
			"caliber": "9mm"
		},
		"shots": [{
			"angle": 243.3434,
			"score": 60.4323,
			"problem": "BREAKING WRIST DOWN",
			"split": 0,
			"pitch": [...],
			"trigger_hold": 1.294893,
			"handedness": "right",
			"trigger_pull": 0.49837,
			"bullseye": false,
			"yaw": [...]
		}]
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
