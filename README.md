# TrackersVsFirefox
comparing different blocking utilities

Testing Firefox against 25 sites listed in the bookmarks.html file.  Refreshed the pages a few times to make sure they fully loaded & scrolled down and up the page a few times to make sure it loaded what all it wanted.

Visualizations provided by Firefox Lightbeam https://addons.mozilla.org/en-US/firefox/addon/lightbeam/

Import the bookmarks.html into FFox to test for yourself!


No Tracking Protection
Firefox > Privacy & Security > Content Blocking > Custom > uncheck everything
![noTracking](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_TP_disabled/no_blocking.png)

Standard Tracking Protection (Firefox's default)
Firefox > Privacy & Security > Content Blocking > Standard
![StandardTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_Standard_Preset/standard_blocking_preset.png)

Strict Tracking Protection
Firefox > Privacy & Security > Content Blocking > Strict

personal note: Strict mode is when browsing performance drastically improved.
![StrictTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_Strict_Preset/strict_preset.png)

uBlock Origin "Easy Mode" (uBO's default configuration & Firefox's Content Blocking disabled.  Cosmetic filtering is irrelevant.)
![uBOEasy](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Defaults/ublock_origin_default_preset.png)

uBlock Origin "Medium Mode" (same as uBO Easy but third party scripts & frames disabled.  Cosmetic filtering is irrelevant.)

*Used these additional settings though it's mostly irrelevant: enable advanced mode, check the 4 privacy ckboxes (CSP, Hyperlink auditing, WebRTC, prefecthing). Used all of the uBO Built-in rules in the top section as well as EasyList, Adguard Base, EasyPrivacy, Adguard Tracking Protection, and imported StevenBlack's hosts file as a custom list since it's the most solid hostsfile blocklist, disabled cosmetic filtering.)

![uBOMedium](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Medium_Mode/ublock_origin_medium_mode%2B.png)
