# TrackersVsFirefox
comparing different blocking utilities

Testing Firefox against 25 sites listed in the bookmarks.html file.  Refreshed the pages a few times to make sure they fully loaded & scrolled down and up the page a few times to make sure it loaded what all it wanted.

Visualizations provided by Firefox Lightbeam https://addons.mozilla.org/en-US/firefox/addon/lightbeam/
*deadlink.  github repo is at https://github.com/mozilla/lightbeam-we
uploaded the latest release which I did the testing into this parent directory file jid1-F9UJ2thwoAm5gQ@jetpack.xpi

Import the bookmarks.html into FFox to test for yourself!


**No Tracking Protection**
Firefox > Privacy & Security > Content Blocking > Custom > uncheck everything
![noTracking](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_TP_disabled/no_blocking.png)

**Standard Tracking Protection (Firefox's default)**
Firefox > Privacy & Security > Content Blocking > Standard
![StandardTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_Standard_Preset/standard_blocking_preset.png)

**Strict Tracking Protection**
Firefox > Privacy & Security > Content Blocking > Strict

personal note: Strict mode is when browsing performance drastically improved.  **Strict Mode with the Level 2 (not depicted resulted in approx. 326 connected domains. Level 2 tested June 28,2019)**
![StrictTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noAddons_Strict_Preset/strict_preset.png)

uBlock Origin "Easy Mode" (uBO's default configuration & Firefox's Content Blocking disabled.  Cosmetic filtering is irrelevant.)
![uBOEasy](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Defaults/ublock_origin_default_preset.png)

**uBlock Origin "Medium Mode"** (same as uBO Easy but third party scripts & frames disabled.  Cosmetic filtering is irrelevant.)

*Used these additional settings though it's mostly irrelevant: enable advanced mode, check the 4 privacy ckboxes (CSP, Hyperlink auditing, WebRTC, prefetching). Used all of the uBO Built-in rules in the top section as well as EasyList, Adguard Base, EasyPrivacy, Adguard Tracking Protection, and imported StevenBlack's hosts file as a custom list since it's the most solid hostsfile blocklist, disabled cosmetic filtering.)
*Whitelisted a few domains to fix expected breakage. eg. ajax.googleapis.com, trbas.com, fscdn.com, youtube.com, ytimg.com, etc.  Global or local noop rules as appropriate.
![uBOMedium](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Medium_Mode/ublock_origin_medium_mode%2B.png)

**Privacy Badger**
![PrivacyBadger](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/PrivacyBadger/privacy_badger.png)

**NoScript** custom configuration

*I tried to unbreak as much as possible.  I really like NoScript but its features are just different.  Pros: I like the "Trust No One" approach but you can achieve this with uBO in Medium Mode; even without any blocklists in uBO if you have Medium Mode on you're almost there.  I'd be most interested to know how NoScript and uBlock compare in regards to performance and if these implementations cripple web technologies in an unforeseen way or can cause websites to spazz and keep trying the same thing over and over. Anyways, my config file is in the folder if you want to import it.  I use NoScript in a certain way so I wanted to reproduce how I use it.  Clear out the preset domains, temporarily allow 1st-party.  Uncheck all default components, only check scripts, fonts, fetch for trusted, and apply custom permissions for any 1st and 3rd parties that need something not allowed.  Regardless, **NoScript only sees domains if they include javascript**, so if a domain was only referenced for web fonts you will not see them.  I also ran this a week later so the sites' connecting domains might've changed a little.
Not depicted but I also ran a test w/ NoScript and Firefox's tracking protection on and it was pretty comprable to UbO in Medium Mode.  So, really, it's a coin toss.  uBO offers a little more control in trust of a domain as a 1st-party vs 3rd-party and non-javascript 3rd parties but it is a relatively minor difference.
![NoScript Custom](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/noscript_custom/NoScript_custom.png)


*Notes on UBlock Origin*
Normally, I would block websockets, objects, and other in uBO by default with these rules added to My Filters:

    *$font,third-party
    *$object
    *$other
    *$websocket

And sometimes

    *$xmlhttprequest,third-party

...and sometimes 3rd party fonts to save on bandwidth, esp. on mobile devices.  Even in Medium Mode and on a static site, woff files can still be half of a website's size.

I wish someone would make a Decentraleyes for just font libraries, come up with a standard set to inject, or cache them in an add-on bucket... something.  Fonts get used for general graphics as well which is confusing.  I just don't understand them.

Recommendations?

If you don't want to deal with add-ons: in the least enable Firefox's built-in tracking protection (Privacy & Security >  Content Blocking set to custom and check all of the boxes, enable tracker blocking for all windows, and block all 3rd party cookies.

If you do want to deal with add-ons use at least NoScript + Firefox's Tracking Protection or uBlock Origin in Medium Mode.  The default uBO setup doesn't offer much more than Firefox's built-in features.  Taking an aggressive approach to block all 3p scripts by default drastically eliminates the need to rely on blocklists and prevents those trackers not presently on blocklists.  ghacks also lists quite a few additional configurations and recommended extensions
https://github.com/ghacksuserjs/ghacks-user.js/wiki/4.1-Extensions
I don't like most people's recommendations because most of us (myself included) do not understand the overlap amongst extensions.  My setup changes all of the time depending on how I want to approach it.
