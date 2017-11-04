# Mantis Groups API

## /get-groups

`user_pk`: "foo",  
`user_secret_key`: ""  

Returns:  
`groups`: an array of groups the user belongs to  
Group -  
`pk`: the group id  
`name`: the name of the group  
`latest_sessions`: an array of the last five sessions  
`best_sessions`: an array of the best sessions in the last 7 days  
`members`: an array of users, each user contains summary stats (`weekly_shot_count`, `weekly_benchmark_score`)
`admin`: true / false
`pending_member_requests`: an array of dicts containing `id`, `username`. Only appears if user is admin.
`settings`: a dict containing  
   `privacy`: "open" / "closed",  
   `visibility`: "visible" / "hidden" 

## /public-groups
Returns:
`groups`: an array of all public groups  

## /search-groups

`user_pk`: "foo",  
`user_secret_key`: "",  
`search_term`: "mantis"

## /create-group

`user_pk`: "foo",  
`user_secret_key`: "fff..."  
`name`: "mantis_group",  
`privacy`: "open" / "closed"  

## /join-group, /leave-group, /delete-group

`user_pk`: 123,  
`user_secret_key`: "fff...",  
`group_pk`: 45  

## /edit-group

`user_pk`: 123,  
`user_secret_key`: "fff...",  
`privacy`: "open" / "closed",  
`visibility`: "visible" / "hidden",  
`name`: "new_name"

## /add-to-group, /delete-from-group

`user_pk`: 123,  
`user_secret_key`: "fff...",  
`group_pk`: 45,  
`admin`: true / false, (make this new group member an admin?)  
`user_to_add_pk` / `user_to_delete_pk`: 234   
   
