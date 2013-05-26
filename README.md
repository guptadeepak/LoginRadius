LoginRadius Unified Social API
====
The LoginRadius Unified Social API aggregates the functionality of 30 social networks into one. It is a REST API over HTTPS and uses GET/POST requests for implementation. The Get request is use to fetch the data from different social networks and Post request is use to write/push the data into different social networks. 

Features of the API:
--------------------

 - Social Authentication from social networks
 - Fetch user profile data such as profile information, status messages, activities, events, group, companies, etc.
 - Invite friends from social network using Contact/Friends API and Write API
 - Update status message for user's social network

Social Authentication and User profile data API
----
This API is use to authenticate users from their social network and fetch the user profile data. The API returns success response after authentication from Social networks and also returns user profile data. The social authentication is supported by oAuth (v1 and v2) and OpenID protocols. 

> Returns normalized user profile data set into aggregates LoginRadius data format.

#### API specification

API Endpoint| https://hub.loginradius.com/UserProfile.ashx?apisecrete={SECRET}&token={TOKEN} 
 ---------   |   ----- 
**API help Endpoint** | https://hub.loginradius.com/userprofile.ashx/help
**Request Type**     | HTTP Get Request
**Input Parameters**      | LoginRadius API Secret, User profile session Token
**Error Codes** | 403 Forbidden : Your API secret or token is invalid
**Response** | JSON

The social profile data is divided into 2 groups:

#### a) Basic profile data
   Basic profile data has limited profile fields such as FirstName, LastName, Date of Birth, Gender, etc. (see the list of all data fields below)
 
##### JSON Format

Name	|Type	|Read-only	|Description
------ | ---- | -------- | ---------
ID	|String	|ReadOnly	|Social ID of the user
Provider|	String|	ReadOnly|	Social ID Provider of the user
Prefix |	String	|ReadOnly	|Prefix of the user
FirstName|	String|	ReadOnly	|First Name of the user
MiddleName|	String|	ReadOnly|	Middle Name of the user
LastName|	String|	ReadOnly|	Last Name of the user
Suffix|	String|	ReadOnly|	Suffix of the user
FullName|	String|	ReadOnly|	Full Name of the user
NickName|	String|	ReadOnly|	Nick Name of the user
ProfileName|	String|	ReadOnly|	Profile Name of the user
BirthDate|	String|	ReadOnly|	Birthdate of the user
Gender|	String|	ReadOnly|	Gender of the user
Website|	String	|ReadOnly	|Website of the user
Email->Type|	String|	ReadOnly|	Email type
Email->Value|	String|	ReadOnly|	Email of the user
Country|	String|	ReadOnly|	Country of the user
ImageUrl|	String|	ReadOnly|	Image Url of the user

#### b) Extended profile data
Extended profile data has lots of information about the user’s social profile data like address, phone no, interest, education, positions, etc. (see the list of all data fields below)

