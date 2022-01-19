My Witcher 3 Mods
=================

This is a little collection of a few mods for Witcher 3 that I put together
for my own use, mostly based on existing W3 mods from [Nexus](https://www.nexusmods.com/witcher3).

modAutoDismantleJunk
--------------------

This one is based on [Auto Manage Items](https://www.nexusmods.com/witcher3/mods/4482),
a mod which causes various inventory-management things to happen when the
user opens up the Bestiary menu.  The main thing I was interested in with
that mod was automatically dismantling "junk" items into their component
crafting parts, without doing all the extra processing that that mod does.

So, this is my own stripped-down version which *just* does that.  The
internals here are actually pretty different -- the mod at Nexus just makes
two passes through your inventory, checking for "junk" items each time,
and converting those to their broken-down parts.  This version will loop
through as many times as it takes (up to a hardcoded limit) to ensure that
any longer "chains" of breaking-down get fully completed.  My version also
waits until the very end to award money for "pure" junk items (which have
no purpose other than to be sold, such as fisstech, etc), and will give at
least 1 crown per item sold.

Ideally, what I'd like is to hook into the inventory pick-up functionality
and do this auto-dismantle right then, rather than letting the items build
up in your inventory, but I struggled to come up with a good implementation
of that in the apparent absence of usable hash/dict/map/whatever objects
in redscript (and also on account of my relative unfamiliarity with both
redscript and the W3 APIs), so I didn't bother pursuing that for too long.
Bestiary menu it is!

modMastercraftsEverywhere
-------------------------

This is based on [Craft All Items](https://www.nexusmods.com/witcher3/mods/378)
and was *originally* a somewhat pared-down version of that mod.  I think over
time I ended up adding a bit more back in, and I suspect that at the moment,
they do pretty much exactly the same thing.  So, probably a bit pointless.  Ah
well.

modNoCrossbowReload
-------------------

This is based on [Semi-Auto and Double Barreled Crossbow](https://www.nexusmods.com/witcher3/mods/830)
but has a much tighter focus, and only implements the semi-autoness.  The
implementation here's actually based on some info found in the discussion
threads on that mod's page, rather than the mod itself.

