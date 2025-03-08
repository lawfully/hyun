---
title: Notes and Plans
categories: [journal]
---
My wife wants me to be her editor *cum* website/shopping mall manager. When it comes down to what wife says, I don't really have a way to say no; "well..." is the best I can mutter. Plus, after I began using the AI/LLM or whatever it is, it's not like I'm super busy. Finally, I'm not bad at both. I can handle $$\LaTeX$$ and `pandoc` and stuff pretty well, understand the networking--I mean computer sort, not mingling with people for no reason whatsoever--and, yes, I should be honest here, I like those things.

And, I have a sort of *fear of missing out,* not exactly financially, but I'm worried by not doing the leadership and marketing things, I'm missing out my experience of being a human-sort of way. And, as I said earlier, who can say no to your wife? That's an *existential* question.

So, I chatted with the AI yesterday, who was very helpful figuring out what [shopify](https://shopify.com), [beehiiv](https://beehiiv.com) and [substack](https://substack.com) means and what to do about them. It's gonna be a long weekend.

---

By the way, I wanted to try [Zettlr](https://www.zettlr.com/) but it required [electron](https://www.electronjs.org/) 30 despite current [version](https://releases.electronjs.org/) is `35` or something. It's a big headache because it's gonna take about 100GB! My hard disk is limited--sorry--to 500GB and it's going to take about 1/5 of the total. Is it worth it? I don't know. Packages these days are so huge! If I want the most recent (35) and obsolete (30) together, it'll take up half of my hard disk!

**Followup**

```bash
$ yay -Ps
==> Total Size occupied by packages: 26.8 GiB
==> Size of pacman cache /var/cache/pacman/pkg/: 1.3 MiB
==> Size of yay cache /mnt/my/.cache/yay: 94.6 GiB
```

I use 26.8 GiB for all my packages and, the cache size when I *try* to install zettlr (that apparently depends on electron30) reached 94.6 GiB (note I moved my yay cache to a different hard disk mounted in `mnt/my`) and failed for, errors that I can't fathom to resolve:

```bash
error: unresolvable package conflicts detected
error: failed to prepare transaction (conflicting dependencies)
```

I'm giving up, not for want of persistence but disk space. I can't give 100 GiB to try a software. By the way, I learned that I should delete pacman/yay cache periodically, by executing:

```bash
$ yay -Scc
```