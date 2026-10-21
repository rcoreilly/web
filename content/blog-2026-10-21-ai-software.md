+++
Name = "2026-Oct-21: AI Software: Everyone gets their own toothbrush!"
Date = "2026-10-21"
Categories = ["Blog"]
+++

I am now realizing that I have been a kind of accidental pioneer of the new future that is unfolding with the advent of AI-driven software development:

> Everyone gets to use their own personal software toothbrush!

As in "I'd rather use someone else's toothbrush, than their [fill in the blank]".

This is otherwise known as the **Linux syndrome**: instead of being able to agree on a single way of packaging and distributing Linux, there are a "million" different distributions, that all dilute the potential collective effort expended. Imagine how awesome it could have been, if all that effort had been properly channeled into one coordinated system!

The opposite end of this continuum is Apple, who just makes mostly all the right decisions for you, and makes sure it all works. Mostly...

Except, when their Mail app doesn't have a reasonable keyboard-driven way to file emails into folders. So you need a 3rd party app ([MsgFiler](https://msgfiler.com/)). Which then keeps breaking due to software updates from Apple. And sometimes just fails to work entirely for long stretches of time.

And the fact that there were no decent open source vector graphics drawing apps for the Mac: [Inkscape](https://inkscape.org) was so slow as to be unusable due to its use of a Linux-native GUI framework, and the GUI is over-complex in a [Blender](https://www.blender.org/) kind of way.

So, back when I wrote my first Go-native GUI framework called [GoKi](https://github.com/goki), I coded up my own vector graphics app (grid), and dreamed of being able to write an email client. I also wrote my own version of [emacs](https://www.gnu.org/software/emacs/), because that's what I use every second of every day, and at the time, there was no [VS Code](https://code.visualstudio.com/), and the main options were horribly bloated electron-based apps like [atom](https://github.com/atom/atom). Or emacs itself -- but I honestly never really loved writing elisp...

Once my son Kai joined my team, we wrote the new-improved [CogentCore](https://cogentcore.org) and all those apps got so much better! But, honestly, still not quite up to par with the rising bar of the rest of the widely-used options -- Inkscape got much better, and VS Code came out.. Mail still annoys, but does now finally seem to be working..

But I had managed to make my own personal software (which I'm pretty sure I am the one-and-only user of) entirely functional for my own uses. The critical element of **complete personal control** over exactly how it works, and the ability to fix the most annoying bugs without sitting around **helplessly waiting for someone else to get around to it**, was somehow entirely worth all the effort. Even at the cost of **complete personal responsibility** for all the bugs.

## AI software for everyone!

Fast-forward to what is happening now: with the advent of AI coding tools ("vibe coding"), the number of Go-native GUI frameworks is now proliferating, with a new one being announced seemingly on a daily basis! Here's a listing:

* https://awesome-go.com/gui/
* https://groups.google.com/g/golang-nuts/search?q=GUI (also https://github.com/belluikit/bellui didn't use GUI term)
* some discussion of the state of affairs: https://groups.google.com/g/golang-nuts/c/Cfc58bYFO_8/m/xV0SgQAcCAAJ

And Rust seems to be an even more popular AI coding target, with this project getting recent attention: [Photoshop in Rust](https://www.tomshardware.com/software/video-editing-graphic-design/solo-developer-rebuilds-adobe-creative-suite-in-rust-using-claude-releases-it-free-to-all-targets-100-percent-parity-in-one-month-despite-piracy-claims-and-safety-warnings).

So, projecting forward, it seems that the logical progression will be for each person with sufficient OCD levels to write their own entire software stack, just as I have painstakingly done mainly in the pre-AI era!

> One could reasonably wonder if this is a good use of all the computing resources involved.

I have _always_ had the same question about my individual time allocation on such projects -- but I could justify it based on the "entertainment value" (yeah, I know... such a geek...), plus the fact that it is improving the software that I use for my day job ([emergent](https://github.com/emer)). 

And if you actually try out any of this software, **there are inevitably a lot of bugs!** AI doesn't really change the fact that it takes a huge amount of time and effort to find and fix all those bugs. And with everyone dividing and not conquering these bugs, they just persist...

Yeah, people are, generally speaking, truly inefficient beasts in so many ways.

Maybe it would make sense to try to collaborate more, and get back to some cumulative open source efforts that are really truly awesome and stable etc?

I'm not holding my breath. And meanwhile, I'm now using Claude and my local [[software#AI on MacBook Pro]] to continue to improve my own personal toothbrush. Mmmmm love it!

(note: this website is of course generated by my own personal static website generator, written in CogentCore of course, that translates .md source files into what you're seeing here).

