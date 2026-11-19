# How I Build My Sports Games

I build college sports dynasty games on my own under Empire Sports Apps. The code is private, so this is a short write-up of how they're made and what I've learned.

| Game | Sport | Stack | Status |
|---|---|---|---|
| [Hardwood Empire](https://apps.apple.com/us/app/hardwood-empire/id6760374401) | College basketball | HTML/JavaScript, Capacitor (iOS and Android) | Hit **#1 in the App Store's Sports and Simulation charts** with no ad spend |
| [Home Run Empire](https://apps.apple.com/us/app/home-run-empire/id6767944614) | College baseball | HTML/JavaScript, Capacitor | Live on iOS |
| Touchdown Empire | College football | Unity and C# | In development |

Together the games have **70,000+ downloads**.

## How they're put together

- **One codebase, every phone.** The basketball and baseball games are web apps wrapped with Capacitor, so one JavaScript codebase ships to iOS and Android.
- **Small, single-purpose modules.** Data, game state, the season simulator, recruiting, the transfer portal, the draft, the offseason and saving each live in their own module. Each module has one job, which makes bugs easier to find.
- **The simulation is separate from the screens.** Games are simulated in plain logic that doesn't know anything about the UI, so I can run thousands of seasons headlessly to test it.
- **Saves are treated like real data.** Every save is versioned and migrated forward when the game updates, so nobody loses a dynasty to an update.

## How I test

- **Headless season audits.** Scripts simulate many full seasons and check that stats, records and player development look like real college sports.
- **Real player feedback.** Reviews, support emails and crash reports go into one triage list, and fixes ship in small updates.
- **Phone builds before release.** Everything gets played on a real device through TestFlight before it goes out.

## What I've learned

1. **Keep it simple first.** The features players love most are the clear ones: recruiting, building a roster and watching a program grow.
2. **Model after what already works.** I study the best sports games and my own best-rated features before designing new ones.
3. **Ship, listen, fix.** Small updates driven by real reviews beat big rewrites.
4. **Use AI as a teammate.** I use Claude to write tests, review code and triage feedback, and I still decide what ships.
