# jwt-crack-goLang

JWT bruteForce inspired by https://github.com/lmammino/jwt-cracker

This is really only effective for cracking JWTs with weak secrets. Only works with hmac-sha256 sign.

## Usage
```
Usage of go-jwt-cracker:
  -alphabet string
        The alphabet to use for the brute (default "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789")
  -maxlen int
        The max length of the string generated during the brute (default 12)
  -prefix string
        A string that is always prefixed to the secret
  -suffix string
        A string that is always suffixed to the secret
  -token string
        The full HS256 jwt token to crack
```

## Example
Cracking a token generated with [jwt.io](https://jwt.io):

```bash
go run main.go -token "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6Ik5pa2l0YSBWdG9ydXNoaW4iLCJpYXQiOjE1MTYyMzkwMjIsIm1haWwiOiJuLnZ0b3J1aGluQGluYm94LnJ1IiwidGciOiJAbmlraXRhdm9yeWV0In0.S7vayZVGwvivBhOJfspPkvNqIN8CuUYZmEaJ0gwSFg0" -alphabet "abcdefghijklmnopqrstuwxyz" -maxlen 6
```

### Output

```
Parsed JWT:
- Algorithm: HS256
- Type: JWT
- Payload: {"sub":"1234567890","name":"Nikita Vtorushin","iat":1516239022,"mail":"n.vtoruhin@inbox.ru","tg":"@nikitavoryet"}
- Signature (hex): 4bbbdac99546c2f8af0613897eca4f92f36a20df02b94619984689d20c12160d

There are 254313150 combinations to attempt
Start cracking JWT secret...
Attempts: 100000
Attempts: 200000
Attempts: 300000
...
Attempts: 184500000
Attempts: 184600000
Attempts: 184700000
Found secret in 184776822 attempts: secret
```

### Time spent
- Intel Core i9-9900k @ 3.6GHz - around 1.5 minutes
- Intel Core i5 @ 2.9GHz - around 4 minutes

Donate:

    BTC:  192TC7d7ZRYJQbQnAWvMpkccnBNQN1ae6R
    ETH:  0x7d1082d952f4d584ae2910e14018f4dce7495c74
    LTC:  MLx6wmFjXfBTKj6JfB5NXaiKjNLeEntRoZ
    DOGE: DHCjW71EWBzvv43XPXVJc491brcBJXXq88
author: 
    
    Name:          Nikita
    Company:       SmartWorld
    Position:      TeamLead
    Mail:          n.vtorushin@inbox.ru
    TG:            @nikitavoryet
    Year of birth: 1999
    FullStack:     JS/GO
    