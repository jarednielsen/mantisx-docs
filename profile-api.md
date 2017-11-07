# Profile API

All of the following API calls require 
`user_pk`: "foo",  
`user_secret_key`: "fff...",  

Additional parameters listed below.

## /update-profile-settings
These are all optional fields. For example, to change only privacy, send {"privacy": "private"}.  
`email`   
`username`  
`password`  
`privacy`: "private" \ "public

## /update-profile-pic
This one is different. JavaScript uses FormData to pass in an image.
Do the iOS/Android equivalent of this:
```
let formData = new FormData();
formData.append("profile_pic", file);
formData.append("user_pk", user_pk);
formData.append("user_secret_key", user_secret_key);
$.ajax({
	url: config.URLs.update_profile_pic,
	type: 'POST',
	processData: false,
	contentType: false,
	dataType: 'json',
	data: formData
})
```

## /update-address
`ship_to_name`  
`address`  
`city`  
`state`  
`zip_code`  

## /update-basic-training
Pass in the basic training date as a float, epochs since 1970 in UTC time. (datetime.timestamp() in Python).
If it is not set, pass `null`.  
`basic_training_challenge`: 3,  
`basic_training_completed`: 1510064658.626689

