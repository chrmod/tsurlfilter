# TSWebExtension Changelog

All notable changes to this project will be documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- TODO: manually add compare links for version to the end of the file -->
<!-- e.g. [0.1.2]: https://github.com/AdguardTeam/tsurlfilter/compare/tswebextension-v0.1.1...tswebextension-v0.1.2 -->


## [0.3.20] - 2023-09-19

### Added
- CSP `trusted-types` directive modifying for response headers
  [#2068](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2068).


## [0.3.19] - 2023-09-18

### Fixed
- `$csp`, `$removeparam` and `$removeheader` allowlist rules not being published as filtering log events.
- Cosmetic rule injection in cached subdocument
  [#2420](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2420),
  [#2190](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2190),
  [#2328](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2328).


## [0.3.18] - 2023-09-13

### Fixed
- Do not block a tab loading by `$popup` modifier rule on direct url navigation
  [#2449](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2449).


## [0.3.17] - 2023-09-13

### Added
- New `requestUrl`, `frameUrl` and `requestType` fields in `ApplyBasicRuleEvent`.

### Fixed
- Tab title is now correctly updated on url change when the document does not provide it itself
  [#2428](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2428).
- Filter id for StealthApi to display Stealth Mode cookie events in Filtering Log properly
  [#2487](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2487).


## [0.3.16] - 2023-09-05

### Fixed
- Do not apply cosmetic rules to extension pages while fallback processing
[#2459](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2459).


## [0.3.15] - 2023-09-05

### Fixed
- Redirects are not included into tab's blocked requests count
  [#2443](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2443).


## [0.3.14] - 2023-09-05

### Fixed
- Domains from the allowlist are not properly escaped before being passed into the regular expression rules
  [#2461](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2461).
- Cosmetic rule false positive applying when tab context changed while injection retry
  [#2459](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2459).


## [0.3.13] - 2023-08-25

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.11`.
- Updated `@adguard/scriptlets` to `v1.9.72`.


## [0.3.12] - 2023-08-23

### Fixed
- Incorrect order of `onBeforeRequest` handlers.
- Blocked csp reports do not increment the blocked requests counter.


## [0.3.11] - 2023-08-21

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.10`.
- Updated `@adguard/scriptlets` to `v1.9.70`.

### Fixed
- Applying $cookie rules on the content-script side.


## [0.3.10] - 2023-08-18

### Added
- Blocking third-party requests with `csp_report` content-type.
- Handling discarded tabs replacement on wake up.

### Fixed
- Do not expose JS rules in global page scope.


## [0.3.9] - 2023-08-10

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.7`.


## [0.3.8] - 2023-08-04

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.6`.
- Updated `@adguard/scriptlets` to `v1.9.62`.


## [0.3.7] - 2023-07-21

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.5`.
- Updated `@adguard/scriptlets` to `v1.9.57`.

## Fixed
- Duplicate `eventId` of filtering events.


## [0.3.6] - 2023-07-11

### Fixed
- Rules with the `$popup` modifier were ignored and showed an incorrect dummy
  page instead of closing the tab.
- In some cases, rules with the `$document` modifier did not show the dummy page.

## [0.3.5] - 2023-07-11

### Fixed
- Cosmetic rule logging


## [0.3.4] - 2023-07-11

### Added
- Support of $elemhide, $specifichide and $generichide modifiers.

### Fixed
- Cosmetic rule matching for frames loaded from the service worker cache.


## [0.3.3] - 2023-06-19

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.2`.


## [0.3.2] - 2023-06-14

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.1`.


## [0.3.1] - 2023-06-15

### Added
- new `DocumentApi` class, with frame-matching taking into account the state of the `Allowlist`.

### Changed
- `AllowlistApi` renamed to `Allowlist`. `matchFrame` method moved to `DocumentApi` class.

### Fixed
- Extra headers handling in chromium browsers.
- Filtering log update on cached pages reload.


## [0.3.0] - 2023-06-14

### Changed
- Updated `@adguard/tsurlfilter` to `v2.1.0`.

## [0.2.8] - 2023-06-13

### Changed
- `logLevel` configuration property type to `string`.
- `RequestContextStorage` to extend from `Map`.

### Deleted
- `record`, `find` methods and `onUpdate`, `onCreate` events from `RequestContextStorage`.


## [0.2.6] - 2023-06-06

### Changed
- Updated `@adguard/scriptlets` to `v1.9.37`.


## [0.2.5] - 2023-06-06

### Fixed
- Tab context matching for pages with cached document page.


## [0.2.4] - 2023-06-05

### Fixed
- `hideRequestInitiatorElement` function return more accurate css selector src attribute value
for first party requests.
- `ElementCollapser` inject styles via isolated style tag.


## [0.2.3] - 2023-05-31

### Fixed
- Script rules injection.


## [0.2.2] - 2023-05-29

### Added
- New `logLevel` optional property for MV2 configuration to control logging levels.

### Changed
- `verbose` MV2 configuration property is now optional.


## [0.2.0] - 2023-05-23

### Added
- New MV2 API methods for configuration updating without engine restart: `setFilteringEnabled`,`setCollectHitStats`, `setStealthModeEnabled`, `setSelfDestructFirstPartyCookies`, `setSelfDestructThirdPartyCookies`, `setSelfDestructThirdPartyCookies`, `setSelfDestructFirstPartyCookiesTime`, `setSelfDestructThirdPartyCookiesTime`, `setHideReferrer`, `setHideSearchQueries`, `setBlockChromeClientData`, `setSendDoNotTrack`, `setBlockWebRTC`.

### Changed
- Updated `getMessageHandler` API method return type.
- `start`, `update` and `setFilteringEnabled` API methods flush browser in-memory cache. This change improve filtering on pages with service workers and inactive tabs.

### Fixed
- Stealth module correctly sets browser privacy network settings based on `blockWebRTC`, `stealthModeEnabled` and `filteringEnabled` options
- unique `eventId` for `FilteringEventType.JsInject` events


## [0.1.4] - 2023-04-18

### Fixed
- The cookies lifetime in Stealth Mode does not apply after the engine is
  started, only after restarting.
- Incorrect work of $cookie rules: incorrect parsing of `domain` and `path`
  fields leads to errors when using browser.cookies and creating multiple
  "child" cookies for each sub-request with a more specific path, e.g. request
  to '/assets/script.js' from '/' will create a new cookie for '/assets/'.
- Wrong expirationDate for cookies.

### Added
- Applying $cookie rules to the requests before sending them to a server in the
  onBeforeSendHeaders hook.


## [0.1.3] - 2023-04-17

### Changed
- Updated `@adguard/extended-css` to `v2.0.52`
- Updated `@adguard/scriptlets` to `v1.9.7`


## [0.1.2] - 2023-04-11

### Added
- Separated export of CssHitsCounter to better tree shaking on external
  applications.


## [0.1.1] - 2023-04-04

## Changed
- Improved injection algorithm for cosmetic rules (js and css).
  logic using the Finite State Machine to avoid double injections with
  the previous boolean flag scheme.
- Set injectScript and injectCss error to debug level.


## [0.1.0] - 2023-03-31

### Changed
- Updated tsurlfilter to v2.0.


## [0.0.68] - 2023-03-24

### Added
- Described event flow scheme for webRequestModule.

### Fixed
- Changed enums according to our guideline.


## [0.0.67] - 2023-03-23

### Fixed
- Order of injecting scripts with setDomSignal.


## [0.0.66] - 2023-03-14

### Fixed
- Executing of html and replace rules for Firefox


## [0.0.65] - 2023-03-10

### Fixed
- Executing of scriptlets rules for Firefox

### Added
- Stricter checking for non local JS rules for Firefox AMO


## [0.0.64] - 2023-03-10

### Changed
- Updated `@adguard/scriptlets` to `v1.9.1`

### Fixed
- Cosmetic rules applying if CssHitsCounter is disabled
- Mark requests from navigation from address bar as first-party requests.


## [0.0.63] - 2023-02-17

### Changed
- Updated `@adguard/extended-css` to `v2.0.51`


## [0.0.62] - 2023-02-10

### Added
- Added cosmetic rules injection in tabs opened before API initialization
### Fixed
- Fix js rule injections via WebRequest API.
- Fix extended css rule injections via content-script on API initialization.
  Content-script wait for engine start before processing.
- Fix css hit counter enabling.
  Now, it is initialized only if `collectHitStats` configuration prop is true.


## [0.0.61] - 2023-02-07

### Added
- Support for browser.windows.onWindowFocusChanged to make browser.tabs.onActivated
  event calls work better when focus changes between windows.


## [0.0.60] - 2023-02-03

### Changed
- Updated `@adguard/extended-css` to `v2.0.49`


## [0.0.59] - 2023-02-03

### Changed
- Updated `@adguard/extended-css` to `v2.0.45`


## [0.0.58] - 2023-02-02

### Fixed
- When opens phishing or malware site, extension will open new tab in the
  standard window with information about blocked domain and possible actions.


## [0.0.57] - 2023-01-20

### Changed
- The order of imports to avoid side effects on tree shaking.
- Made load of AdGuard Assistant lazy to decrease size of content-script bundle.

### Fixed
- Fixed allowlist api rule generation and matching


## [0.0.56] - 2023-01-12

### Fixed
- Fixed simultaneous increase of package numbers for packages tsurlfilter and
  tswebextension in the branch epic
- Fixed working with DNT-headers and GPC from stealth mode
- Fixed js and css injection error handling
- Fixed request events initialization
- Fixed memory leaks in the tests

### Removed
- Previous url from tab's metadata

### Changes

- Merged changed from master branch


## [0.0.47] - 2022-12-27

### Fixed

- Allowlist rule priority

### Added

- Simple support of `$jsonprune`

### Removed

- Unused injectExtCss method in the CosmeticAPI


## [0.0.45] - 2022-12-26

### Fixed
- Recovered work of the blocking scriptlets `click2load.html`

### Changed
- Updated `@adguard/scriptlets` to `v1.7.20`


## [0.0.44] - 2022-12-23

### Added

- Merged changed from master branch

### Removed

- Support of $webrtc rules

### Fixed

- JS and CSS injection error handling
- Request events initialization
