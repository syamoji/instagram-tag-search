# This is tag search gem for Instagram.

### Download data
- page url
- timestamp
- count of comments
- count of likes
- caption
- tags
- owner id

## How to use
```ruby
# load gem library
require 'instagram-tag-search'

# make a instance
# tag_name : tag, get_number : number of download posts
instagramData = InstagramData.new(tag_name: '岸和田', get_number: 10)

# get data
# use getInstagramData method
instagramData.getInstagramData

# download data information
instagramData.instagram_data
# page url           instagramData.instagram_data[0][:pageUrl]
# timestamp          instagramData.instagram_data[0][:timestamp]
# count of comments  instagramData.instagram_data[0][:commentCount]
# count of likes     instagramData.instagram_data[0][:likeCount]
# caption            instagramData.instagram_data[0][:caption]
# owner id           instagramData.instagram_data[0][:userId]
# tags               instagramData.instagram_data[0][:tags]

# If you want to save to CSV file, use writeToCSV method.
# first argument is instagramdata
# second argument is csv filename
# if you do not specify second argument, 
# save file name is like this: getInstagramData_201807222200.csv
instagramData.writeToCSV(instagramData.instagram_data)

# If you want to view csv file with Excel,
# you have to convert character encode to sjis.
# CSV file save to [[filename]]_sjis.csv
# [restriction] some character convert to '?'.
# For example, emoji, like this. 😍 -> ?
instagramData.convertCSVtoSJIS
```
