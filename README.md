# getsong

[![travis](https://travis-ci.org/schollz/getsong.svg?branch=master)](https://travis-ci.org/schollz/getsong) 
[![go report card](https://goreportcard.com/badge/github.com/schollz/getsong)](https://goreportcard.com/report/github.com/schollz/getsong) 
[![coverage](https://img.shields.io/badge/coverage-60%25-yellow.svg)](https://gocover.io/github.com/schollz/getsong)
[![godocs](https://godoc.org/github.com/schollz/getsong?status.svg)](https://godoc.org/github.com/schollz/getsong) 

This is a simple library that utilizes the [rylio/ytdl YouTube downloader](https://github.com/rylio/ytdl) and [ffmpeg](https://www.ffmpeg.org/) to get almost any mp3 of a song that you want to listen to. I wrote this so I could [download mp3s of my favorite Spotify playlists](https://github.com/schollz/spotifydownload). 


## Install

```
go get -u github.com/schollz/getsong/...
```

## Usage 

The aim of this library to have a low (or zero) false positive rate, so it works best when the entered title + artist are spelled correctly.

### Use as a program

```bash
$ getsong 'Getting in Tune' 'The Who'
Downloading 'Getting in Tune by The Who (W6-3rnD7FSc).webm'...
 4.72 MiB / 4.72 MiB [==========================] 100.00% 37.97 KiB/s 2m7s
...converting to mp3...
Downloaded 'Getting in Tune by The Who (W6-3rnD7FSc).mp3'
```

### Use as a library

```golang
// download "True" by "Spandau Ballet"
fname, err := getsong.GetSong("True", "Spandau Ballet")
if err == nil {
    fmt.Printf("Downloaded '%s'\n", fname)
}
```

## Contributing

Pull requests are welcome. Feel free to...

- Revise documentation
- Add new features
- Fix bugs
- Suggest improvements

## License

MIT
