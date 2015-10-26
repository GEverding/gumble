# gumble

## Sub-projects

- gumble [![GoDoc](https://godoc.org/github.com/GEverding/gumble/gumble?status.svg)](https://godoc.org/github.com/GEverding/gumble/gumble)
    - Client library
- gumble_openal
    - [OpenAL](http://kcat.strangesoft.net/openal.html) audio system for gumble
- gumble_ffmpeg
    - [ffmpeg](https://www.ffmpeg.org/) audio source for gumble
- gumbleutil
    - Extras that can make working with gumble easier

## Example

    package main

    import (
      "github.com/GEverding/gumble/gumble"
      "github.com/GEverding/gumble/gumbleutil"
    )

    func main() {
      gumbleutil.Main(nil, gumbleutil.Listener{
        UserChange: func(e *gumble.UserChangeEvent) {
          if e.Type.Has(gumble.UserChangeConnected) {
            e.User.Send("Welcome to the server, " + e.User.Name + "!")
          }
        },
      })
    }

## Related projects

- [barnard](https://github.com/GEverding/barnard)
    - terminal-based Mumble client
- [piepan](https://github.com/GEverding/piepan)
    - an easy to use framework for writing scriptable Mumble bots using JavaScript and Lua

## License

MIT

## Author

Tim Cooper (<tim.cooper@GEverding.com>)
