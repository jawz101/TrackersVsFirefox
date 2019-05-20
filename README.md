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

*Used these additional settings though it's mostly irrelevant: enable advanced mode, check the 4 privacy ckboxes (CSP, Hyperlink auditing, WebRTC, prefetching). Used all of the uBO Built-in rules in the top section as well as EasyList, Adguard Base, EasyPrivacy, Adguard Tracking Protection, and imported StevenBlack's hosts file as a custom list since it's the most solid hostsfile blocklist, disabled cosmetic filtering.)
*Whitelisted a few domains to fix expected breakage. eg. ajax.googleapis.com, trbas.com, fscdn.com, youtube.com, ytimg.com, etc.  Global or local noop rules as appropriate.
![uBOMedium](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Medium_Mode/ublock_origin_medium_mode%2B.png)

NoScript custom configuration and configured

*I tried to unbreak as much as possible.  I really like NoScript but its features are just different.  Pros: I like the "Trust No One" approach but you can achieve this with uBO in Medium Mode; even without any blocklists in uBO if you have Medium Mode on you're almost there.  I'd be most interested to know how NoScript and uBlock compare in regards to performance and if these implementations cripple web technologies in an unforeseen way or can cause websites to spazz and keep trying the same thing over and over. Anyways, the config file is in the folder if you want to import it.  I use NoScript in a certain way so I wanted to reproduce how I use it.  Clear out the preset domains, temporarily allow 1st-party.  Uncheck all default components, only check scripts, fonts, fetch for trusted, and apply custom permissions for any 1st and 3rd parties that need something not allowed.  Regardless, NoScript only sees 3rd parties if they come with a script, so if a domain was only referenced for web fonts you can't really block them.  In uBO you could create some My Filters to block extra stuff by default.- which I usually do, but not for these tests.  I also ran this a week later so the sites' connecting domains might've changed a little.
![NoScript Custom](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noscript_custom/NoScript_custom.png)

Normally, I would block websockets, objects, and other in uBO by default with these rules added to My Filters:
    *$object
    *$other
    *$websocket
and sometimes 3rd party fonts to save on bandwidth, esp. on mobile devices.  All things being blocked, woff files can still be half of a website's size.
    *$fonts,third-party
