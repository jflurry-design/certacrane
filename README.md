# certacrane

Static support, privacy and terms pages for **CertaCrane**, an iPhone and iPad app, published with GitHub Pages. They follow the same layout as `jflurry-design/ledger-site` (Kitchen Table Finance), recolored to the CertaCrane icon palette.

Live site: https://jflurry-design.github.io/certacrane/ (GitHub Pages, main branch)

| Page | URL | Used for |
|---|---|---|
| Support (home) | https://jflurry-design.github.io/certacrane/ | App Store Connect → Support URL |
| Support (alias) | https://jflurry-design.github.io/certacrane/support/ | Forwards to the home page. The app's `SubscriptionLinks.support` uses this URL. |
| Privacy Policy | https://jflurry-design.github.io/certacrane/privacy/ | App Store Connect → Privacy Policy URL; the app's `SubscriptionLinks.privacyPolicy` |
| Terms of Use | https://jflurry-design.github.io/certacrane/terms/ | Optional. The app's `SubscriptionLinks.termsOfUse` points at Apple's Standard EULA. |

## Structure

Plain HTML and CSS: no build step, JavaScript, cookies, analytics or third-party requests.

```
index.html            support + FAQ (site home)
support/index.html    forwards to ../ (keeps the in-app /support/ link working)
privacy/index.html    privacy policy
terms/index.html      Standard EULA link + short terms + safety notice
assets/site.css       light: navy on off-white; dark: crane yellow on navy
assets/icon.svg       app icon (icon/final/svg/icon-light.svg)
assets/fonts/         Figtree + Inter variable fonts (SIL OFL 1.1, licenses included)
.nojekyll             serve files as they are (no Jekyll processing)
```

## Editing

- `<!-- ATTORNEY REVIEW -->` and `<!-- REVIEW -->` comments mark open questions. They don't show on the page, but anyone can read them with View Source, so remove them before publishing.
- When the Privacy or Terms text changes, update the **"Effective"** date.
- Prices, the trial, permission strings and in-app paths must match App Store Connect and the app. Current values (Oct 2026): `craneinspector.pro.yearly` $499/yr and `craneinspector.pro.monthly` $99/mo, in the group "CertaCrane Pro", each with a 7-day free trial and no Family Sharing. There is no free tier.
- The permission strings quoted in `privacy/` are copied word for word from `INFOPLIST_KEY_NS*UsageDescription` in `project.pbxproj`. If those strings change, update the quotes here too.
