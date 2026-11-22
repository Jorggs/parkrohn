# parkrohn

**Browser-based tools for timing parkrun events with a *real* double (or multiple) finish funnel.**

Live site: **[parkrohn.run](https://parkrohn.run)**

parkrohn lets a parkrun split its finishers across two or more separate funnels, each with its own timekeepers and its own run of finish tokens, and then merges everything back into one correct set of results ready for the parkrun EMS (Event Management System).

It was written by Robin Davey and John Jaap of [Preston Park parkrun](https://www.parkrun.org.uk/prestonpark/), first trialled there on 14 June 2025, and has since been used by a number of other parkruns.

> **parkrohn is an independent project. It is not written, endorsed or supported by parkrun.**

---

## Why a "real" double funnel?

A single funnel can only take so many finishers at once. At busy events (Christmas Day, New Year's Day, milestone runs) it backs up, and finishers end up waiting in a queue or ducking between funnels.

A traditional double funnel still uses one timer and one sequence of tokens, so the limitations of token distribution are still the same, but this is ameliorated somewhat by keeping athletes in a queuing system.

A **real** double funnel runs each funnel on its own: its own timekeepers, its own block of tokens (for example 1–499 in Funnel A, 500+ in Funnel B). parkrohn then interleaves the funnels by finish time to produce a single merged result. The home page of the site explains this in more detail with diagrams.

## What's in this repository

Each tool is a single, self-contained HTML file. There is no build step, no server-side code and nothing to install.

| File | What it is |
|---|---|
| `home.html` | Landing page: why a real double funnel, its history and how it works. `/` redirects here. |
| `parkrohn.html` | **The main tool**: the EMS Pre-processing Tool. Load the timer and scanner files for each funnel, fix problems (dropped, swapped or reversed tokens, missing times, funnel duckers), merge the funnels and download files ready to upload to EMS. Sessions can be saved, restored, exported and imported. |
| `user_guide.html` | Step-by-step guide to using parkrohn for single, double and multiple funnels, with screenshots. |
| `news.html` | News, updates and observations from events that have used it. |
| `funnel-simulator.html` | Simulates finishers arriving at single, traditional and real multi-funnel set-ups, to compare queuing and delays. |
| `Multi_Funnel_Splitter.html` | Testing aid: splits real single-funnel data into 2–10 funnels, so the merge process can be practised and tested. |
| `*.png` | Logos, diagrams and screenshots used by the pages above. |
| `.htaccess` | Apache rule on the live host that redirects `/` to `home.html`. Not needed anywhere else. |

## Running it

Download or clone the repository and open any of the HTML files in a modern desktop browser. That's all.

- **All processing happens in your browser.** No results, names or athlete numbers are sent anywhere.
- The tools are designed for a laptop or desktop screen. Small screens are not supported.
- To host your own copy, upload the files to any static web host (or enable GitHub Pages on this repository).

## Using it at your event

Read the [User Guide](https://parkrohn.run/user_guide.html) first. Running a real double funnel needs some planning on the day, not just the software: separate token blocks, timekeepers and scanners for each funnel, and marshals to direct finishers.

If you're thinking of trying it, email **[report@parkrohn.run](mailto:report@parkrohn.run)** and we'll help you get ready.

## Contributing and reporting problems

Bug reports and suggestions are welcome, either as a [GitHub issue](https://github.com/Jorggs/parkrohn/issues) or by email to report@parkrohn.run.

If you change the code, please test it with realistic data before using it at a live event. `Multi_Funnel_Splitter.html` is handy for that. **Please don't commit real parkrunners' names or athlete numbers** in code, comments, sample data or screenshots.

## Licence

Released under the [MIT Licence](LICENSE). You are free to use, copy, modify and share it.

The software is provided **as is, without warranty of any kind**. You use it at your own risk, and you remain responsible for checking your event's results before they are published.

"parkrun" is a trademark of parkrun Global Limited. This project is not affiliated with parkrun.
