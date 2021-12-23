# Huey
Hugo theme


## Why is it named Huey?
The name "Huey" was taken from the musician "Baby Huey". The record was on the mantle when the theme author was trying to come up with a name.


## Todo
- Current page in navigaiton
- Current title + main page title
- Add back the subtitle
- RSS (index.xml)

## Configuration

### Subtitle and Description
If you set a "subtitle" in your config.toml in [params], this will be used as the default subtitle. If you prefer, you can use the "description" used in your site instead, which is also used in your header for search engines. If neither a "subtitle" or "description" are set, nothing will be displayed

### Using FontAwesome
Font Awesome is a configuration option, though you will need to specify your own token. Additionally, the rest is up to you! This was added as a convenience for people who prefer to modify themes without knowing about how most of it works. 



### Configuration Params Needed

    dateFormat = "January 2, 2006"
    description = "Leader and Coffee Drinker"
    subtitle = ""
    keywords = ""

    # Use your Font Awesome token here
    # fontawesomeToken = "018de52a07"


## Using Local Assets

Assets, such as Bulma CSS, are stored as part of the project theme. This ensures you can move your site around without needing network access. However, other assets like Font Awesome are not local. They are instead pulled from Font Awesome CDN (Content Delivery Network). 

If you need to have Font Awesome icons readily available, download them to the `/static` folder in a dedicated `icons` folder. Link to the static icon assets directly whenever needed. 