##### JSON Format
Name|	Type|	Read-only|	Description
-----|-----|------|------
ID|	String|	ReadOnly|	Social ID of the user
Provider|	String|	ReadOnly|	Social ID Provider of the user
Prefix|	String|	ReadOnly|	Prefix of the user
FirstName|	String|	ReadOnly|	First Name of the user
MiddleName|	String|	ReadOnly|	Middle Name of the user
LastName|	String|	ReadOnly|	Last Name of the user
Suffix|	String|	ReadOnly|	Suffix of the user
FullName|	String|	ReadOnly|	Full Name of the user
NickName|	String|	ReadOnly|	Nick Name of the user
ProfileName|	String|	ReadOnly|	Profile Name of the user
BirthDate|	String|	ReadOnly|	Birthdate of the user
Gender|	String|	ReadOnly|	Gender of the user
Website|	String|	ReadOnly|	Website of the user
Email->Type|	String|	ReadOnly|	Email type
Email->Value|	String|	ReadOnly|	Email of the user
Country|	String|	ReadOnly|	Country of the user
ThumbnailImageUrl|	String|	ReadOnly|	Thumbnail Image Url of the user social avatar
ImageUrl|	String|	ReadOnly|	Image Url of the user
Favicon|	String|	ReadOnly|	Favicon of the user
ProfileUrl|	String|	ReadOnly|	Profile Url of the user
HomeTown|	String|	ReadOnly|	Home Town of the user
State|	String|	ReadOnly|	State of the user
City|	String|	ReadOnly|	City of the user
Industry|	String|	ReadOnly|	Industry of the user
About|	String|	ReadOnly|	Bio of the user
TimeZone|	String|	ReadOnly|	Timezone of the user
LocalLanguage|	String|	ReadOnly|	LocalLanguage of the user
Verified|	String|	ReadOnly|	Verified status of the user
UpdatedTime|	String|	ReadOnly|	Updated time of the user
Positions|	Array|	ReadOnly|	Job positions of the user
Educations|	Array|	ReadOnly|	Education details of the user
Language|	String|	ReadOnly|	Language of the user
PhoneNumbers|	Array|	ReadOnly|	Phone Numbers of the user
IMAccounts|	Array|	ReadOnly|	IM Account usernames  of the user
Addresses|	Array|	ReadOnly|	Addresses of the user
MainAddress|	String|	ReadOnly|	MainAddress of the user
Created|	String|	ReadOnly|	Date of creation of the user account
LocalCity|	String|	ReadOnly|	LocalCity of the user
ProfileCity|	String|	ReadOnly|	ProfileCity of the user
LocalCountry|	String|	ReadOnly|	LocalCountry of the user
ProfileCountry|	String|	ReadOnly|	ProfileCountry of the user
RelationshipStatus|	String|	ReadOnly|	RelationshipStatus of the user
Quota|	String|	ReadOnly|	Quote of the user
InterestedIn|	String|	ReadOnly|	InterestedIn of the user
Interests|	Array|	ReadOnly|	Interests of the user
Religion|	String|	ReadOnly|	Religion of the user
Political|	String|	ReadOnly|	Political Views of the user
Sports|	Array|	ReadOnly|	Sports of the user
InspirationalPeople|	Array|	ReadOnly|	InspirationalPeople of the user
HttpsImageUrl|	String|	ReadOnly|	HttpsImageUrl of the user
FollowersCount|	Integer|	ReadOnly|	Followers Count of the user
FriendsCount|	Integer|	ReadOnly|	Friends Count of the user
TotalStatusesCount|	Integer|	ReadOnly|	Total Statuses Count of the user
Associations|	String|	ReadOnly|	A short-form textarea enumerating the Associations a member has
NumRecommenders|	Integer|	ReadOnly|	The number of recommendations the member has
Honors|	String|	ReadOnly|	A short-form text area describing what Honors the member may have
Skills|	Array|	ReadOnly|	Individual skills are structured objects returned as part of profile.
CurrentStatus|	String|	ReadOnly|	the member's current status, if set the timestamp, in milliseconds, when the member's status was last set
Certifications|	Array|	ReadOnly|	Individual certifications are structured objects returned as part of profile
Courses|	Array|	ReadOnly|	Course entities of the user
Volunteer|	String|	ReadOnly|	Volunteer entities of the user
RecommendationsReceived|	Array|	ReadOnly|	Recommendations received by the user
Languages|	Array|	ReadOnly|	Languages of the user
Hireable|	Bool|	ReadOnly|	Mention user is Hireable or not
Age|	Integer|	ReadOnly|	Age of the user
Patents|	String|	ReadOnly|	Patents information of the user
FavoriteThings|	String|	ReadOnly|	Favorite things of the user
ProfessionalHeadline|	String|	ReadOnly|	Professional Headline of the user
ProviderAccessCredential|	Object|	ReadOnly|	Provider Access token

> **Detailed information on user profile data fields and JSON:**

> Basic User profile data - [Data Fields][1] | [JSON][2]

> Extended User profile data - [Data Fields][3] | [JSON][4]

