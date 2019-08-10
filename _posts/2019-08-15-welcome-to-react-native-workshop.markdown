---
layout: post
title:  "Welcome to React Native Workshop"
---

# Following are the useful info to refer to during workshop

 - React Native Installation steps to follow [here](https://facebook.github.io/react-native/docs/getting-started) and follow the **React-Native CLI** guide

 - Sample JSON
 {% highlight json %}
 [
  {
    "name": "Iron Cross Army",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/b/40/image_not_available.jpg",
    "description": ""
  },
  {
    "name": "Iron Fist (Bei Bang-Wen)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/9/20/53176ebd40ad7.jpg",
    "description": ""
  },
  {
    "name": "Iron Fist (Danny Rand)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/3/f0/52616788ebc63.jpg",
    "description": ""
  },
  {
    "name": "Iron Fist (Orson Randall)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/6/e0/53176e979cca2.jpg",
    "description": ""
  },
  {
    "name": "Iron Fist (Quan Yaozu)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/4/20/53176e89b563e.jpg",
    "description": ""
  },
  {
    "name": "Iron Fist (USM)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/6/20/52321751dffa6.jpg",
    "description": "Danny is always focused yet relaxed - more Zen-focused than chill surfer dude."
  },
  {
    "name": "Iron Fist (Wu Ao-Shi)",
    "thumbnailUrl": "http://i.annihil.us/u/prod/marvel/i/mg/7/03/53176f05a6851.jpg",
    "description": ""
  }
]
 {% endhighlight %}
 - API Related details

 API base URL | `https://gateway.marvel.com:443/v1/public`
 API endpoint to search characters by name starts with | `/characters`
 `apikey` | `6c3e2173a8f3e5adb795172ad8dd3ef2`
 `hash` | `4629485a6de69f01f4046b53b33a1386`
 
 - Final URL
 ```
 https://gateway.marvel.com:443/v1/public/characters?apikey=6c3e2173a8f3e5adb795172ad8dd3ef2&hash=4629485a6de69f01f4046b53b33a1386&ts=1&nameStartsWith=Spider
 ```
 - Code snippet to convert API response to the desired data
 {% highlight javascript %}
 getParsedData(apiData) {
    return apiData.data.results.map(item => {
        return {
            name: item.name,
            thumbnailUrl: `${item.thumbnail.path}.${item.thumbnail.extension}`,
            description: item.description,
        };
    });
 }
 {% endhighlight %}