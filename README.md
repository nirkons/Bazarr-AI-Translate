# Bazarr AI Translate
Script to automatically translate subtitles with Bazarr as a Tautulli Agent when an item is added to Plex or autonomously via cron

Based on my own experience, it is hard to find subtitles for some old/unpopular series/movies, genres or even animes and in most of the cases they have English subtitles embedded or at least online.
I created this script because auto-translation is not in Bazarr's roadmap (https://bazarr.featureupvote.com/suggestions/126221/auto-translation-feature). Take in mind that this will not provide the optimal subtitles and, as the developer tells in the comments, understand this is just a last resort solution.

The script first tries to download subtitles in a desired languages (two can be selected) and if it does not find any of them then downloads/imports embedded subtitles in English and translates to your desired language. Languages can be modified in `FIRST_LANG` and `SECOND_LANG`(if only want one, leave empty).

### Required
- Bazarr (obviously)
### Optional (modify the script if you dont use them)
- Tautulli: used to detect the new episodes/movies added into Plex and running the script itself
- Plex: refresh metadata of the new added episodes/movies to ensure subtitles are loaded instantly
You can remove `refresh_plex_item_metadata()` to run without these two and run the script manually or via cron.

## Best Bazarr settings to optimize this script:
- Configure **Embedded Subtitles** Provider


![imagen](https://github.com/anast20sm/Bazarr_AutoTranslate/assets/33606434/d5e5b443-b0ae-4adb-b32b-07a6f5338a1d)


- Disable **Use Embedded Subtitles**


![imagen](https://github.com/anast20sm/Bazarr_AutoTranslate/assets/33606434/e2712537-1e83-4590-9cc4-1f2e47ad0cbc)


Embedded subtitles cannot be used/modified by Bazarr so with these two settings it will extract the embedded subtitles in case there are (by default I only programmed extract English subs).

- Enable **Upgrade Previously Downloaded Subtitles** and **Upgrade Manually Downloaded or Translated Subtitles**


 ![imagen](https://github.com/anast20sm/Bazarr_AutoTranslate/assets/33606434/42736f20-fb55-43de-b45e-a07cceea73d2)


 
 ![imagen](https://github.com/anast20sm/Bazarr_AutoTranslate/assets/33606434/5c1eb5c1-e52f-42c4-a871-eb4cfbb90582)


This is recommended to always have the best possible subtitles, and if possible one made by a person who understands what is happening in the show/movie and writes with context.
I repeat again, as translated subtitles will never be as good as subtitles made by someone, this setting will ensure translated is only the last option.

## Setup in Tautulli
https://github.com/Tautulli/Tautulli/wiki/Custom-Scripts
