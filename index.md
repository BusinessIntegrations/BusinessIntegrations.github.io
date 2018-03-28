
# Business Integrations on Github

Business Integrations Ltd is a web design and hosting company in the UK. We specialise in building elegant websites using CMS frameworks.
We started out using Kentico CMS, but are now favouring the open-source Orchard CMS. Using Orchard gives us full access to all functionality and the source code, and a CMS without the licensing restrictions that Kentico has, and also without paying large amounts of money for licenses for extra functionality.

On Github we will be publishing repos of Orchard CMS modules, both third-party ones that we use frequently that we have adapted or modified to our own ends, or that we've written ourselves.

## Approach
We maintain a variety of private git repos (custom and cloned) outside of github and these are where we manage our code, creating branches for bugs and new features etc. 

Periodically, we will ```merge --squash``` them into a BI/public branch and publish that, as we don't want think there's any merit in the details of every internal decision, commit comment and commit history being in the public domain. There may be times of course where we think that might not be the right approach, but for now we'll only make public our general releases.

## Changes we make
Orchard modules are generally created from a command-line tool to scaffold the Visual Studio project. When starting work using a third-party repo we'll generally merge the source with a newly-scaffolded project to ensure that it really is based on the latest version - rather than a project that may well be a number of years old, that has had tweaks here and there to make it 'current version compliant'. This does mean that often there will be changes to many of the core project files (.csproj, .gitignore, web.config etc).

We also apply a set of our own defined coding styles and standards (with the help of Resharper, of course). This includes, but is not limited to:
1. Removing unnecessary usings and project references.
2. Code formatting (based on the Orchard standard, but with extra details added).
3. Class member reordering.
4. Class member naming conventions.
5. Applying C#6 coding styles
6. Applying limited sets of #regions
7. Adding missing Nuget packages (Mvc etc)
8. Replacing hard-coded strings with constants defined in static classes, or using nameof() etc.

Of course, the problem with standards and conventions is that everyone has their own, so we've tried to apply some rigour, standardisation and housekeeping to keep the code tidy without overdoing it. Hope that's OK!

### Useful Links
For more information on [OrchardCMS](http://orchardproject.net/).
Our company [website](http://business-integrations.com).
