# Site Essentials
---
We design and build web sites for clients using OrchardCMS which out-of-the-box doesn't come with some of the core functionality you'd generally expect from a CMS: Sitemaps, FavIcons, SEO etc etc.

Although there appear to be a lot of modules available for Orchard in the gallery, many are out of date, or don't work with the latest version (1.10.2), or are generally no longer supported. 
However, rather than starting from scratch, we took a bunch of third-party modules and reworked them where necessary. We currently use these modules in production websites, and we generally refer to them as our 'Site Essentials' - as they contain functionality we'd generally use in every website.

## Modules
All of these modules have been forked and are available on our main [organisation page](https://github.com/BusinessIntegrations), or from the links below. I've also listed the functional changes/fixes we've made to each module below.

Our approach to code changes is listed on [here](https://businessintegrations.github.io).

The default branch containing our modified code for each is BI\public.

### 1) Cookie Consent: [Mod.CookieConsent](https://github.com/BusinessIntegrations/Mod.CookieConsent)
- Added an Enabled flag in settings to allow this to be toggled on/off.

### 2) Social Media Meta Tags [Om.Orchard.SocialMetaTags](https://github.com/BusinessIntegrations/Om.Orchard.SocialMetaTags)
- Fixed 'artice' typo, removed errant text in settings page.
- Moved admin menu into its own root instead of Settings.

### 3) Google Analytics [Orchard-Simple-Analytics](https://github.com/BusinessIntegrations/Orchard-Simple-Analytics)
- No functional changes introduced.

### 4) Sitemap [Orchard-SiteMap](https://github.com/BusinessIntegrations/Orchard-SiteMap)
- Fixed reliance on deprecated jQuery module.
- Removed redundant import/export code.
- Added an extra route (googlesitemap.xml) for compatibility with one of our previously developed sites.
- Deal with bug when BaseUrl is empty - use request URL instead.
- Any AutoRoute part that is defined as the HomePage is included in the sitemap as the root of the site instead of its original path. (i.e. ~/ instead of ~/HomePage)
- Fixed bug in HomeController where empty enumerable caused an exception.
- Fixed empty columns to display correctly.

### 5) Favicons [Vandelay](https://github.com/BusinessIntegrations/vandelay)
- This module originally contained a lot of unrelated features, most of which we didn't need, so this code was completely reworked to strip out all extraneous features and code. (Sorry Bertrand!)
- Enabled multiple FavIcon definitions to be defined and persisted
- Reuse existing table but persists a JSON string containing all the definitions instead of single media path. 
- Enabled persistence and configuration of the Rel/Type fields to allow for expanded options. 
- Provided a suggestion list of available values for the Rel field. (icon, apple-touch-icon etc)
- Provided a suggestion list of available values for the Type field. (image/icon, image/x-icon etc)

### 6) SEO/Robots.txt [Yaplex.SEO](https://github.com/BusinessIntegrations/Yaplex.SEO)
- Fixed serious bug in SeoOverrideDriver.cs that caused infinite recursion.
- Updated SEO Driver to only update meta-data when displayType=="Detail".
- Added import/export code.
- Moved Robots controller/menu to use driver/site settings instead.
- Added caching service.

### 7) Code Prettify [Devworx.CodePrettify](https://github.com/BusinessIntegrations/Devworx.CodePrettify)
- Other than fixing a small bug (invalid hex in css) no functional changes were made to this module.

