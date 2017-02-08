---
layout: lawlog
title: LawLog and LawDiff tools for exploring changes in legal texts
is_project_page: true
---

# What is it?

To me, best way of understanding law is to see how it evolved through multiple revisions, accreting changes and amendments through time. This is second iteration of project to show changes in law text by sequentially comparing historical versions.

I worked on this a some years back (around 2011 actually). The previous version was based on Ruby On Rails, but with a twist of actually executing on JRuby, and deploying to Google AppEngine JVM-based Cloud service (was free hosting at the time!). The current iteration UI is developed on Scala, using Play 2.5 framework.

# Where can I see it?

Please access [https://law.valte.rs](https://law.valte.rs).

The data intake is retrieving law texts from national database via curl, and uses python scripts for cleaning up the html.

Currently my instance of app is simply running on a Raspberry Pi 3 box which sits right next to my router at home. If you find that the site does not respond, please try again in few minutes - I might have brought the instance down to redeploy, etc.

In terms of Scala, the project code is not complicated at all. The interesting part is how little code is actually necessary - how very expressive the language is.

# What is LawDiff?

LawDiff is the little engine behind producing the diffs (while the lawlog is simply a UI wrapper around the diff xml report files). In turn, DaisyDiff does the heavy lifting in terms of applying comparison to body of texts. LawDiff simply configures it to best match specifics legal text.
