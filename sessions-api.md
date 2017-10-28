# Sessions API

All of the following API calls require  
`user_pk`: "foo",  
`user_secret_key`: "fff...",  
`secret_key`: "man..."

Additional parameters listed below.

## /post-session
`gun_type` maps (0: pistol), (1: rifle)  
`fire_type` maps (1: live), (2: dry), (3: co2)  
`date` takes the number of seconds (not milliseconds) since 1970  
`gun.make`, `gun.model`, `gun.caliber` are empty strings if no gun selected  
```
phone_type "ios" \ "android"  
device_info`: (string)   
sessions: [{
  drill_id: (int)  
  drill_name: (string)  
  score_bars:  (int)  
  time_bars: (int)  
  time_display: (string)  
  deleted: (boolean)  
  firearm: {
    make: (string)  
    model: (string)  
  }  
  time_stamp: (int)
  stamp: (string)
  shots: [{
    score: (decimal)  
    angle: (decimal)  
    problem: (string)  
    pitch: (array of decimals)  
    yaw: (array of decimals)  
    bullseye: (boolean)  
    trigger_hold: (decimal)  
    trigger_pull: (decimal)  
    deleted: (boolean)  
    shot_index: (int)  
    hold_index: (int)  
    pull_index: (int)  
  }]
}]
``` 

## /get-session
`session_pks`: (list of ints)

## /get-all-sessions

## /get-paginated-sessions
Returns batches of 50 sessions, ordered by descending date.
For example, page=0 would return the 50 most recent sessions.
`page`: (int)

## /get-session-summaries
`last_synced_token`: (string)

## /get-other-user-summary
`requested_user_pk`: (int)
