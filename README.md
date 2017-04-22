# Easy Allies community project #
## Quotes made by Chad ##
### Description ###
The purpose is to store all the quotes made by the EZA chat during live streams on Twitch. The ability to receive all the chat messages is limited by the archive storage time limit, and the future of the Twitch Rechat API.

### Software platform ###
As of yet not decided.
The architecture must though (at least) consist of three server instances:
- Extraction; e.g. Python or NodeJS
- Database; e.g. MongoDB or MariaDB
- Web
    + Front-end; AngularJS, React, Ember
    + Back-end; Python or NodeJS

### Extraction process ###
When a new VOD is available (detected by daily API checks), the process of extracting quotes will initiate. The thoughtout process is as now the following:
1. Set of quote extracting by a web hook
2. Extract quotes using a regular expression pattern
3. Store *only* the quotes in a suitable database, which solution? A NoSQL-based, or SQL-based.

### Availability of the quotes ###
The quotes will be available through a web page. The VOD timestamp of the chat quote is used to provide a Twitch VOD preview, imagine a list of previews and the corresponding quote. Though this will rely on that the quote timestamp and VOD preview timestamp is exactly relative, in terms of its creation and relevance. Though this can be dirty solved by setting the VOD preview timestamp back with e.g. 5 seconds.

The web page will provide the following functions:
- Quote of the day
- Searching
    + By keyword
    + By VOD
    + Within a time span
    All above can be freely combined
- VOD preview in relation of the chat quote (though limited by the time availability limit, perhaps a manual link to YouTube archive in the future?)

### Use of APIs ###
- Twitch API; https://dev.twitch.tv/

### Project revision history ###
- 0.1.0 (2017-04-22)
    + Initial description