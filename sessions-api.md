# Sessions API

All of the following API calls require  
`user_pk`: "foo",  
`user_secret_key`: "fff...",
`secret_key`: "man..."

Additional parameters listed below.

## /post-session
```
phone_type "ios" \ "android"  
device_info`: "iPhone 6"  
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
  time_stamp: (int) (seconds - not milliseconds - since 1970)
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
