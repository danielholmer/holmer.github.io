---
title: Spotify-helper&#58;  Your friendly Spotify assistant
excerpt: "A web-app for automatically displaying lyrics to your currently playing song on Spotify."
tags:
    - Project
header:
  overlay_image: /assets/images/spotify/spotify-header.png
  #caption: "Photo credit: [coolbackgrounds.io](https://coolbackgrounds.io/)"
share: false
subscribe: false
comments: false
#last_modified_at:
---

I spend several hours each day listening to music on Spotify. Wheter I'm studying, doing the dishes,
or going for a walk, there is almost a guarantee that a song is streaming through my headphones.
Lately I've found myself searching for the lyrics of songs in an increasing frequency;  
manually having to google the artist and song name of the currently playing track. This is in itself
not a hard task, but nevertheless something that could potentially be [automated, saving precious seconds each lookup](https://xkcd.com/1319/)! Out of this idea a web-app with the (increadibly innovative) name _Spotify-helper_ was born.

The app (which can be found at **[spotify.holmer.io](https://spotify.holmer.io)**) allows a user to login using their Spotify account, and automatically be shown the lyrics to the song currently playing by the account. There is also an option to show
the users top 20 most played songs during three different time frames; weekly, monthly and yearly.   

Inline-style:
![alt text](/assets/images/spotify/main-demo.png "Logo Title Text 1")

```python
auth_manager = spotipy.oauth2.SpotifyOAuth(client_id=SPOTIPY_CLIENT_ID,
                                           client_secret=SPOTIPY_CLIENT_SECRET, redirect_uri=SPOTIPY_REDIRECT_URI, cache_path=CACHE_PATH,
                                           show_dialog=True,
                                           scope='user-read-currently-playing user-read-private user-top-read')
```

sass_dir

```python
@app.route("/logout/")
def logout():

    session.pop('token_info', None)
    session.clear()
    os.remove(CACHE_PATH)

    return redirect("/")
```
