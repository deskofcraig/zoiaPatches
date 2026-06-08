# ZOIA rules

## Layout
The grid layout is 8 blocks horizontally by 5 blocks vertically, giving 40 blocks per page. 

## Pages
A patch can have up to 64 pages, numbered 0-63.

## Available colors
| Color     | Hexcode   |
|-----------|-----------|
| `red`     | #FF0000 |
| `orange`  | #FFA500 |
| `mango`   | #FFB000 |
| `yellow`  | #FFFF00 | 
| `lime`    | #AFFF00 | 
| `green`   | #00FF00 | 
| `surf`    | #00FF99 | 
| `aqua`    | #00FFFF | 
| `sky`     | #00BFFF | 
| `blue`    | #0000FF |
| `purple`  | #7F00FF |
| `magenta` | #FF00FF |
| `pink`    | #FF69B4 |
| `peach`   | #FFDAB9 |
| `white`   | #FFFFFF |

## Characters allowed
```
{ 
  "characters":[ 
     {"allowed":["A","B","C","D","E","F","G","H","I","J","K",
     "L","M","N","O","P","Q","R","S","T",
     "U","V","W","X","Y","Z",
     "a","b","c","d","e","f","g","h","i","j","k",
     "l","m","n","o","p","q","r","s","t",
     "u","v","w","x","y","z",
     ".","_","-",
     "0","1","2","3","4","5","6","7","8","9"]},
    {"max-length":"15 characters"}
    ]
}
```