Contact/Network API
---
The API is use to get contacts/network data for user’s social account. This API is supported by oAuth ID providers such as Facebook, LinkedIn, Twitter, Google, Yahoo and MSN.

#### API specification

API Endpoint| https://hub.loginradius.com/contacts/{SECRET}/{TOKEN}
------------|--------------------
**API help Endpoint**| https://hub.loginradius.com/contacts/help
**Request Type**|	HTTP Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

#### Data Fields

Name|	Type|	Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	Social ID of the user
Name|	String|	ReadOnly|	Name of the Friend/Follower/Connnection
EmailID|	String|	ReadOnly|	E-MailId of the Friend
PhoneNumber|	String|	ReadOnly|	Phone no of the Friend
ProfileUrl|	String|	ReadOnly|	profile url of the Friend
ImageUrl|	String|	ReadOnly|	image Url of the Friend
Status|	String|	ReadOnly|	Current Status message  of the Friend
Industry|	String|	ReadOnly|	Industry of the Friend
Country|	String|	ReadOnly|	Country of the Friend
Gender|	String|	ReadOnly|	Gender of the Friend

> **Detailed information:** [Data Fields][5] | [JSON][6]

User Activities API
----
The API is use to get the profile data from user’s activities from their social account. The API has variations based on the social network like Facebook will provide user’s Groups, posts and events; Twitter will provide Mentions, Timeline; LinkedIn will provide followed companies.

### a) Get user's Facebook Groups
##### API specification

API Endpoint|	https://hub.loginradius.com/GetGroups/{SECRET}/{TOKEN}
------------|    ----
**API help Endpoint**|	https://hub.loginradius.com/GetGroups/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Fields
 Name	|Type|	Read-only	|Description
----|---|----|---
ID|	String|	ReadOnly|	Social ID of the user
Name|	String|	ReadOnly|	Group Name


### b) Get user's Facebook Posts
API Endpoint|https://hub.loginradius.com/GetPosts/{SECRET}/{TOKEN}
----|----
**API help Endpoint**|	https://hub.loginradius.com/GetPosts/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Fields
Name|	Type|	Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	ID of the post
Name|	String|	ReadOnly|	Name of the user who has posted
Title|	String|	ReadOnly|	Title of the post
StartTime|	Integer|	ReadOnly|	Start Time of the post
UpdateTime|	String|	ReadOnly|	Update time of the post
Message|	String|	ReadOnly|	Message of the post
Place|	String|	ReadOnly|	Place of the post
Picture|	String|	ReadOnly|	Url of the picture mentioned in the post
Likes|	Integer|	ReadOnly|	Number of likes of the post
Share|	String|	ReadOnly|	Number of shares of the post

### c) Get user's Facebook Events

API Endpoint|	https://hub.loginradius.com/GetEvents/{SECRET}/{TOKEN}
----| ----
**API help Endpoin**|	https://hub.loginradius.com/GetEvents/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Format
Name|	Type|	Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	ID of the Event
Name|	String|	ReadOnly|	Name of the Event
StartTime|	String|	ReadOnly|	Start time of the Event
RsvpStatus|	String|	ReadOnly|	Response status of the event
Location|	String|	ReadOnly|	Location of the Event

### d) Get user's Twitter mentions

API Endpoint|	https://hub.loginradius.com/status/mentions/{SECRET}/{TOKEN}
----|----
**API help Endpoint**	|https://hub.loginradius.com/status/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token,URI  type of request like Mentinons
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Format
Name|	Type|	Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	ID of the mention
Text|	String|	ReadOnly|	Text of the mention
DateTime|	String|	ReadOnly|	Date and Time of the mention
Likes|	Integer|	ReadOnly|	Likes of the mention
Place|	String|	ReadOnly|	Place of the mention
Source|	String	|ReadOnly	Source of the mention
ImageUrl|	String|	ReadOnly|	ImageUrl of the image in the mention
LinkUrl|	String|	ReadOnly|	LinkUrl of the mention

### e) Get user's Twitter TimeLine

