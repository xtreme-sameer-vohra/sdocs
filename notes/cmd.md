
# Commands

## General
- switch user
 `su some-user-name`

- execute previous command
`!!` 

- List file system mounts
	`findmnt`	

- Filter results
	`awk '/search_pattern/ {print $1 $2}'
		$1 refers to column 1, starting from index 0
## Search
- Find File
	`find path_to_search -name "*.txt" `
	
  - `-not` to inverse results
  - `-maxdepth some_int` to limit depth of search
  - `-size +1M` find files larger than 1 MB
  - `-type f|d` find files or directories
  - `-exec grep -n -i "foo" 

- Grep
	`grep -i "search text" path_to_search
	- `-n` print line number of match
	

Search within File



	


## Notes
- .deb packages are for debian/ubuntu
- .rpm packages are for rhel/suse