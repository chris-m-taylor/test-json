# Band Content JSON Objects Documentation

This documentation provides information about the structure of JSON objects used to manage band content on your website.

## Environment-specific Configuration

- **Production Environment (Prod):** The production environment looks for information in the "prod" folder.
- **Development Environment (Dev):** The development environment looks for information in the "dev" folder.

Please ensure that you place the appropriate JSON files in the respective folders based on your environment.

## Vercel Deployment Configuration

When deploying your application to Vercel, make sure to set the following environment variables:

- **BANDS_IN_TOWN_API_KEY:** Provide your Bands In Town API key in vercel for fetching show information.
- **HYPHENATED_BAND_NAME:** Set the hyphenated band name as an environment variable. This is used to point to the correct test-json route.

This documentation provides information about the structure of JSON objects used to manage band content on your website.

## Menu JSON Object

The `menu` object contains information about the navigation menu options.

```json
{
  "menu": {
    "menuOptions": [
      {
        "label": "Home",
        "route": "/"
      },
      {
        "label": "Shows",
        "route": "/#ShowsLink"
      },
      {
        "label": "Lyrics",
        "route": "/Lyrics"
      },
      {
        "label": "Videos",
        "route": "/#VideosLink"
      }
    ]
  },
  "theme": "forest"
}
```

### Available Menu Options

- "Home" - Label: "Home", Route: "/"
- "Shows" - Label: "Shows", Route: "/#ShowsLink"
- "Lyrics" - Label: "Lyrics", Route: "/Lyrics"
- "Videos" - Label: "Videos", Route: "/#VideosLink"

### Available Theme Options
- "theme" - Label: "chosen theme"
Make sure you add the theme to the project and name it the same thing.

### Modifying Menu Options

To customize the navigation menu, you can:

- Remove any nested menu options to hide them from all navigation bars.
- To add a new link, ensure that the `route` field matches the component ID for auto-scrolling. For new pages, create them in the Next.js app folder and wrap any conditional rendering as needed.

## Band Info JSON Object

The `bandInfo` object provides general information about the band.

```json
{
  "bandInfo": {
    "name": "Band Name",
    "slogan": "Providing quality music since YYYY"
  },
  "images": {
    "bandGroupPic": "https://example.com/band-image.jpg"
  },
  "social": {
    "socialLinks": {
      "youtube": { "link": "https://www.youtube.com" },
      "instagram": { "link": "https://www.instagram.com" },
      "appleMusic": { "link": "https://www.apple.com" },
      "spotify": { "link": "https://www.spotify.com" },
      "twitter": { "link": "https://www.twitter.com" },
      "facebook": { "link": "https://www.facebook.com" },
      "tiktok": { "link": "https://www.tiktok.com" },
      "bandcamp": { "link": "https://www.bandcamp.com" }
    },
    "bandEmail": "band@example.com",
    "youtubeVideoIds": [
      "videoId1",
      "videoId2",
      "videoId3"
    ]
  }
}
```

### Band Information

- Band Name: "Band Name"
- Slogan: "Providing quality music since YYYY"

### Band Images

- Band Group Picture: This is currently stored in github but in the future can be a link to anywhere

### Social Links

You can customize the social links:

- YouTube: [YouTube Link](https://www.youtube.com)
- Instagram: [Instagram Link](https://www.instagram.com)
- Apple Music: [Apple Music Link](https://www.apple.com)
- Spotify: [Spotify Link](https://www.spotify.com)
- Twitter: [Twitter Link](https://www.twitter.com)
- Facebook: [Facebook Link](https://www.facebook.com)
- TikTok: [TikTok Link](https://www.tiktok.com)
- Bandcamp: [Bandcamp Link](https://www.bandcamp.com)

### Contact Information

- Band Email: band@example.com

### YouTube Videos

You can customize the displayed YouTube videos by replacing the video IDs in the `youtubeVideoIds` array. You get these values by looking at the ?v=dDFAddfD in a youtube video.

The presence of a YouTube link in the `socialLinks` field will determine whether the "See All Videos" button is displayed on the website. If the YouTube link is removed, the button will be hidden.

## Songs JSON Object

The `songs` object contains information about the band's songs.

```json
{
  "songs": [
    {
      "title": "Song 1",
      "lyrics": "Verse 1:\nLyrics for the first verse...\n\nChorus:\nLyrics for the chorus..."
    },
    {
      "title": "Song 2",
      "lyrics": "Verse 1:\nLyrics for the second song's verse...\n\nChorus:\nLyrics for the second song's chorus..."
    }
  ]
}
```

### Available Songs

1. **Song 1**
   - Lyrics:
     ```
     Verse 1:
     Lyrics for the first verse...
     
     Chorus:
     Lyrics for the chorus...
     ```

2. **Song 2**
   - Lyrics:
     ```
     Verse 1:
     Lyrics for the second song's verse...
     
     Chorus:
     Lyrics for the second song's chorus...
     ```

### Modifying Songs

Make sure this route exists even if you are not using it. It needs an empty song array at the minimum.

To modify the songs component:

- If the song component is empty, the "/Lyrics" route will return no songs.
- To remove the option to go to the "/Lyrics" page entirely, remove it from the navigation links in the Menu JSON Object.
- Note that lyrics are wrapped in a `<pre>` tag, so formatting in the string will be applied to the page. It's recommended to format songs in a text file and then convert them to JSON-safe strings.

Feel free to copy and paste these JSON templates into your project and customize them according to your band's content and needs.