API Endpoint	|https://hub.loginradius.com/status/timeline/{SECRET}/{TOKEN}
----|----
**API help Endpoint**|	https://hub.loginradius.com/status/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token,URI  type of request like Timeline
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Format
Name|	Type	|Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	ID of the Timeline
Text|	String|	ReadOnly|	Status of the Timeline
DateTime|	String|	ReadOnly|	Date of the Timeline
Likes|	String|	ReadOnly|	No of like for the Timeline
Place|	String|	ReadOnly|	Location of the Timeline
Source|	String|	ReadOnly|	Source of the Timeline
ImageURL|	String|	ReadOnly|	Image URL of the Timeline
LinkURL|	String|	ReadOnly|	Link URL of the Timeline

### f) Get companies followed in LinkedIn

API Endpoint|	https://hub.loginradius.com/GetCompany/{SECRET}/{TOKEN}
----|----
**API help Endpoint**|	https://hub.loginradius.com/GetCompany/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	JSON

##### Data Fields

Name|	Type|	Read-only|	Description
----|----|----|----
ID|	Array|	ReadOnly|	ID of the company
Name|	Array|	ReadOnly|	Name of the Company


Write Permission API
---
The API is use to write/post message on users social network. The API has variations based on the social network like Facebook can post data on user’s wall; Twitter can post direct message to user; LinkedIn can post direct message to user.

####API specification:

API Endpoint |	https://hub.loginradius.com/directmessage/{SECRET}/{TOKEN}?sendto={SENDTO}&subject={SUBJECT}&message={MESSAGE}
--- | ---
**API help Endpoint**|	https://hub.loginradius.com/directmessage/help
**Request Type**|	Http Get Request
**Input Parameters**|	LoginRadius API Secret, User profile session Token
**Error Codes**|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
**Response**|	Boolean

#### Parameters Format

Name|	Type|	Read-only|	Description
---|---|---|---
To|	String|	 |	Contactlist Member Id that user get from user contact list
Subject|	String| |	 	Subject of the Message
Message|	String||	 	Message

#### Response
True/False

### a) Post status to facebook's wall

API Endpoint|	https://hub.loginradius.com/status/update/{SECRET}/{TOKEN}?to={to}&title={title}&url={url}&imageurl={imageurl}&status={status}&caption=caption}&description={description}
---|---
API help Endpoint|	https://hub.loginradius.com/status/help
Request Type|	Http Get Request
Input Parameters|LoginRadius API Secret  **User profile session Token (to)**: [optional parameter] if you want to  post status on a particular user wall then just pass member id in to it work only in Facebook title :- [optional parameter] status message **title url**:- [optional parameter] any url that you want post in status message **imageurl** :- [optional parameter] any image url that you want post in status message **status** :- your status message **caption** : [optional parameter] caption that you want post in status message **description** :- [optional parameter] description  that you want post in status message **Note**: - If you want post url or imageurl then all parameter are compulsory.
Error Codes|	403 Forbidden : Your api secret or  token is invalid 401 unauthorized : Your api key secret not exists in our system
Response|	Boolean

#### Parameters Format:

Name|	Type|Read-Only|Description
----|----|---- |----
To|	String	|| 	optional parameter if you want post status on a particular user wall then just pass memberid in to it work only in facebook
Title|	String||	 	optional parameter status message title
Url|	String||	 	optional parameter any url that you want post in status message
ImageUrl|	String	|| 	optional parameter any image url that you want post in status message
Status|	String||	 	your status message
Caption|	String||	 	optional parameter caption that you want post in status message
Description|	String||	 	optional parameter caption that you want post in status message

#### Response
true/false

  [1]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Basic%20Profile%20Data%20-%20Data%20fields
  [2]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Basic%20Profile%20Data%20-%20Json
  [3]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Extended%20profile%20data%20-%20Data%20fields
  [4]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Extended%20profile%20data%20-%20Json
  [5]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Contacts/Friends%20-%20Data%20Fields
  [6]: http://support.loginradius.com/customer/portal/articles/1158295-loginradius-api---json-and-data-tables#Contacts/Friends%20-%20JSON
