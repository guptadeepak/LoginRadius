LoginRadius Unified Social API
====
The LoginRadius Unified Social API is implemented as REST over HTTPS using GET/POST. Using API you can do social authentication, social Sharing and to capture user profile data from 25+ ID providers. All the resources have their own functions in the API and you can use features such as Social Account linking, Friend Invite, online/offline access, etc.

[Basic Profile Data](#BasicProfileData) - [Data Fields](#BPDataFields) | [JSON](#BPJSON)<br/>
[Extended Profile Data](#ExtendedProfileData) - [Data Fields](#EDataFields) | [JSON](#EJSON)<br/>
[Contacts/Friends](#Contacts) - [Data Fields](#ContactDataFields) | [JSON](#ContactJSON)<br/>
[Twitter Mentions](#Mentions) - [Data Fields](#MentionsDataFields) | [JSON](#MentionsJSON)<br/>
[Twitter Timeline](#Timeline) - [Data Fields](#TimelineDataFields) | [JSON](#TimelineJSON)<br/>
[Facebook Groups](#Groups) - [Data Fields](#GroupsDataFields) | [JSON](#GroupsJSON)<br/>
[Facebook Events](#Events) - [Data Fields](#EventsDataFields) | [JSON](#EventsJSON)<br/>
[Followed Companies (LinkedIn)](#Companies) -[Data Fields](#CompDataFields) | [JSON](#CompJSON)?<br/>
[Post Message (Facebook Wall, Twitter Tweet and LinkedIn Status)](#PostOnWall) -[Data Fields](#PostMDataFields) | [JSON](#PostMJSON)<br/>
[Posts and Write](#PostandWrite) - [Data Fields](#WriteDataFields) | [JSON](#WriteJSON)<br/>
[Send Messages (Twitter and LinkedIn)](#SendMessage) - [Data Fields](#SendMDataFields) | [JSON](#SendMJSON)<br/>


Social Authentication API
----
This API is use to authenticate users from their social network. The API would return the success response after authenticated from Social ID provider and also return the unique provider Identifier. The social authentication is supported by oAuth and OpenID protocols.

#### JSON Format
Name | Type | Read-Only |  Description
---- | ---- | --------- |    -----------
ID  | String |  ReadOnly| Social ID of the user
Provider	|String|	ReadOnly|	Social ID Provider of the user
Email->Type|	String|	ReadOnly|	Email type
Email->Value	|String	|ReadOnly|	Email of the user

#### Sample JSON

    {
          "ID":"00000010411351",
          “Provider”: “Facebook”,
          "Email":[
            {
                  "Type":"Primary",
          	  "Value":"example@example.com"
            }
            {
                  "Type":"Secondary",
                  "Value":"example@example.com"
            }
          ],
     }


User Profile API
---
This API is use to get the social profile data from user’s social account after authentication. The social profile will be retrieved via oAuth and OpenID protocols. The data would be normalized into LoginRadius’s JSON format.

The social profile data is divided into 2 groups:

#### <a name="BasicProfileData">a) Basic profile data</a>
   Basic profile data has limited profile fields such as FirstName, LastName, Date of Birth, Gender, etc. (see the list of all data fields below)
 
##### <a name="BPDataFields">Basic Profile Data - Data Fields</a>

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

##### <a name="BPJSON">Basic Profile Data - JSON Format</a>
	{
         	"ID":"100008695649009",
         	"Provider":"facebook",
         	"Prefix":”prefix”,
         	"FirstName":"James",
        	 "MiddleName":"",
         	"LastName":"Bond",
        	 "Suffix":”suffix”,
         	"FullName":"James Bond",
         	"NickName":null,
         	"ProfileName":"james.bond",
         	"BirthDate":"01/9/1969",
         	"Gender":"M",
         	"ImageUrl":"https://graph.facebook.com/100008695649009/picture?type=large",
         	"ThumbnailImageUrl":"https://graph.facebook.com/100008695649009/picture?type=square",
         	"Email":
         	[
           	{
             		"Type":"Primary",
             		"Value":"james007@email.com"
           	}
         	],
         	"Country":null,
         	"LocalCountry":"United States", 
         	"ProfileCountry":null
	}

#### <a name="ExtendedProfileData">b) Extended profile data</a>
Extended profile data has lots of information about the user’s social profile data like address, phone no, interest, education, positions, etc. (see the list of all data fields below)

##### <a name="EDataFields">Extended Profile Data - Data Fields</a>
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

##### <a name="EJSON">Extended Profile Data - JSON Format</a>
	{
       "ID":"00000010411351",
       “Provider”: “Facebook”,
       "Prefix":null,
       "FirstName":"George",
       "MiddleName":"Andy",
       "LastName":"Rodik",
       "Suffix":null,
       "FullName":"George Andy Rodik,
       "NickName":null,
       "ProfileName":"geogepr",
       "BirthDate":"08/11/1987",
       "Gender":"male",
       "Email":[
          {
                "Type":"Primary",
                "Value":"example@example.com"
          }
          {
       			"Type":"Secondary",
                "Value":"example@example.com"
          }
        ],
        "Country":'Germany',
        "TimeZone":"-7",
	}

<a name="Contacts">Contact/Network API</a>
---
This API is use to get contacts/network data for user’s social account. This API is only supported by oAuth ID providers such as Facebook, LinkedIn, Twitter, Google, Yahoo, MSN.

#### <a name="ContactDataFields">Contact/Friends- Data Fields</a>

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

#### <a name="ContactJSON">Contact/Friends- JSON Format</a>
	[
	{
		Name: "LoginRaduis",
		EmailID: "test@loginradius.com,
		PhoneNumber: "012121212121",
		ID: "87547124451",
		ProfileUrl: “http://www.facebook.com/87547854745”,
		ImageUrl: https://graph.facebook.com/87547854745/picture,
		Status: “This is my current status message”,
		Industry: “IT”,
		Country: ”US”,
		Gender: “Male”
	},
	]

User Activities API
----
This API is use to get the profile data from user’s activities from their social account. The API has variations based on the social network like Facebook will provide user’s Groups, posts and events; Twitter will provide Mentions, Timeline; LinkedIn will provide followed companies.

### <a name="Groups">a) Get user's Facebook Groups</a>

##### <a name="GroupsDataFields">Facebook Groups-Data Fields</a>
 Name	|Type|	Read-only	|Description
----|---|----|---
ID|	String|	ReadOnly|	Social ID of the user
Name|	String|	ReadOnly|	Group Name

##### <a name="GroupsJSON">Facebook Groups- JSON Format</a>
	[
 	{             
		ID: "325558927496078",
		Name: "Group Name1"
 	},
 	{
		ID: "189026094548878",
		Name: "Group Name2"
 	},
 	{
		ID: "187232004689444",
		Name: "Group Name3"
 	},
	]

###<a name="PostandWrite"> b) Posts and Write</a>

##### <a name="WriteDataFields">Posts and Write- Data Fields</a>
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

##### <a name="WriteJSON">Posts and Write- JSON Format</a>
	[
 	{
		ID: "100000834571501_440628135975002",
		Name: "John",
		Title: Philip,
		StartTime: "Date(1352187235000)/",
		UpdateTime: "Date(1352187235000)/",
		Message: "This is an awesome product.",
		Place: "Canada",
		Picture: https://fbcdn-photos-a.akamaihd.net/hphotos-ak-prn1/603971_498544000179346_1116425398_s.jpg",
		Likes: 5,
		Share: 1
 	}
	]

### <a name="Events">c) Get user's Facebook Events</a>

#####<a name="EventsDataFields"> Facebook Events- Data Fields</a>
Name|	Type|	Read-only|	Description
----|----|----|----
ID|	String|	ReadOnly|	ID of the Event
Name|	String|	ReadOnly|	Name of the Event
StartTime|	String|	ReadOnly|	Start time of the Event
RsvpStatus|	String|	ReadOnly|	Response status of the event
Location|	String|	ReadOnly|	Location of the Event

##### <a name="EventsJSON">Facebook Events- JSON Format</a>
	[
 	{
		ID: "325558927496078",
		Name: "A ski trip"
		StartTime:””,
		RsvpStatus:”attending”
		Location:”Edmonton”
 	},
	]

### <a name="Mentions">d) Get user's Twitter mentions</a>

##### <a name="MentionsDataFields">Twitter mentions- Data Fields</a>
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

##### <a name="MentionsJSON">Twitter mentions- JSON Format</a>
	[
 	{
		ID: "245396845445120000",
		Text: "Hi:-)",
		DateTime: "9/10/2012 10:42:21 PM",
		Likes: 0,
		Place: "Edmonton",
		Source: "<a href="http://twitter.com/download/iphone" rel="nofollow">Twitter for iPhone</a>",
		ImageUrl: http://www.cancer-fund.org/images/share/diy/img_sample.gif,
		LinkUrl: http://gimp.open-source-solution.org/manual/plug-in-sample-colorize.html
 	}
	]

### <a name="Timeline">e)Get user's Twitter TimeLine</a>

##### <a name="TimelineDataFields">Twitter TimeLine- Data Fields</a>
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

##### <a name="TimelineJSON">Twitter TimeLine- JSON Format</a>
	[
 	{
		ID: "245396845445120000",
		Text: "Hi:-)",
		DateTime: "9/10/2012 10:42:21 PM",
		Likes: 0,
		Place: "Edmonton",
		Source: "<a href="http://twitter.com/download/iphone" rel="nofollow">Twitter for iPhone</a>",
		ImageUrl: http://www.cancer-fund.org/images/share/diy/img_sample.gif,
		LinkUrl: http://gimp.open-source-solution.org/manual/plug-in-sample-colorize.html
 	}
	]

### <a name="Companies">f) Get companies followed in LinkedIn</a>

##### <a name="CompDataFields">followed companies (LinkedIn)- Data Fields</a>

Name|	Type|	Read-only|	Description
----|----|----|----
ID|	Array|	ReadOnly|	ID of the company
Name|	Array|	ReadOnly|	Name of the Company

##### <a name="CompJSON">followed companies (LinkedIn)- JSON Format</a>
	[
 	{ 
    	ID: 117342,
     	Name: "IOTAP"
 	},
 	{ 
     	ID: 14425,
     	Name: "Mirasoft"
 	} 
	]

Write Permission API
---
This API is use to write/post message on users social network. The API has variations based on the social network like Facebook can post data on user’s wall; Twitter can post direct message to user; LinkedIn can post direct message to user.

####<a name="SendMessage">a)Send Messages (Twitter and Linkedin)</a>

####<a name="SendMDataFields">Send Messages (Twitter and Linkedin)-Data Fields</a>
Name|	Type|	Read-only|	Description
---|---|---|---
To|	String|	 |	Contactlist Member Id that user get from user contact list
Subject|	String| |	 	Subject of the Message
Message|	String||	 	Message

####<a name="SendMJSON">Send Messages - Response</a>
True

### <a name="PostOnWall">b) Post Message (Facebook Wall, Twitter Tweet and LinkedIn Status)</a>

#####<a name="PostMDataFields"> Post Message - Data fields</a>

Name|	Type|Read-Only|Description
----|----|---- |----
To|	String	|| 	optional parameter if you want post status on a particular user wall then just pass memberid in to it work only in facebook
Title|	String||	 	optional parameter status message title
Url|	String||	 	optional parameter any url that you want post in status message
ImageUrl|	String	|| 	optional parameter any image url that you want post in status message
Status|	String||	 	your status message
Caption|	String||	 	optional parameter caption that you want post in status message
Description|	String||	 	optional parameter caption that you want post in status message

##### <a name="PostMJSON">Post Message - Resposne</a>
true
