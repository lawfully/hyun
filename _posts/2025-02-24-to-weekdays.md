---
title: frustration with https
categories: journal
---

## https
Problem is, it takes too long for an iteration. Like 24-48 hours. Really. 

No progress. And, for the other site, content is not updated. Although github action goes well. This homepage, too. Great.

No idea how to proceed. So, I have two problems:

1. No domain for the other site, and
2. No push for both.

On the first (`https`) just wait. Let's try to push this one first. OK, pushing this site worked. And, the other one, too. I think it's somehow a glitch on github server. Just back to the start. Back to `https` thing, I mean. What can I do, other than waiting? Just waiting.

`https` trouble may have something to do with `MX` records, as presumably both points to '@'. To test this thinking, I removed `MX` records to point to `mail` instead of `@`. Will it work? On both sides? Let's wait and see. At least, DNS check takes less time. On the email side, it seems working, even after change of the `MX` records.

## github action failure
It's rather annoying. What's the difference between "publishing from the branch" and "github actions"? The documentation, which I should have read earlier, says something about "publishing from branch" should be an easier option than github actions. See [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow). Coming to think about it, that's obvious. And, for some confusing reason, I set up one site one way and the other the other, and apparently both works. Apparently sometimes. 

>As long as it's working, don't touch it.

Right? One of the pains of using [jekyll scholar](https://github.com/inukshuk/jekyll-scholar) I guess.