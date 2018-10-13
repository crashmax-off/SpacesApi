# API of Spaces.ru

## Available methods:
- [`Session`](#session)

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

## Session:
### POST `https://spcs.me/neoapi/session`
| Params | Value | Description |
|-|-|-|
| `login` | `string` | Nickname (3-15), E-mail or phone number |
| `password` | `string` | Username password (6-20) |
| `method` | `login` | Authorization method |
| `rid` | `APA91bFwsPw4clF4y0RHWtg6Y4fC6UnxcrmZYLiko_ifv-8g7Qi-5koV4GRaVax5zMWTMke9eUF-MzHhzdM9iYQEFDff5lnHuMlwIl-zNAu4MfYS4PlL0j8C28XZgNJmQbRSd1BE4eSW` | API Token (Required) |

### Response data
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

## Response Codes:

## WebSocket Token:

## SID:

## CK:
