Here are storage paths for some other common web browsers:

**Firefox:** “%USERPROFILE%\AppData\Roaming\Mozilla\Firefox\Profiles\”

**Edge:** “%USERPROFILE%\AppData\Local\Microsoft\Edge\User Data\”

**Opera:** “%USERPROFILE%\AppData\Roaming\Opera Software\Opera Stable”

## Some common browser artifacts are:

- Search history
- Visited Websites
- Downloads
- Cookies
- Cache
- Bookmarks
- Favicons
- Sessions
- Form history
- Thumbnails
- Extensions

## Search History

Search history refers to information of any search terms used. This information is important because it can uncover users' intentions on by showing the exact URLs that the user typed in the search bar. The search history is saved in the SQLite database named “History” and is under the “keyword_search_term” table.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/Browser-Forensics/3-+Browser+Artifacts/1.png)

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\History**” on Chrome

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\places.sqlite**” on Firefox

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\History**” on Edge

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\History**” on Opera

**Note:** It is worth mentioning that Microsoft Edge and Opera have the same path and database names as Chrome. This is because these browsers are all Chromium based meaning they have same backend engine.

## Visited Websites

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\History**” on Chrome

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\places.sqlite**” on Firefox

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\History**” on Edge

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\History**” on Opera

## Downloads

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\History**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\places.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\History**” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\History**” on Opera.

## Cookies

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Network\Cookies**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\cookies.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Network\Cookies**” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Network\Cookies**” on Opera.

## Cache

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Cache\Cache_Data**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\webappsstore.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Cache\Cache_Data**” on Edge,

“**C:\Users\[username]\AppData\Local\Opera Software\Opera Stable\Cache\Cache_Data**” on Opera.

**Note:** Only Opera cache is saved under “\Appdata\Local\*”, the rest of Opera data is stored under “\Appdata\Roaming\”

## Bookmarks

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Bookmarks**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\places.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Bookmarks**”  on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Bookmarks**”  on Opera.

## Favicons

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Favicons**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\favicons.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Favicons**” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Favicons**” on Opera.

## Session file

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Sessions\***” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\sessionstore.jsonlz4**” on Firefox (1)

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\sessionstore-backups\***” on Firefox (2)

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Sessions\***” on Edge

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Sessions\***” on Opera

## Form History

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Web Data**” on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\formhistory.sqlite**” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Web Data**” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Web Data**” on Opera.

## Thumbnails

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Top Sites**”on Chrome,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Top Sites**” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Top Sites**” on Opera.

## Extensions

“**C:\Users\[username]\AppData\Local\Google\Chrome\User Data\Default\Extensions\{randomfoldername}\***”on Chrome,

“**C:\Users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[randomfoldername]\extensions\***” on Firefox,

“**C:\Users\[username]\AppData\Local\Microsoft\Edge\User Data\Default\Extensions\{randomfoldername}\***” on Edge,

“**C:\Users\[username]\AppData\Roaming\Opera Software\Opera Stable\Extensions\{randomfoldername}\***” on Opera.

