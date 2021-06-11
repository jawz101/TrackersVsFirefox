# TrackersVsFirefox
comparing different blocking utilities

**if you use this for some research project or just want to talk about it lemme know.  I'd love to know/ help in any way.

Testing Firefox against 25 sites listed in the bookmarks.html file.  Refreshed the pages a few times to make sure they fully loaded & scrolled down and up the page a few times to make sure it loaded what all it wanted.

Visualizations provided by Firefox Lightbeam https://addons.mozilla.org/en-US/firefox/addon/lightbeam/
*deadlink.  github repo is at https://github.com/mozilla/lightbeam-we
uploaded the latest release with which I did the testing into this parent directory file jid1-F9UJ2thwoAm5gQ@jetpack.xpi

Import the bookmarks.html into FFox to test for yourself!


**No Tracking Protection**
Firefox > Privacy & Security > Content Blocking > Custom > uncheck everything
![noTracking](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/no_protection.png)

**Standard Tracking Protection (Firefox's default)**
Firefox > Privacy & Security > Content Blocking > Standard
![StandardTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/standard.png)

**Strict Tracking Protection**
Firefox > Privacy & Security > Content Blocking > Strict
![StrictTP](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/strict.png)

**uBlock Origin "Easy Mode"** (uBO's default configuration & Firefox's Content Blocking disabled.  Cosmetic filtering is irrelevant.)
![uBOEasy](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/uBlockOrigin_Defaults/ublock_origin_default_preset.png)

**uBlock Origin "Medium Mode"** (same as uBO Easy but third party scripts & frames disabled.  Cosmetic filtering is irrelevant.  attached my setup)
![uBOMedium](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/ubo_medium.png)

**NoScript** (custom configuration. attached my setup)
![NoScript Custom](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/noscript.png)

**Privacy Badger**
![PrivacyBadger](https://raw.githubusercontent.com/jawz101/TrackersVsFirefox/master/v2021/privacy_badger.png)

*Notes on UBlock Origin*
Normally, I would block websockets, objects, and other in uBO by default with these rules added to My Filters:

    *$font,third-party
    *$object
    *$other
    *$websocket

And sometimes

    *$xmlhttprequest,third-party

...and sometimes 3rd party fonts to save on bandwidth, esp. on mobile devices.  Even in Medium Mode and on a static site, woff files can still be half of a website's size.

Recommendations?

If you don't want to deal with add-ons: in the least enable Firefox's built-in tracking protection (Privacy & Security >  Content Blocking set to custom and check all of the boxes, enable tracker blocking for all windows, and block all 3rd party cookies.

If you do want to deal with add-ons use at least NoScript + Firefox's Tracking Protection or uBlock Origin in Medium Mode.  The default uBO setup doesn't offer much more than Firefox's built-in features.  Taking an aggressive approach to block all 3p scripts by default drastically eliminates the need to rely on blocklists and prevents those trackers not presently on blocklists.
