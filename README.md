# API of Spaces.ru

## Available methods:

- Authorization
	- [`login`](#login)
	- [`logout`](#logout)
	- [`check`](#check)
	- [`getOAuthLinks`](#getoauthlinks)

## Other:

- [`Response Codes`](#response-codes)
- [`WebSocket Token`](#websocket-token)
- [`SID`](#sid)
- [`CK`](#ck)

## Special HTTP headers:

| Params | Value | Description |
|-|-|-|
| `Content-Type` | `multipart/form-data` | Used to send data ([Wikipedia](https://ru.wikipedia.org/wiki/Multipart/form-data)) |
| `X-Proxy` | `spaces` | Special header (Required) |
| `Cookie` | `json=1` or `json=1; sid=`[SID](#sid) | Required to get JSON. Also used as GET parameter `https://spcs.me/?json=1` |

## login:
### POST `https://spcs.me/neoapi/session`

| Params | Value | Description |
|-|-|-|
| `login` | `string` | Nickname (3-15), E-mail or phone number |
| `password` | `string` | Username password (6-20) |
| `method` | `login` | Authorization method |
| `rid` | `APA91bFwsPw4clF4y0RHWtg6Y4fC6UnxcrmZYLiko_ifv-8g7Qi-5koV4GRaVax5zMWTMke9eUF-MzHhzdM9iYQEFDff5lnHuMlwIl-zNAu4MfYS4PlL0j8C28XZgNJmQbRSd1BE4eSW` | API Token (Required) |

### Response Data:

``` JSON
{
	"css_files": [],
	"time": 1539255488,
	"config": {
		"large_display_min_width": 480,
		"thumbs": {
			"baseurl": "http://tsx.spaces.ru/"
		},
		"TOUCH_INTERFACE_SCREEN_WIDTH": 320,
		"icons": {
			"baseurl": "https://spac.me/i/"
		}
	},
	"attributes": {
		"channel_id": "2704a220cb801792d410b05d37ce6c37",
		"sid": "6693985458435384",
		"isAutoreg": 0,
		"avatar": "https://ts01.spac.me/tpic/5a349533ff6e12b04bd8d60c1d1c5df3/109940268.p.41.40.0.20020970.jpg?1450357123",
		"name": "AnomaIy",
		"CK": "5384",
		"nid": 22003524,
		"mysite_link": "https://spcs.me/mysite/?name=AnomaIy&amp;sid=6693985458435384",
		"online_status": {
			"system": 0,
			"alt": "(ON)",
			"last_time": 1539255488,
			"off_img": "man_off.gif",
			"is_online": 1,
			"no_link": 1,
			"on_img": "man_on.gif",
			"id": "22003524"
		},
		"mailTbNm": 0
	},
	"t": 0.236968040466309,
	"code": "00000"
}
```

| Key | Value | Description |
|-|-|-|
| `channel_id` | `string` | [WebSocket Token](#websocket-token) |
| `sid` | `string` | [SID](#sid) |
| `avatar` | `url` | Thumbnail avatar (40x40) |
| `name` | `string` | Nickname |
| `CK` | `string` | Last four digits of [SID](#sid) ([CK](#ck)) |
| `nid` | `int` | User id |
| `code` | `int` | [Response Codes](#response-codes) |

## logout:
### POST `https://spcs.me/neoapi/session`

| Params | Value | Description |
|-|-|-|
| `method` | `logout` | Logout method |
| `rid` | `APA91bFwsPw4clF4y0RHWtg6Y4fC6UnxcrmZYLiko_ifv-8g7Qi-5koV4GRaVax5zMWTMke9eUF-MzHhzdM9iYQEFDff5lnHuMlwIl-zNAu4MfYS4PlL0j8C28XZgNJmQbRSd1BE4eSW` | API Token (Required) |

### Response Data:

``` JSON
{
	"css_files": [],
	"time": 1539684953,
	"config": {
		"large_display_min_width": 480,
		"thumbs": {
			"baseurl": "http://tsx.spaces.ru/"
		},
		"TOUCH_INTERFACE_SCREEN_WIDTH": 320,
		"icons": {
			"baseurl": "https://spac.me/i/"
		}
	},
	"t": 0.189088821411133,
	"code": "00000"
}
```

| Key | Value | Description |
|-|-|-|
| `code` | `int` | [Response Codes](#response-codes) |

## check:
### POST `https://spcs.me/neoapi/session`

| Params | Value | Description |
|-|-|-|
| `method` | `check` | Check session method |
| `rid` | `APA91bFwsPw4clF4y0RHWtg6Y4fC6UnxcrmZYLiko_ifv-8g7Qi-5koV4GRaVax5zMWTMke9eUF-MzHhzdM9iYQEFDff5lnHuMlwIl-zNAu4MfYS4PlL0j8C28XZgNJmQbRSd1BE4eSW` | API Token (Required) |

### Response Data:

``` JSON
{
	"css_files": [],
	"time": 1539255488,
	"config": {
		"large_display_min_width": 480,
		"thumbs": {
			"baseurl": "http://tsx.spaces.ru/"
		},
		"TOUCH_INTERFACE_SCREEN_WIDTH": 320,
		"icons": {
			"baseurl": "https://spac.me/i/"
		}
	},
	"attributes": {
		"channel_id": "2704a220cb801792d410b05d37ce6c37",
		"sid": "6693985458435384",
		"isAutoreg": 0,
		"avatar": "https://ts01.spac.me/tpic/5a349533ff6e12b04bd8d60c1d1c5df3/109940268.p.41.40.0.20020970.jpg?1450357123",
		"name": "AnomaIy",
		"CK": "5384",
		"nid": 22003524,
		"mysite_link": "https://spcs.me/mysite/?name=AnomaIy&amp;sid=6693985458435384",
		"online_status": {
			"system": 0,
			"alt": "(ON)",
			"last_time": 1539255488,
			"off_img": "man_off.gif",
			"is_online": 1,
			"no_link": 1,
			"on_img": "man_on.gif",
			"id": "22003524"
		},
		"mailTbNm": 0
	},
	"t": 0.236968040466309,
	"code": "00000"
}
```

| Key | Value | Description |
|-|-|-|
| `channel_id` | `string` | [WebSocket Token](#websocket-token) |
| `sid` | `string` | [SID](#sid) |
| `avatar` | `url` | Thumbnail avatar (40x40) |
| `name` | `string` | Nickname |
| `CK` | `string` | Last four digits of [SID](#sid) ([CK](#ck)) |
| `nid` | `int` | User id |
| `code` | `int` | [Response Codes](#response-codes) |

## getOAuthLinks:
### POST `https://spcs.me/neoapi/common`

| Params | Value | Description |
|-|-|-|
| `method` | `getOAuthLinks` | Fetch social Auth urls |

### Response Data:

``` JSON
{
	"css_files": [],
	"time": 1539685368,
	"config": {
		"large_display_min_width": 480,
		"thumbs": {
			"baseurl": "http://tsx.spaces.ru/"
		},
		"TOUCH_INTERFACE_SCREEN_WIDTH": 320,
		"icons": {
			"baseurl": "https://spac.me/i/"
		}
	},
	"urls": {
		"ok_login_URL": "https://spcs.me/oauth/?CK=4434&amp;P=2&amp;redirect_uri=registration/external/&amp;sid=0837524164004434&amp;state=CK:4434,Link_id:0,S:2,sid:0837524164004434,permissions_granted:VALUABLE_ACCESS;GET_EMAIL",
		"vk_login_URL": "https://spcs.me/oauth/?CK=4434&amp;P=1&amp;redirect_uri=registration/external/&amp;sid=0837524164004434&amp;state=CK:4434,Link_id:0,S:1,sid:0837524164004434",
		"facebook_login_URL": "https://spcs.me/oauth/?CK=4434&amp;P=4&amp;redirect_uri=registration/external/&amp;sid=0837524164004434&amp;state=CK:4434,Link_id:0,S:4,sid:0837524164004434",
		"mail_ru_login_URL": "https://spcs.me/oauth/?CK=4434&amp;P=3&amp;redirect_uri=registration/external/&amp;sid=0837524164004434&amp;state=CK:4434,Link_id:0,S:3,sid:0837524164004434"
	},
	"t": 0.00297307968139648,
	"code": "00000"
}
```

| Key | Value | Description |
|-|-|-|
| `ok_login_URL` | `url` | [Odnoklassniki](https://apiok.ru/ext/oauth/) |
| `vk_login_URL` | `url` | [Vkontakte](https://vk.com/dev/auth_sites) |
| `facebook_login_URL` | `url` | [Facebook](https://developers.facebook.com/docs/facebook-login/web/) |
| `mail_ru_login_URL` | `url` | [Mail.ru](https://api.mail.ru/docs/guides/oauth/) |
| `code` | `int` | [Response Codes](#response-codes) |

## Response Codes:
### Common:

| Key | Value | Description |
|-|-|-|
| `SUCCESS` | `00000` | |
| `ERR_NEED_CAPTCHA` | `00001` | | 
| `ERR_UNKNOWN_METHOD` | `00002`| | 
| `ERR_USER_NOT_FOUND` | `00003` | | 
| `ERR_WRONG_CAPTCHA_CODE` | `00004` | | 
| `ERR_EMPTY_MESSAGE` | `00005` | | 
| `ERR_UNKNOWN_ERROR` | `00006` | |
| `ERR_OFTEN_OPERATION` | `00007` | | 
| `ERR_WRONG_CK` | `00008` | |
| `ERR_SMS_NOT_SEND` | `00009` | | 
| `ERR_UNKNOWN_ERROR_PLEASE_RETRY` | `00010` | | 
| `ERR_FORBIDDEN` | `00011` | |
| `ERR_BAD_REQUEST` | `00012` | | 
| `ERR_NEED_CONFIRM_ACTION` | `00013` | | 
| `ERR_USER_IN_YOUR_BLACKLIST` | `00014` | | 
| `ERR_YOU_IN_USER_BLACKLIST` | `00015` | |
| `ERR_MESSAGE_TOO_LONG` | `00016` | | 
| `ERR_MESSAGE_WITH_UNPAID_STICKERS` | `00017` | | 
| `ERR_GCM` | `00018` | | 
| `ERR_USER_ACT_PHONE_NOT_FOUND` | `00019` | | 
| `ERR_OBJECT_NOT_FOUND` | `00020` | |
| `ERR_USER_IS_OWNER` | `00021` | |
| `ERR_COMM_NOT_FOUND` | `00022` | | 
| `ERR_WRONG_EMAIL` | `00023` | | 
| `ERR_WRONG_PHONE` | `00024` | |
| `ERR_USER_IS_BLOCKED` | `00025` | | 
| `ERR_USER_IS_FROZEN` | `00026` | |
| `ERR_APP_NOT_FOUND` | `00027` | | 
| `ERR_WML` | `00028` | |
| `ERR_ADULT_CONTENT` | `00029`| | 
| `ERR_SPAM_CONTROL` | `00030` | |
| `ERR_WRONG_OWNER` | `00031` | | 
| `ERR_NOT_ENOUGH_KARMA` | `00032` | | 
| `ERR_SMALL_RATE` | `00033` | | 
| `ERR_URL_NOT_FOUND` | `00034` | |
| `ERR_YOU_ARE_BANNED` | `00035` | |

### Auth:

| Key | Value | Description |
|-|-|-|
| `ERR_AUTH_REQUIRED` | `01001` | | 
| `ERR_EMPTY_LOGIN_OR_PASSWORD` | `01002` | |
| `ERR_WRONG_LOGIN_OR_PASSWORD` | `01003` | |
| `ERR_SESSION_NOT_FOUND` | `01004` | |
| `ERR_USER_MODEL_NOT_CONSTRUCTED` | `01005` | |
| `ERR_AUTH_ERROR` | `01006` | |
| `ERR_ALREADY_LOGGED_IN` | `01007` | |
| `ERR_ACTIVATION_REQUIRED` | `01008` | |

### Mail:

| Key | Value | Description |
|-|-|-|
| `ERR_CONTACT_NOT_FOUND`: `02001` | |
| `ERR_MESSAGE_ERROR`: `02002` | |
| `ERR_SPAM_CONTROL`: `02003` | |
| `ERR_ADMIN_SEND_DENIED`: `02004` | |
| `ERR_GARBAGE_IS_CLEARING`: `02005` | |
| `ERR_CONTACT_IS_SWAPPING`: `02006` | |
| `ERR_MESSAGE_NOT_FOUND`: `02007` | |
| `ERR_WRONG_EMAIL_FORMAT`: `02008` | |
| `ERR_MESSAGE_SEND_DENIED`: `02009` | |
| `ERR_DUP_MESSAGE`: `02010` | |
| `ERR_WRONG_PHONE_FORMAT`: `02011` | |
| `ERR_TOO_LARGE_ATTACHES_WEIGHT`: `02012` | |
| `ERR_SPAMING_INNER_CONTACT`: `02013` | |
| `ERR_TALK_NOT_FOUND`: `02014` | |

### Reg:

| Key | Value | Description |
|-|-|-|
| `ERR_WRONG_CONTACT`: `03001` | |
| `ERR_CONTACT_ALREADY_USED`: `03002` | |
| `ERR_CONTACT_ALREADY_REGISTERED`: `03003` | |
| `ERR_IP_LIMIT_EXCEEDED`: `03004` | |

### Friends:

| Key | Value | Description |
|-|-|-|
| `ERR_HIS_LIMIT_EXCEEDED`: `04001` | |
| `ERR_YOUR_LIMIT_EXCEEDED`: `04002` | |
| `ERR_OFFER_EXISTS`: `04003` | |
| `ERR_ALREADY_FRIENDS`: `04004` | |
| `ERR_OFFER_BLOCKED`: `04005` | |
| `ERR_FRIEND_NOT_FOUND`: `04006` | |
| `ERR_PENDING_NOT_FOUND`: `04007` | |
| `ERR_FROM`: `04008` | |
| `ERR_EMAIL_USED`: `04009` | |
| `ERR_INVITE_EXISTS`: `04010` | |

### Chat:

| Key | Value | Description |
|-|-|-|
| `ERR_ATTACH_SEND_DENIED`: `05001` | |
| `ERR_ROOM_NOT_FOUND`: `05002` | |
| `ERR_CONTACT_DENIED`: `05003` | |
| `ERR_BANNED`: `05004` | |
| `ERR_NEWBIE`: `05005` | |
| `ERR_FORBIDDEN`: `05006` | |
| `ERR_SHUTUP`: `05007` | |
| `ERR_MESSAGE_PARAMS`: `05008` | |
| `ERR_SPAM`: `05009` | |
| `ERR_DUP_MESSAGE`: `05010` | |
| `ERR_COMPLAIN`: `05011` | |
| `ERR_MESSAGE_NOT_FOUND`: `05012` | |
| `ERR_USER_ISNT_FRIEND`: `05013` | |

### Forum:

| Key | Value | Description |
|-|-|-|
| `ERR_COMMENT_NOT_FOUND`: `06001` | |
| `ERR_TOPIC_NOT_FOUND`: `06002` | |
| `ERR_FORUM_NOT_FOUND`: `06003` | |
| `ERR_FORUM_IN_GARBAGE`: `06004` | |

### Trash:

| Key | Value | Description |
|-|-|-|
| `ERR_OBJ_DELETED`: `07001` | |
| `ERR_OBJ_RESTORED`: `07002` | |

### Voting:

| Key | Value | Description |
|-|-|-|
| `ERR_VOTE_NOT_FOUND`: `08001` | |

### Files:

| Key | Value | Description |
|-|-|-|
| `ERR_DIR_ACCESS_DENIED` | `09001` | |
| `ERR_FILE_NOT_FOUND` | `09002` | |
| `ERR_RESOLUTION_NOT_AVAILABLE` | `09003` | |
| `ERR_WRONG_SIZE` | `09004` | |
| `ERR_BAD_VIDEO_CONVERTER_KEY` | `09005` | |
| `ERR_UPLOAD_ERROR` | `09006` | |
| `ERR_WRONG_TYPE` | `09008` | |
| `ERR_DIR_NOT_FOUND` | `09009` | |
| `ERR_WRONG_TEMP_ID` | `09010` | |
| `ERR_STRANGER_FILE` | `09011` | |
| `ERR_EDIT` | `09012` | |
| `ERR_CANT_LOAD_PIC` | `09013` | |
| `ERR_COLLECTION_NOT_FOUND` | `09015` | |
| `ERR_YOUR_FILE` | `09016` | |
| `ERR_YOUR_COLLECTION` | `09017` | |

### Search:

| Key | Value | Description |
|-|-|-|
| `ERR_BAD_QUERY` | `10001` | |

### Lenta:

| Key | Value | Description |
|-|-|-|
| `ERR_SUBSCR_NOT_FOUND` | `11001` | |
| `ERR_AUTHOR_IS_PRIVATE_GROUP` | `11002` | |
| `ERR_SUBSCR_ALREADY_EXISTS` | `11003` | |

### Gifts:

| Key | Value | Description |
|-|-|-|
| `ERR_GIFT_NOT_FOUND` | `12001` | |

### Services:

| Key | Value | Description |
|-|-|-|
| `ERR_COUNTRY_NOT_FOUND` | `13001` | |
| `ERR_REGION_NOT_FOUND` | `13002` | |
| `ERR_CITY_NOT_FOUND` | `13003` | |
| `ERR_UNIVERSITY_NOT_FOUND` | `13004` | |
| `ERR_FACULTY_NOT_FOUND` | `13005` | |
| `ERR_MOBILE_BRAND_NOT_FOUND` | `13006` | |
| `ERR_GHOST_NOT_FOUND` | `13007` | |
| `ERR_GHOST_UNCHANGED` | `13008` | |

### Complaints:

| Key | Value | Description |
|-|-|-|
| `ERR_WRONG_TYPE` | `14001` | |
| `ERR_WRONG_REASON` | `14002` | |
| `ERR_COMPLAIN_DENIED` | `14003` | |
| `ERR_COMPLAINTS_EXIST` | `14004` | |
| `ERR_TIME_EXCEED` | `14005` | |
| `ERR_CNT_EXCEED` | `14006` | |

### Blacklist:

| Key | Value | Description |
|-|-|-|
| `ERR_WRONG_TYPE` | `15001` | |
| `ERR_OBJECT_NOT_FOUND` | `15002` | |
| `ERR_SPAM_CONTROL` | `15003` | |

### Polls:

| Key | Value | Description |
|-|-|-|
| `ERR_POLL_EXIST` | `16001` | |
| `ERR_ACCESS_DENIED` | `16002` | |
| `ERR_WRONG_OWNER` | `16003` | |
| `ERR_WRONG_END_TIME` | `16004` | |
| `ERR_WRONG_VARIANT` | `16005` | |
| `ERR_VARIANTS_CNT` | `16006` | |
| `ERR_POLL_ISNT_VALIDATE` | `16007` | |
| `ERR_POLL_NOT_FOUND` | `16008` | |
| `ERR_SMALL_RATE` | `16009` | |
| `ALREADY_VOTED` | `16010` | |
| `ERR_VOTING` | `16011` | |

### Attaches:

| Key | Value | Description |
|-|-|-|
| `ERR_ATTACH_NOT_FOUND` | `17001` | |
| `ERR_TYPE_ISNT_SUPPORTED` | `17002` | |
| `ERR_PARENT_NOT_FOUND` | `17003` | |
| `ERR_ATTACH_ALREADY_EXIST` | `17004` | |
| `ERR_WRONG_OWNER` | `17005` | |
| `ERR_MAX_COUNT` | `17006` | |
| `ERR_CHECK_ATTACH` | `17007` | |

### Comm:

| Key | Value | Description |
|-|-|-|
| `ERR_BLOCKED` | `18001` | |
| `ERR_ACCESS_DENIED` | `18002` | |

### Comments:

| Key | Value | Description |
|-|-|-|
| `ERR_INVALID` | `19001` | |
| `ERR_NOT_FOUND` | `19002` | |
| `ERR_EDIT_TIME` | `19003` | |

## WebSocket Token:

## SID:

## CK:
