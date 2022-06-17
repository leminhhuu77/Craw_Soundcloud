# Using 2 ways to crawl data from SoundCloud
> We use concurrency to send multiple request in order to run program more faster but it will be lag when running parse_html as it must open multi-tab chrome
### Get data using SoundCloud API
> we have a list urls of 50 top tracks, it's a system-playlists which are automatically created by SoundCloud, not belonging to any user (we put it in **url_entry** folder)\
###### Prerequisite
Firstly, we send sequence *resolve request* to these top URL to get a lists of *track_id*.
Secondly, we will send request with *tracks* endpoint for each *track_id* to get detail infor of each track and it also contains *user* property, which has *id* of user belonging to that track and we will have a list of *user_id*
###### Get detail users
Then sending request with *users* endpoint and we write all detail information of users to CSV file

###### How to get a tracks and playlists
> Idea: We will loop through each users above and get their playlists and tracks

For playlists, we use */users/playlists* endpoint
And using */users/tracks* endpoint for crawling tracks of users

### Get data using Parse HTML
- We use selenium library so we download chromedriver.exe our version is 95.0.4638.69 
- If you use another version please download at https://sites.google.com/a/chromium.org/chromedriver/downloads
