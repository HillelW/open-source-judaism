# THE HEBREW CALENDAR

*A Mathematical and Algorithmic Study*

The most sophisticated deterministic algorithm in pre-modern Jewish law — reconciling sun and moon through pure arithmetic, without observation, authority, or communication, continuously since the fourth century.

# Table of Contents

- [Part I: TWO CLOCKS THAT DON'T AGREE](#part-i-two-clocks-that-dont-agree)
  - [The Problem](#the-problem)
  - [What the Moon Actually Does](#what-the-moon-actually-does)
  - [The Observation Era](#the-observation-era)
- [Part II: THE BUILDING BLOCKS](#part-ii-the-building-blocks)
  - [Chalakim: The Unit of Time](#chalakim-the-unit-of-time)
  - [The Molad: Mean New Moon](#the-molad-mean-new-moon)
  - [The Metonic Cycle](#the-metonic-cycle)
- [Part III: THE FOUR POSTPONEMENTS](#part-iii-the-four-postponements)
  - [Lo ADU](#lo-adu)
  - [Molad Zaken](#molad-zaken)
  - [GaTRaD](#gatrad)
  - [BeTUTKaPoT](#betutkapot)
  - [The Interaction of the Dehiyyot](#the-interaction-of-the-dehiyyot)
  - [The Algorithm](#the-algorithm)
  - [Worked Examples](#worked-examples)
  - [What the Dehiyyot Achieve](#what-the-dehiyyot-achieve)
- [Part IV: YEAR TYPES AND THE COMPLETE CALENDAR](#part-iv-year-types-and-the-complete-calendar)
  - [Six Possible Year Lengths](#six-possible-year-lengths)
  - [The Fourteen Keviyyot](#the-fourteen-keviyyot)
  - [The Four Gates](#the-four-gates)
  - [Torah Portions and the Liturgical Year](#torah-portions-and-the-liturgical-year)
- [Part V: THE COMPLETE ALGORITHM](#part-v-the-complete-algorithm)
  - [From Year Number to Complete Calendar](#from-year-number-to-complete-calendar)
  - [Converting Between Hebrew and Gregorian Dates](#converting-between-hebrew-and-gregorian-dates)
  - [Implementation Notes](#implementation-notes)
- [Part VI: SEASONS AND THEIR ARITHMETIC](#part-vi-seasons-and-their-arithmetic)
  - [Tekufat Shmuel](#tekufat-shmuel)
  - [Tekufat Rav Adda](#tekufat-rav-adda)
- [Part VII: THE HISTORY OF THE TRANSITION](#part-vii-the-history-of-the-transition)
  - [From Sanhedrin to Calculation](#from-sanhedrin-to-calculation)
  - [The Evidence of Continued Dispute](#the-evidence-of-continued-dispute)
  - [Maimonides and the Codification](#maimonides-and-the-codification)
- [Part VIII: PRECISION, DRIFT, AND THE LONG VIEW](#part-viii-precision-drift-and-the-long-view)
  - [The Full Cycle](#the-full-cycle)
  - [The Drift](#the-drift)
  - [The Calendar as Engineering](#the-calendar-as-engineering)
- [Part IX: TWO OPEN QUESTIONS](#part-ix-two-open-questions)
  - [Could the Calendar Be Reformed?](#could-the-calendar-be-reformed)
  - [The Return to Observation](#the-return-to-observation)
- [Glossary](#glossary)
- [Bibliography](#bibliography)

# Part I: TWO CLOCKS THAT DON'T AGREE

## The Problem

Imagine you have a meeting every Tuesday at 9:00 a.m. Now imagine the meeting drifts — not by a lot, just eleven minutes earlier each week. For the first month, you barely notice. By the end of the first year, it's shifted by nearly ten hours: your morning meeting now falls just before midnight on Monday. Give it another year and it has slid entirely through the night and back into daylight, landing on Monday afternoon. A third year and it has crept to Monday morning. It takes about three years for the meeting to complete one full circuit of the clock and return roughly to where it started.

That drift is not a thought experiment. It's the actual relationship between the moon's cycle and the solar year, and it is the fundamental problem the Hebrew calendar exists to solve.

The moon goes through a complete cycle of phases — new moon to full moon and back to new moon — in about 29 and a half days.[^1] Twelve of those lunar months add up to roughly 354 days. The solar year, the time it takes the earth to complete one orbit and return to the same point in its seasonal cycle, runs about 365 and a quarter days.[^2] The difference is approximately 11 days per year. Left uncorrected, a calendar of twelve lunar months falls behind the sun by 11 days every year. After three years, the gap is a full month. After nine years, it's a full season. A spring holiday drifts into winter, then autumn, then summer, cycling through the seasons like that meeting sliding around the clock.

Every civilization that has cared about both the moon and the sun has had to reckon with this. The two cycles are incommensurable — you cannot express one as a clean multiple or fraction of the other. There is no number of lunar months that adds up exactly to a number of solar years. The ratio is irrational, not just inconvenient but mathematically irreconcilable.[^3] Any calendar that wants to track both must cheat somehow — must introduce some mechanism that forces alignment where nature provides none.

Civilizations have responded to this problem in three fundamentally different ways.

The first approach: ignore the sun entirely. Build the calendar on the moon alone and let the months drift through the seasons. This is a pure lunar calendar, and the most prominent example is the Islamic calendar.[^4] It runs twelve lunar months per year, every year, with no correction. The result is that Islamic holidays migrate through the seasons over a cycle of about 33 years. Ramadan, the month of fasting, sometimes falls in the long, hot days of summer and sometimes in the short, cool days of winter. The calendar makes no attempt to anchor months to seasons, and that is a feature, not a bug — the theology is one of equality, each season bearing its share of the fast.

The second approach: ignore the moon entirely. Build the calendar on the sun and let the months become arbitrary divisions of the solar year, untethered from any astronomical event. This is a pure solar calendar, and the Gregorian calendar is its most familiar instance.[^5] Its months are roughly 30 or 31 days, bearing no relationship to the lunar cycle. The new moon falls on a different calendar date each month. The full moon wanders. Seasons stay put — December is always winter in the northern hemisphere, July always summer — but the moon becomes decorative, something you notice when it's pretty in the sky but that has no structural role in timekeeping.

The third approach: refuse to choose. Track both. Insist that months follow the moon and that the year follows the sun, and find some way to make those two demands compatible. This is a lunisolar calendar, and it is the hardest problem in calendar design.[^6]

The Hebrew calendar takes the third path, and it does so because the Torah insists on it.

In Exodus, God tells Moses: <span dir="rtl">הַחֹדֶשׁ הַזֶּה לָכֶם רֹאשׁ חֳדָשִׁים רִאשׁוֹן הוּא לָכֶם לְחׇדְשֵׁי הַשָּׁנָה</span> — "This month shall be for you the first of months; it is the first for you of the months of the year."[^7] The word for month, <span dir="rtl">חֹדֶשׁ</span>, shares a root with <span dir="rtl">חָדָשׁ</span>, "new" — it means, at its core, the renewal, the new moon. Months must begin with the new moon. That's the lunar requirement.

But Deuteronomy adds a second command: <span dir="rtl">שָׁמוֹר אֶת חֹדֶשׁ הָאָבִיב וְעָשִׂיתָ פֶּסַח לַה' אֱלֹקֶיךָ</span> — "Observe the month of spring, and make the Passover offering to the Lord your God."[^8] Passover must fall in the spring. Not in whatever season the lunar months happen to have drifted into, but in spring — <span dir="rtl">אָבִיב</span>, the season when barley ripens. That's the solar requirement.

Two clocks, one calendar. The months must follow the moon. The year must follow the sun. And those two cycles, as a matter of mathematics, don't agree. The Talmud makes the consequence explicit: the commandment to keep Passover in its proper season implies that the court must intercalate — must periodically add an extra month to push the lunar calendar back into alignment with the solar year.[^9] Without intercalation, the lunar calendar drifts, and within a few years Passover migrates out of spring. The Torah's two requirements, taken together, demand a mechanism that nature doesn't provide. The calendar must be engineered.

## What the Moon Actually Does

The moon orbits the earth, and the earth orbits the sun, and the interplay of those two motions produces the lunar phases. The time from one new moon to the next — one complete cycle of phases — is called the synodic month.[^10] This is the calendar's fundamental unit. Everything else is built on top of it.

The Talmud records the length of the synodic month with startling precision. The value, as codified by Maimonides: 29 days, 12 hours, and 793 <span dir="rtl">חֲלָקִים</span> (parts).[^11]

That unit, the <span dir="rtl">חֵלֶק</span> (plural <span dir="rtl">חֲלָקִים</span>), is the calendar's secret weapon. One hour is divided into 1,080 <span dir="rtl">חֲלָקִים</span>. Each <span dir="rtl">חֵלֶק</span> is therefore 1/1080 of an hour, or 3 and 1/3 seconds. The choice of 1,080 is not arbitrary — it is a small miracle of practical engineering. The number 1,080 has an extraordinary number of divisors: 2, 3, 4, 5, 6, 8, 9, 10, 12, 15, 18, 20, 24, 27, 30, 36, 40, 45, 54, 60, 72, 90, 108, 120, 135, 180, 216, 270, 360, 540, and 1,080 itself. Nearly any fraction you might want to express comes out as a whole number of <span dir="rtl">חֲלָקִים</span>. One-third of an hour is 360 <span dir="rtl">חֲלָקִים</span>. One-quarter is 270. One-fifth is 216. One-eighth is 135. One-tenth is 108.

This matters because the entire Hebrew calendar is computed using integer arithmetic — whole numbers of days, hours, and <span dir="rtl">חֲלָקִים</span>. There are no rounding errors. No approximations that accumulate drift. No fractions that fail to terminate. Every intermediate calculation in the calendar algorithm produces exact whole-number results. The choice of 1,080 as the subdivision of the hour is what makes this possible. It is a unit designed for computation, centuries before the word "computation" existed.

So: the synodic month is 29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span>. Converting to decimal days: 12 hours is half a day (0.5), and 793 <span dir="rtl">חֲלָקִים</span> is 793/1080 of an hour, which is 793/25920 of a day (approximately 0.030594). The total: 29.530594 days.

The modern astronomical value for the mean synodic month, determined by centuries of telescopic observation and refined by atomic clocks and laser ranging, is approximately 29.530589 days.[^12] The difference between the traditional value and the modern measurement is about 0.000005 days per month — roughly 0.4 seconds. In the time it takes you to blink, the discrepancy between the ancient value and the modern one has already come and gone.

Over one year (about 12.4 synodic months), the accumulated error is less than 5 seconds. Over a century, it's about 8 minutes. The value is not perfect — no fixed value can be, since the actual length of the synodic month varies slightly from one lunation to the next due to the eccentricities of the lunar and terrestrial orbits. But as a mean value, as an average designed to track the moon's behavior over long periods, it is extraordinarily good. Whoever established it — and the historical question of exactly when and where this value originated remains a matter of scholarly debate — got it right to a degree that compels a certain awe.[^11]

## The Observation Era

The fixed calendar that Jews use today is a relatively late development. For most of the biblical and Talmudic periods, the Hebrew calendar was not calculated at all. It was observed.

The Mishnah, compiled around 200 CE, preserves a detailed account of how this worked.[^14] The system centered on the new moon. Astronomically, the new moon — the moment of conjunction, when the moon passes between the earth and sun — is invisible. What is visible, a day or two later, is the first thin crescent of the waxing moon, appearing low in the western sky just after sunset. That crescent was the signal.

On the thirtieth day after the previous month had been declared, the Sanhedrin — the supreme rabbinical court in Jerusalem — convened to receive testimony. Witnesses who had spotted the new crescent would come before the court and be examined. The questioning was rigorous: In which direction was the crescent facing? How high was it above the horizon? How wide was the crescent? What was its orientation relative to the sun? The court knew what answers were astronomically plausible and which were not. A witness who described the crescent pointing the wrong way, or appearing in an impossible part of the sky, would be dismissed.

Rabban Gamliel, who led the Sanhedrin in the late first and early second century CE, kept visual aids — diagrams of the moon in its various phases, displayed on a tablet and on the wall of his upper chamber — and would show them to witnesses: "Did it look like this, or like this?"[^15] This is, in essence, a forensic identification protocol. The court was not simply asking "did you see the moon?" but "describe precisely what you saw, and let us determine whether your observation is consistent with what the moon should have looked like."

If the court accepted the testimony, the new month was declared: "<span dir="rtl">מְקֻדָּשׁ</span>!" — "Sanctified!" And then the news had to travel. Initially, the system used signal fires. A chain of beacons was lit from the Mount of Olives in Jerusalem, relayed from hilltop to hilltop: to Sartaba, to Grofina, to Hauran, and onward, until the flames reached the Jewish communities of Babylonia. The Mishnah describes how each station would wave its torch back and forth and up and down until it could see the next station doing the same, confirming receipt.

But the system was sabotaged. The Cutheans — Samaritans, or perhaps other hostile groups — began lighting decoy fires on the wrong nights, sowing confusion among distant communities. The rabbis were forced to abandon the beacon system and switch to human messengers. Messengers were reliable but slow. Communities close to Jerusalem — within a few days' travel — received the message in time to know which day had been declared as the first of the new month. But distant communities, particularly those in Babylonia, sometimes could not receive the messenger before the festivals arrived.

The solution was pragmatic and has left a permanent mark on Jewish practice. Distant communities, uncertain which of two possible days was the true festival date, observed both. This is the origin of <span dir="rtl">יוֹם טוֹב שֵׁנִי שֶׁל גָּלֻיּוֹת</span> — the second day of festivals observed in the diaspora. It is not a theological elaboration or a mystical doubling. It is an information-lag artifact, a workaround for the speed of pre-modern communication, frozen into law long after the original uncertainty was resolved.

The court's power over the calendar was understood to be absolute — and not merely in the administrative sense that someone has to make the call. The Talmud tells a famous story that makes the stakes vivid. Rabbi Yehoshua, a leading sage, calculated that the Sanhedrin under Rabban Gamliel had declared the wrong day for Rosh Hashanah. By Rabbi Yehoshua's reckoning, the day the court had designated as the first of Tishrei was off by a day, which meant Yom Kippur — the most solemn day of the year, when carrying and handling money are strictly forbidden — fell on a different date than the court had declared. Rabban Gamliel sent Rabbi Yehoshua an order: appear before me, carrying your staff and your money-belt, on the day that falls as Yom Kippur by your own calculation.

This was not a small request. It was a demand that Rabbi Yehoshua publicly desecrate what he believed to be Yom Kippur — to carry objects on a day his own scholarship told him was holy. Rabbi Akiva, consoling him, pointed to the verse in Leviticus: "These are the appointed times of the Lord... which you shall proclaim" — the emphasis on *you*, meaning the court. The appointed times are whatever the court declares them to be, even if the court is mistaken. Rabbi Yehoshua went. He appeared before Rabban Gamliel carrying his staff and his money. And Rabban Gamliel stood, kissed him on the head, and said: "Come in peace, my teacher and my student — my teacher in wisdom, and my student because you accepted my ruling."

The message embedded in this story is foundational: the Hebrew calendar is a legal institution, not an astronomical one. The court's declaration is not a report about when the moon appeared. It is an act of law that defines when the month begins. If the court says today is the first of the month, then today is the first of the month — even if the moon disagrees, even if the best astronomer in the room can prove otherwise. The calendar is not discovered; it is declared.

This observation-based system worked well for centuries. It was flexible — the court could add a leap month whenever the seasons seemed to demand it, adjusting on the fly — and it was authoritative, backed by the prestige and power of the Sanhedrin. But it had dependencies. It required a functioning court with recognized jurisdiction. It required witnesses willing and able to travel to Jerusalem. It required a communication network capable of distributing the court's decisions. It required, in short, a stable institutional infrastructure centered on the Land of Israel.

By the fourth century CE, that infrastructure was collapsing. Roman persecution was intensifying. The Sanhedrin's authority was eroding. The patriarch Hillel II, according to tradition, saw that the observation-based system could not survive much longer and took a radical step: he published the rules of the fixed calendar, making the computation public so that any community, anywhere, could determine the calendar independently.[^13] The calendar would no longer require witnesses, signal fires, messengers, or a court. It would run on arithmetic alone — a self-executing algorithm that produces the same answers a properly functioning Sanhedrin would have reached, mechanically, without human judgment, for as long as anyone cares to compute it.

How that algorithm works — the specific rules that turn the molad, the <span dir="rtl">חֲלָקִים</span>, and the 19-year cycle into a functioning calendar — is the subject of Part II.

---

---

# Part II: THE BUILDING BLOCKS

Every calendar is a machine built from parts. The Gregorian calendar's parts are familiar: the 24-hour day, the 365-day year, the leap-day correction every four years (with its own correction every hundred years, and a correction to the correction every four hundred years). These are approximations — rounded values that accumulate small errors and periodically need patching.

The Hebrew calendar takes a different approach. It is built from three mathematical primitives that, once understood, generate the entire system through exact arithmetic. No rounding, no patching, no accumulated drift within the system's own terms. The three primitives are: a unit of time called the *chelek*, a formula for the mean new moon called the *molad*, and a 19-year pattern called the Metonic cycle.

## Chalakim: The Unit of Time

The smallest unit of time in the Hebrew calendar is the *chelek* (<span dir="rtl">חלק</span>, plural *chalakim*, "parts"), defined as one 1,080th of an hour — about 3⅓ seconds.[^16] That denominator is not arbitrary. It is the product of a carefully chosen set of small primes: 1,080 = 2³ × 3³ × 5. This makes it spectacularly divisible. The number 1,080 has exactly 32 divisors:

| | | | | | | | |
|---|---|---|---|---|---|---|---|
| 1 | 2 | 3 | 4 | 5 | 6 | 8 | 9 |
| 10 | 12 | 15 | 18 | 20 | 24 | 27 | 30 |
| 36 | 40 | 45 | 54 | 60 | 72 | 90 | 108 |
| 120 | 135 | 180 | 216 | 270 | 360 | 540 | 1080 |

A practical consequence: virtually any fraction you need to express in calendar arithmetic comes out as a whole number of chalakim. One-third of an hour? 360 chalakim, exact. One-quarter? 270. One-fifth? 216. One-eighth? 135. No remainders, no decimals, no rounding errors. The calendar's designers chose 1,080 precisely because they needed a unit fine enough for astronomical precision but divisible enough to keep the arithmetic clean.

Here are the key conversions that govern the system:

| Unit | Chalakim |
|------|----------|
| 1 hour | 1,080 |
| 1 day | 25,920 |
| 1 week | 181,440 |
| 1 lunar month | 765,433 |

That last number deserves attention. The calendar's lunar month — the interval between one mean new moon and the next — is defined as exactly 29 days, 12 hours, and 793 chalakim. In chalakim: 29 × 25,920 + 12 × 1,080 + 793 = 751,680 + 12,960 + 793 = 765,433.[^17] This is a fixed constant, not an average recalculated each month. Every single month in the Hebrew calendar is exactly this long — at least from the perspective of the molad calculation.

To appreciate what this buys you, contrast it with the Gregorian calendar. The Julian year is 365.25 days, handled by adding a leap day every four years. The Gregorian refinement drops three leap days every 400 years. These are approximations: rounded values selected to keep the error tolerably small over human timescales. The Hebrew calendar never rounds. It works entirely in chalakim, and every intermediate calculation comes out as a whole number. The difference is like measuring with a ruler marked to the nearest centimeter versus one marked in fractions of a millimeter. The Hebrew calendar chose the finer ruler and never needed to approximate.[^18]

There is one caveat. The calendar's lunar month of 29 days, 12 hours, 793 chalakim corresponds to 29.53059 days. The modern measured value of the mean synodic month is 29.53059 days — the same to six significant figures.[^19] But the two are not identical. The calendar's value is fixed by definition; the astronomical value drifts over centuries as tidal interactions between the earth and moon gradually slow the system. The calendar cannot track this drift because it has no mechanism for updating its fundamental constant. For the first several thousand years of the calendar's use, the discrepancy is negligible — less than half a second per month. Over longer timescales, it matters. This is a problem for Part VIII.

## The Molad: Mean New Moon

The *molad* (<span dir="rtl">מולד</span>, "birth") is the calculated moment of the mean conjunction — the average instant when the moon passes directly between earth and sun, becoming invisible from earth. It is the mathematical heartbeat of the calendar: a perfectly regular clock that ticks once every 29 days, 12 hours, and 793 chalakim.[^20]

Three things the molad is *not*. It is not the actual astronomical conjunction, which varies from the mean by up to 14 hours in either direction due to the eccentricities of the lunar orbit. It is not the first visible crescent, which appears one to two days after the conjunction depending on latitude, season, and atmospheric conditions. And it is not an observation — nobody looks at the sky to determine the molad. It is a pure mathematical abstraction: given the molad of any month, you can compute the molad of every other month by adding or subtracting multiples of the fixed interval. The calculation is the same whether you are computing forward to the year 10,000 or backward to the epoch.

The epoch — the starting point from which all moladot are reckoned — is the molad of Tishrei of Year 1 of the Hebrew calendar. It carries the mnemonic name BaHaRaD (<span dir="rtl">בהר״ד</span>), formed from the Hebrew-letter numerals of its three components:[^21]

- <span dir="rtl">ב</span> (bet) = Day 2 of the week (Monday, or more precisely, the Hebrew day beginning at 6 PM on Sunday evening)
- <span dir="rtl">ה</span> (heh) = 5 hours after the start of the day (i.e., 11 PM Sunday night)
- <span dir="rtl">ר״ד</span> (resh-dalet) = 204 chalakim (about 3 minutes and 24 seconds past 11 PM)

So BaHaRaD places the primordial molad at approximately 11:03 PM on a Sunday night. Year 1 of the Hebrew calendar corresponds to 3761 BCE — long before anyone was using this system. The epoch was back-calculated to create a consistent reference point anchored to the traditional date of creation.[^22]

The molad formula is simple. To find the molad of any month, count the number of elapsed months since the epoch and multiply by the month-length (29d 12h 793p). Add the result to BaHaRaD. Since every step uses integer arithmetic in chalakim, no precision is ever lost.

Here is the algorithm in full:

> **Algorithm: COMPUTE MOLAD OF TISHREI**
>
> **Input:** Hebrew year *Y*
>
> **Step 1 — Count elapsed months.**
> Let *N* = *Y* − 1 (the number of elapsed years since the epoch).
> Divide *N* by 19 to find complete Metonic cycles and the remainder.
> Let *cycles* = ⌊*N* / 19⌋
> Let *r* = *N* mod 19
> Each complete cycle contains exactly 235 months.
> For the remaining *r* years, count 12 months per ordinary year and 13 per leap year, where leap years fall at cycle positions 3, 6, 8, 11, 14, 17, and 19.
> Let *M* = *cycles* × 235 + (months in the partial cycle)
>
> **Step 2 — Compute the molad by components.**
> Chalakim: *M* × 793 + 204. Divide by 1,080; the quotient carries into hours, the remainder is the chalakim of the molad.
> Hours: *M* × 12 + 5 + carry from chalakim. Divide by 24; the quotient carries into days, the remainder is the hour of the molad.
> Days: *M* × 29 + 2 + carry from hours. Take mod 7; the remainder is the day of the week (1 = Sunday through 7 = Shabbat; if the remainder is 0, the day is Shabbat).
>
> **Output:** The molad falls on day *d*, at *h* hours and *p* chalakim after 6 PM of the preceding evening.

The beauty of this method is that Steps 1 and 2 require nothing beyond multiplication, addition, and division with remainder — operations a student can perform with a pencil, even for dates thousands of years in the future. The calendar carries no lookup tables, no astronomical observations, no corrections. Everything flows from one constant (the month-length) and one starting point (BaHaRaD).[^23]

### Worked Example: Molad of Tishrei 5787

The Hebrew year 5787 begins in the fall of 2026. Let us compute its molad.

**Step 1.** The number of elapsed years is *N* = 5,786. Dividing by 19: 5,786 = 304 × 19 + 10, so there are 304 complete Metonic cycles and 10 remaining years. The 304 complete cycles contribute 304 × 235 = 71,440 months. For the 10 remaining years (positions 1 through 10 in the current cycle), the leap years at positions 3, 6, and 8 each contribute 13 months; the other 7 years contribute 12 each. That gives 7 × 12 + 3 × 13 = 84 + 39 = 123 months. Total elapsed months: *M* = 71,440 + 123 = 71,563.

**Step 2.** Now the component arithmetic:

| Component | Calculation | Carry | Remainder |
|-----------|-------------|-------|-----------|
| Chalakim | 71,563 × 793 + 204 = 56,749,459 + 204 = 56,749,663 | 52,545 hours | 1,063 chalakim |
| Hours | 71,563 × 12 + 5 + 52,545 = 858,756 + 52,550 = 911,306 | 37,971 days | 2 hours |
| Days | 71,563 × 29 + 2 + 37,971 = 2,075,327 + 37,973 = 2,113,300 | — | mod 7 = 0 → day 7 |

**Result:** The molad of Tishrei 5787 falls on day 7 (Shabbat), 2 hours, 1,063 chalakim. Translating: Shabbat begins at 6 PM Friday evening; 2 hours later is 8:00 PM; 1,063 chalakim is approximately 59 minutes and 3 seconds. So the molad occurs at roughly 8:59 PM on Friday evening, September 11, 2026.[^24]

A quick sanity check: September 11, 2026 is indeed a Friday. The Hebrew day of Shabbat begins Friday at sunset, so a Friday-evening molad falling on Hebrew Shabbat is consistent. Rosh Hashanah 5787, after the postponement rules discussed in Part III are applied, falls on Saturday, September 12, 2026.

Notice what did not happen anywhere in this calculation: no decimal arithmetic, no rounding, no table lookups, no approximations. The answer is exact in the calendar's own terms. A different operator performing the same steps with the same inputs will always get the same result, now and a thousand years from now. That is the molad's core design achievement.

## The Metonic Cycle

A purely lunar calendar — twelve months of alternating 29 and 30 days — produces a year of about 354 days, roughly 11 days short of the solar year. After three years, the calendar is a full month behind the sun. After nine years, it has slipped by a whole season. This is the Islamic calendar's design: its months migrate through the solar year, and Ramadan moves from summer to winter and back over a roughly 33-year cycle. For a calendar that needs Passover in spring and Sukkot in autumn, this will not do.[^25]

The solution is intercalation — adding a thirteenth month in some years to pull the lunar calendar back into alignment with the solar year. The question is: how often, and in what pattern? Add a leap month too frequently and the holidays overshoot their season; too rarely and they fall behind. The answer turns on a coincidence of celestial mechanics so precise it borders on the uncanny.

Nineteen solar years and 235 lunar months are almost exactly the same length.

Using the calendar's own values: 235 months × 29.53059 days = 6,939.69 days. Nineteen solar years (using the calendar's implicit value of 365.2468 days per year) = 6,939.69 days. The match is extraordinary — the two periods agree to within about two hours over a span of nearly 6,940 days.[^26]

This means that if you distribute exactly 7 additional months across a 19-year cycle — making 7 of the 19 years "leap years" with 13 months instead of 12 — the total number of months in those 19 years is 12 × 12 + 7 × 13 = 144 + 91 = 235. The lunar and solar cycles realign at the end of every cycle, and the calendar stays anchored to the seasons indefinitely. Or nearly so: that residual two-hour discrepancy does accumulate, and we will return to its consequences in Part VIII.

### Which Years Are Leap Years?

The seven leap years in each 19-year cycle fall at positions 3, 6, 8, 11, 14, 17, and 19. The traditional Hebrew mnemonic is GUCHADZaT (<span dir="rtl">גו״ח אדז״ט</span>), constructed from the numerical values of the Hebrew letters:[^27]

| Letter | Value | Cycle Position |
|--------|-------|---------------|
| <span dir="rtl">ג</span> (gimel) | 3 | 3 |
| <span dir="rtl">ו</span> (vav) | 6 | 6 |
| <span dir="rtl">ח</span> (chet) | 8 | 8 |
| <span dir="rtl">א</span> (aleph) | 1 (+10) | 11 |
| <span dir="rtl">ד</span> (dalet) | 4 (+10) | 14 |
| <span dir="rtl">ז</span> (zayin) | 7 (+10) | 17 |
| <span dir="rtl">ט</span> (tet) | 9 (+10) | 19 |

The first three letters encode single-digit positions directly. The last four, read with an implicit tens digit, encode positions in the second half of the cycle. To determine whether a given Hebrew year *Y* is a leap year, compute (*Y* − 1) mod 19 + 1 to find its position in the current Metonic cycle, and check whether that position appears in GUCHADZaT.

These seven positions are not arbitrary. Look at the gaps between consecutive leap years, wrapping around from position 19 back to position 3 of the next cycle: 3, 3, 2, 3, 3, 3, 2, then 3 again (from 19 to the next 3). The pattern is composed entirely of intervals of 2 and 3 — and it distributes the seven leap years as uniformly as possible across the 19-year span. You cannot do better. Any rearrangement would create a larger maximum gap between leap years, allowing the lunar calendar to drift further from the solar year before the next correction. The GUCHADZaT sequence minimizes this worst-case seasonal drift.[^28]

This is a problem in combinatorial optimization, though the calendar's designers would not have used that language. Given 19 slots and 7 items to place, the most uniform distribution produces gaps of either ⌊19/7⌋ = 2 or ⌈19/7⌉ = 3, with no two consecutive short gaps and no three consecutive long gaps. GUCHADZaT satisfies these constraints exactly. In modern terms, it is a Bresenham-like distribution — the same algorithm a computer uses to draw a straight line on a pixel grid, distributing the "steps" as evenly as possible across the available slots.

### Historical Note

The 19-year lunisolar cycle was described by the Greek astronomer Meton of Athens in 432 BCE, and is known to modern astronomy as the Metonic cycle in his honor. Babylonian astronomers appear to have known the cycle considerably earlier; cuneiform tablets from the reign of Nabonassar (747 BCE) suggest systematic use of a 19-year intercalation pattern. Whether the Jewish tradition discovered the cycle independently or adopted it from Babylonian practice during or after the exile is debated among scholars, with strong arguments on both sides.[^29]

Within Jewish sources, the 19-year cycle appears in Pirkei de-Rabbi Eliezer, chapter 8, which states that the sun completes its great cycle in 19 years. The Talmud in tractate Sanhedrin discusses the intercalation of months and treats the pattern as established practice, though the Talmudic-era calendar still relied partly on court declarations rather than pure calculation.[^30] By the time of Maimonides, the fixed calendar was fully codified, and the Metonic cycle's parameters were presented as a system of settled law.

The transition from an observational calendar — in which the Sanhedrin declared new months based on witness testimony of the new crescent — to the fixed calculated calendar is itself a rich story, involving questions of authority, diaspora communication, and the limits of astronomical knowledge. But that story belongs to the calendar's history, not its mathematics. For our purposes, what matters is that the Metonic cycle, however it was discovered, provides a framework of remarkable precision: 235 months per 19 years, with 7 leap years placed at positions that minimize seasonal drift.

### The Residual Error

The Metonic cycle is very good. It is not perfect. Using modern values for the tropical year (365.24219 days) and the calendar's month-length (29.53059 days), 235 months exceed 19 tropical years by approximately 2 hours and 7 minutes. This means the calendar runs slightly slow against the sun — about 6 minutes and 41 seconds per year, or one full day every 216 years. After a millennium, the holidays arrive about 4–5 days later in the solar year than they did when the calendar was fixed. After two millennia, the shift approaches 9 days.

For now, this drift is a footnote. Over the span of time the fixed calendar has been in use — roughly 1,600 years — the accumulated shift is real but not yet large enough to push the holidays out of their mandated seasons in most years. But the drift is monotonic: it always goes in the same direction, and it never self-corrects. The calendar has no built-in mechanism for recalibration. Part VIII will examine when this becomes a halakhic problem and what, if anything, can be done about it.

---

With chalakim, the molad, and the Metonic cycle in hand, the calendar's mathematical foundation is complete. These three primitives — a fine-grained unit of time, an epoch with a formula for the mean new moon, and a 19-year intercalation pattern — are sufficient to determine the molad of Tishrei for any Hebrew year, past or future. From the molad of Tishrei, in principle, we could fix the date of Rosh Hashanah and build the rest of the year's calendar around it.

In practice, we cannot — not yet. Because the Hebrew calendar imposes four rules that override the molad and push Rosh Hashanah away from its calculated date, sometimes by as much as two days. These are the *dechiyot*, the postponement rules, and they are the subject of Part III. They are also, by wide consensus, the most counterintuitive feature of the entire system.

---

# Part III: THE FOUR POSTPONEMENTS

You have a date for the molad of Tishrei. You know the day of the week, the hour, and the fractional parts. A reasonable person might assume that Rosh Hashanah falls on that day. It does not — or rather, it might not. Between the molad and the actual first day of Tishrei stand four rules called the <span dir="rtl">דחיות</span> (*dehiyyot*, "postponements"), and they can push Rosh Hashanah forward by one or even two days.

The dehiyyot are the most counterintuitive feature of the fixed calendar. Everything else follows from astronomy and arithmetic: the synodic month, the 19-year cycle, the molad calculation. The dehiyyot are different. They are constraint rules — filters imposed on top of the astronomical calculation to ensure the resulting calendar satisfies halakhic requirements and avoids impossible year lengths. Think of them as the calendar's integrity checks: the molad proposes a date, and the dehiyyot accept or reject it.

There are exactly four. Two are straightforward. Two require walking through arithmetic that would make a fine examination problem. All four, once understood, reveal something about the deep structure of the calendar — the way astronomical cycles, liturgical needs, and number theory interlock into a system that has run without correction for over a millennium.

## Lo ADU

<span dir="rtl">לא אד״ו ראש</span> — "Rosh [Hashanah shall] not [fall on] ADU." The letters <span dir="rtl">א</span>, <span dir="rtl">ד</span>, and <span dir="rtl">ו</span> represent their numerical values: 1 (Sunday), 4 (Wednesday), and 6 (Friday). Rosh Hashanah is forbidden from falling on any of these three days.[^31]

Three forbidden days. Three halakhic reasons. Each one traces back to a collision between the calendar and Shabbat.

**Sunday forbidden.** If Rosh Hashanah were Sunday, then Hoshanah Rabbah — the 21st of Tishrei, the seventh day of Sukkot — would fall on Shabbat. On Hoshanah Rabbah, the liturgy requires beating bundles of willow branches against the ground (<span dir="rtl">חיבוט ערבה</span>), a practice that cannot be performed on Shabbat.[^32] Pushing Rosh Hashanah from Sunday to Monday solves the problem: Hoshanah Rabbah lands on Sunday instead.

**Wednesday forbidden.** If Rosh Hashanah were Wednesday, Yom Kippur (the 10th of Tishrei) would fall on Friday. A person who dies on Friday afternoon cannot be buried until after Shabbat — burial is forbidden on both Yom Kippur and Shabbat, creating two consecutive days during which the dead must wait. Additionally, food preparation for the Shabbat meals is impossible during the Yom Kippur fast.[^33] Rosh Hashanah moves to Thursday.

**Friday forbidden.** If Rosh Hashanah were Friday, Yom Kippur would fall on Sunday. The burial problem recurs in reverse: a person who dies on Shabbat cannot be buried until Monday — Shabbat forbids it, and Yom Kippur immediately follows. Fresh vegetables and other perishable foods prepared before Shabbat would not survive to Monday's post-fast meal.[^34] Rosh Hashanah moves to Shabbat.

The upshot: Rosh Hashanah can only fall on Monday, Tuesday, Thursday, or Shabbat. Four days out of seven. The calendar year has exactly four possible starting days, and every other holiday's day of the week follows from that starting point.

This deterministic cascade is captured in a beautiful mnemonic called <span dir="rtl">א״ת ב״ש</span> (AT BASH), recorded in the Tur and codified in the Shulchan Aruch.[^35] The name refers to the traditional letter-pairing cipher where the first letter of the alphabet maps to the last, the second to the second-to-last, and so on. Applied to the calendar, it works like this: take the first day of Pesach, and count forward through the days of the Pesach festival. Each day corresponds — via the AT BASH letter pairs — to another holiday that falls on the same day of the week.

| Pair | Day of Pesach | Corresponding Holiday | Same Day of Week? |
|------|--------------|----------------------|-------------------|
| <span dir="rtl">א״ת</span> | 1st day (15 Nisan) | Tisha B'Av (9 Av) | Always[^36] |
| <span dir="rtl">ב״ש</span> | 2nd day (16 Nisan) | Shavuot (6 Sivan) | Always[^37] |
| <span dir="rtl">ג״ר</span> | 3rd day (17 Nisan) | Rosh Hashanah (1 Tishrei of the following year) | Always |
| <span dir="rtl">ד״ק</span> | 4th day (18 Nisan) | <span dir="rtl">קריאת התורה</span> / Simchat Torah (23 Tishrei, diaspora) | Always |
| <span dir="rtl">ה״צ</span> | 5th day (19 Nisan) | <span dir="rtl">צום</span> / Yom Kippur (10 Tishrei of the following year) | Always |
| <span dir="rtl">ו״פ</span> | 6th day (20 Nisan) | <span dir="rtl">פורים</span> / Purim (14 Adar of the same year) | Always |

The letters are abbreviations: <span dir="rtl">ת</span> for Tisha B'Av, <span dir="rtl">ש</span> for Shavuot, <span dir="rtl">ר</span> for Rosh Hashanah, <span dir="rtl">ק</span> for <span dir="rtl">קריאת התורה</span> (the Torah reading of Simchat Torah), <span dir="rtl">צ</span> for <span dir="rtl">צום</span> (fast, i.e., Yom Kippur), and <span dir="rtl">פ</span> for Purim.

Why does this work? Because the intervals between these holidays, measured in days, are all divisible by seven. The 1st day of Pesach to Tisha B'Av spans exactly 112 days (16 weeks). The 2nd day of Pesach to Shavuot spans exactly 49 days (7 weeks — the Omer count itself). And so on for each pair.[^38] The calendar's fixed month lengths lock these relationships into place. Once you know the day of the week for Pesach, every other holiday's weekday is determined.

The mnemonic is more than a parlor trick. It means the entire liturgical year is fully constrained by a single piece of information: the day of the week on which Rosh Hashanah falls. Lo ADU restricts that to four possibilities. Four starting days produce four families of year layouts. (The actual number of distinct year types is larger — fourteen — because month-length variations within each starting day create further subdivisions. But the weekday skeleton is always one of four.)

## Molad Zaken

<span dir="rtl">מולד זקן</span> — the "old molad." If the molad of Tishrei occurs at or after 18 hours into the Hebrew day (which is noon in civil time, since the Hebrew day begins at 6:00 PM), Rosh Hashanah is postponed to the following day.[^39]

The threshold is sharp: 18 hours, 0 chalakim. A molad at 17 hours and 1079 chalakim stays put. A molad at 18 hours and 0 chalakim moves. There is no grey zone.

The name "old molad" points to the rule's origin. In the era of observation-based calendar setting, the Sanhedrin declared a new month when witnesses testified to seeing the thin crescent of the new moon in the western sky just after sunset. For the crescent to be visible on a given evening, the conjunction (molad) had to occur long enough before sunset for the moon to separate from the sun by a visible angle. If the molad happened at noon or later, the moon would not yet be visible that evening — the angular separation would be too small.[^40] The earliest the new crescent could appear would be the *following* evening, which belongs to the *following* day in Hebrew reckoning.

The fixed calendar preserves this logic even though no one is watching the sky anymore. The molad zaken rule maintains the fiction — or perhaps the memory — that the calendar tracks visible crescents rather than mean conjunctions. It is one of several places where the fixed calendar encodes the practices of the observational era into arithmetic rules, a kind of fossilized astronomy.

When molad zaken pushes Rosh Hashanah forward by one day, the new date might land on a day forbidden by Lo ADU. In that case, it pushes forward again. The two rules cascade: molad zaken first, then Lo ADU. A molad on Saturday at 18 hours or later pushes to Sunday, but Sunday is ADU, so it pushes again to Monday — a net postponement of two days.[^41]

A historical note. In 921–922 CE, the Palestinian scholar Aaron ben Meir ignited a calendar crisis by arguing that the molad zaken threshold should not be 18 hours exactly, but rather 18 hours minus 642 chalakim — meaning the postponement should trigger about 35 minutes and 40 seconds earlier than the accepted practice.[^42] The difference sounds trivial. It was not. In certain years, ben Meir's threshold and the standard threshold gave different results, causing communities in the Land of Israel and Babylonia to celebrate Pesach and Rosh Hashanah on different days. Rav Saadiah Gaon led the Babylonian opposition. The dispute lasted roughly two years before the Babylonian reckoning prevailed, but it left behind a vivid demonstration of how small a change in one parameter can fracture an entire calendar system.[^43] The full story belongs in Part VII.

## GaTRaD

<span dir="rtl">גטר״ד</span> — the name is an acronym: <span dir="rtl">ג</span> = 3 (Tuesday), <span dir="rtl">ט</span> = 9 (hours), <span dir="rtl">ר״ד</span> = 204 (chalakim). The rule: in a non-leap (ordinary) year, if the molad of Tishrei falls on Tuesday at or after 9 hours and 204 chalakim — that is, 3:11:20 AM Tuesday morning in civil time — Rosh Hashanah is postponed.[^44]

Postponed to where? Not to Wednesday. Wednesday is ADU. So Rosh Hashanah jumps to Thursday — a net shift of two days.

The name tells you the threshold. The reason requires arithmetic. Here is the problem GaTRaD solves:

An ordinary year consists of 12 lunations: 12 × (29 days, 12 hours, 793 chalakim) = 354 days, 8 hours, 876 chalakim. The excess beyond complete weeks is 4 days, 8 hours, 876 chalakim.[^45] This means the molad of Tishrei for the following year will fall 4 days, 8 hours, and 876 chalakim later in the week than the current year's molad.

Now suppose the current molad is Tuesday at 9 hours, 204 chalakim — the GaTRaD threshold. Add the ordinary-year offset:

> Tuesday 9h 204p + 4d 8h 876p = Saturday 18h 0p

Saturday at 18 hours is exactly noon — the molad zaken threshold. The *next* year's molad triggers molad zaken, pushing Rosh Hashanah to Sunday. But Sunday is ADU, so it pushes again to Monday. The next year's Rosh Hashanah lands on Monday.

So what would the current year look like? Rosh Hashanah this year on Tuesday, Rosh Hashanah next year on Monday. Count the days: Tuesday to Monday is a span of 6 days in the week. An ordinary year's natural length is 354 days, and 354 mod 7 = 4. For the weekday to advance by 6 rather than 4, the year would need 354 + 2 = 356 days.

But an ordinary year cannot be 356 days long. The maximum is 355 — a <span dir="rtl">שלמה</span> (*shlemah*, "complete") year in which both Cheshvan and Kislev have 30 days.[^46] There is simply no way to distribute 356 days across 12 months given the calendar's constraints. The year is impossible.

GaTRaD prevents this impossibility. By pushing the current year's Rosh Hashanah from Tuesday to Thursday, the year now runs from Thursday to Monday — a weekday advance of 4, which corresponds to a year of 354 or 355 days. Both are legal. The crisis is averted.

Notice the structure of the argument: GaTRaD does not respond to a problem in the current year. It *anticipates* a problem that would arise in the following year if the current year started on Tuesday. It is a forward-looking constraint, a guard against future impossibility. The calendar looks one year ahead and adjusts today to prevent tomorrow's contradiction.

How rare is GaTRaD? It fires roughly three times per century. The most recent occurrence was year 5745 (1984–85). The next is 5789 (2028–29), when the molad of Tishrei falls on Tuesday at 9 hours, 368 chalakim — comfortably past the threshold.[^47]

## BeTUTKaPoT

<span dir="rtl">בט״ו תקפ״ט</span> — another acronym: <span dir="rtl">ב</span> = 2 (Monday), <span dir="rtl">ט״ו</span> = 15 (hours), <span dir="rtl">תקפ״ט</span> = 589 (chalakim). The rule: in a year immediately following a leap year, if the molad of Tishrei falls on Monday at or after 15 hours and 589 chalakim — that is, 9:32:43 AM Monday morning — Rosh Hashanah is postponed from Monday to Tuesday.[^48]

This is the most subtle of the four rules, because it looks *backward*. GaTRaD protects the next year from being too long. BeTUTKaPoT protects the *previous* year — a leap year — from being too short.

The arithmetic, in full:

A leap year consists of 13 lunations: 13 × (29 days, 12 hours, 793 chalakim) = 383 days, 21 hours, 589 chalakim. The excess beyond complete weeks is 5 days, 21 hours, 589 chalakim. This means the molad advances by that amount from one Tishrei to the next across a leap year.

Now work backward. If the current year's molad is Monday at 15 hours, 589 chalakim, and the previous year was a leap year, then the *previous* year's molad was:

> Monday 15h 589p − 5d 21h 589p = Tuesday 18h 0p

(Subtracting 5 days from Monday gives Wednesday going backward, but with the hour math: 15h − 21h requires borrowing a day, giving us 15h + 24h − 21h = 18h, and Monday − 5d + 1d borrowed = Tuesday.) The previous year's molad was Tuesday at exactly 18 hours — the molad zaken boundary. Molad zaken pushes it to Wednesday. Wednesday is ADU. Lo ADU pushes it to Thursday.

So the previous year's Rosh Hashanah was Thursday. The current year's Rosh Hashanah, without BeTUTKaPoT, would be Monday. Count the days: Thursday to Monday is a span of 4 days in the week. A leap year's natural length is 383 days, and 383 mod 7 = 5. For the weekday to advance by only 4 rather than 5, the year would need 383 − 1 = 382 days.

But a leap year cannot be 382 days long. The minimum is 383 — a <span dir="rtl">חסרה</span> (*chaserah*, "deficient") year in which both Cheshvan and Kislev have 29 days.[^46] There is no valid configuration with fewer than 383 days across 13 months. The year is impossible.

BeTUTKaPoT prevents this impossibility. By pushing the current year's Rosh Hashanah from Monday to Tuesday, the previous leap year now runs from Thursday to Tuesday — a weekday advance of 5, which corresponds to 383 days. A tight fit, but legal. The deficient leap year is the rarest of the year types, but it exists precisely to accommodate situations like this.

How rare is BeTUTKaPoT? Even rarer than GaTRaD — roughly once or twice per century. The most recent occurrence was year 5766 (2005–06), when the molad of Tishrei fell on Monday at 16 hours, 876 chalakim. The next will not occur until 5813 (2052–53).[^49]

## The Interaction of the Dehiyyot

Before assembling the rules into a single algorithm, a critical point about how they interact.

Lo ADU and molad zaken can cascade. If molad zaken pushes Rosh Hashanah to an ADU day, Lo ADU pushes it one more day. This is the only cascading interaction in the system. The result is a two-day postponement — the maximum that Lo ADU and molad zaken together can produce.

GaTRaD and BeTUTKaPoT do *not* cascade with molad zaken. They operate on the *original* molad values, not on already-postponed dates. GaTRaD checks whether the original molad is on Tuesday at or after 9h 204p in a non-leap year. If so, it sets Rosh Hashanah directly to Thursday, bypassing the molad zaken and Lo ADU logic entirely. BeTUTKaPoT similarly checks whether the original molad is on Monday at or after 15h 589p in a year following a leap year. If so, it sets Rosh Hashanah directly to Tuesday.

In practice, GaTRaD and BeTUTKaPoT are mutually exclusive — they cannot both apply to the same year, because GaTRaD requires the current year to be non-leap, while BeTUTKaPoT requires the *previous* year to be a leap year, and these conditions impose different constraints on the molad that prevent overlap. And neither rule can fire simultaneously with molad zaken on the same molad, because their thresholds fall below the 18-hour molad zaken boundary: GaTRaD fires between 9h 204p and 17h 1079p on Tuesday, and BeTUTKaPoT fires between 15h 589p and 17h 1079p on Monday. If the molad were at 18h or later, molad zaken would apply instead, and the day would change, removing the GaTRaD or BeTUTKaPoT trigger.

The four rules, then, are not four layers of a complex cascade. They are four filters, mostly independent, mostly non-overlapping, each designed to catch one specific type of calendar failure. The system is elegant precisely because the rules barely interact.

## The Algorithm

Assembling the pieces into pseudocode:

> **Algorithm: DETERMINE ROSH HASHANAH**
>
> **Input:** Hebrew year *Y*
>
> **Step 1.** Compute the molad of Tishrei for year *Y* (using the procedure from Part II).
> Record the day of the week *D*, hour *H*, and chalakim *C*.
>
> **Step 2.** Check **GaTRaD**: If year *Y* is ordinary (non-leap), and *D* = Tuesday (3), and *H* ≥ 9, and (*H* > 9 or *C* ≥ 204):
> Set *D* = Thursday (5). Done.
>
> **Step 3.** Check **BeTUTKaPoT**: If year *Y* − 1 was a leap year, and *D* = Monday (2), and *H* ≥ 15, and (*H* > 15 or *C* ≥ 589):
> Set *D* = Tuesday (3). Done.
>
> **Step 4.** Apply **Molad Zaken**: If *H* ≥ 18:
> Set *D* = *D* + 1 (wrapping Saturday → Sunday).
>
> **Step 5.** Apply **Lo ADU**: If *D* ∈ {Sunday (1), Wednesday (4), Friday (6)}:
> Set *D* = *D* + 1.
>
> **Output:** Rosh Hashanah of year *Y* falls on day *D*.

Note the order. GaTRaD and BeTUTKaPoT are checked first, against the original molad values. If either fires, it sets the day directly and the algorithm terminates — no further checks are needed, because GaTRaD always produces Thursday (a legal day) and BeTUTKaPoT always produces Tuesday (also legal). Only if neither fires do molad zaken and Lo ADU apply, in that sequence, with possible cascading.

## Worked Examples

The best way to see the dehiyyot in action is to watch them work across several consecutive years.

| Year | Type | Molad of Tishrei | Dehiyyot Applied | Rosh Hashanah |
|------|------|-----------------|------------------|---------------|
| 5784 | Leap | Friday 11h 882p | Lo ADU (Friday → Shabbat) | Shabbat |
| 5785 | Ordinary | Thursday 9h 391p | None | Thursday |
| 5786 | Ordinary | Monday 18h 187p | Molad Zaken (Mon → Tue) | Tuesday |
| 5787 | Leap | Shabbat 2h 1063p | None | Shabbat |

Year 5784 is straightforward: the molad falls on Friday, which is forbidden by Lo ADU, so Rosh Hashanah moves to Shabbat. Year 5785 is even simpler — the molad falls on Thursday, which is legal, with no other rules triggered. Year 5786 shows molad zaken at work: the molad occurs on Monday at exactly 18 hours and 187 chalakim, past the noon threshold, pushing Rosh Hashanah to Tuesday. Year 5787 needs no postponement at all.

For the rarer rules, look further ahead:

| Year | Type | Molad of Tishrei | Dehiyyot Applied | Rosh Hashanah |
|------|------|-----------------|------------------|---------------|
| 5789 | Ordinary | Tuesday 9h 368p | GaTRaD (Tue → Thu) | Thursday |
| 5766 | Ordinary (post-leap) | Monday 16h 876p | BeTUTKaPoT (Mon → Tue) | Tuesday |

Year 5789 (2028–29 CE) fires GaTRaD. The molad falls on Tuesday at 9h 368p — past the 9h 204p threshold — in a non-leap year. Without the postponement, the following year's Rosh Hashanah would require a 356-day ordinary year, which is impossible. GaTRaD pushes directly to Thursday.

Year 5766 (2005–06 CE) fires BeTUTKaPoT. The molad falls on Monday at 16h 876p — well past the 15h 589p threshold — and the previous year (5765) was a leap year. Without the postponement, that leap year would have been only 382 days, which is too short. BeTUTKaPoT pushes to Tuesday, giving the leap year its minimum legal length of 383 days.

Between these six examples, all four dehiyyot appear. The system fires Lo ADU about 43% of the time, molad zaken about 25% of the time, GaTRaD a few times per century, and BeTUTKaPoT once or twice per century.[^50] In roughly 39% of years, no postponement is needed at all — the molad falls on a permitted day before noon, the year is not at risk of impossible length, and Rosh Hashanah simply falls on the day of the molad. In 47% of years, Rosh Hashanah is postponed by one day. In the remaining 14%, it is postponed by two days. No year ever requires a postponement of three or more days.

## What the Dehiyyot Achieve

Step back and look at what the four rules accomplish together.

Lo ADU constrains the *day*: Rosh Hashanah may fall on only four of the seven weekdays. Molad zaken constrains the *time*: the calendar preserves the ancient principle that the molad should precede, not follow, the start of its month. GaTRaD constrains the *year length*: no ordinary year may exceed 355 days. BeTUTKaPoT constrains the *year length* in the other direction: no leap year may fall below 383 days.

Together, the four rules guarantee that every Hebrew year has one of exactly six possible lengths: 353, 354, or 355 days for ordinary years; 383, 384, or 385 days for leap years. Combined with the four permitted starting days, this produces fourteen distinct year types — fourteen <span dir="rtl">קביעות</span> (*keviyyot*, "settings") — each fully determining the day of the week for every date in the year. Fourteen configurations, cycling through a pattern that repeats every 689,472 years.

The dehiyyot are where the calendar stops being pure astronomy and becomes engineering. The molad calculation tracks the moon. The 19-year cycle synchronizes the moon with the sun. But the dehiyyot are the adjustment layer, the mechanism that takes an astronomical output and reshapes it to fit the constraints of a legal and liturgical system. They are the reason the calendar *works* — not just as a timekeeper, but as the infrastructure of a lived religious life in which Yom Kippur never collides with Shabbat, Hoshanah Rabbah always permits its willow ceremony, and every year contains a coherent, physically possible arrangement of months and days.

The next question follows naturally: once Rosh Hashanah's day is fixed, what does the rest of the year look like? How many days go in Cheshvan, how many in Kislev, and which of the fourteen year types are you actually in? That is the work of Part IV.

***

---

# Part IV: YEAR TYPES AND THE COMPLETE CALENDAR

Parts II and III built the machinery: the 19-year cycle determines which years are leap years, the molad calculation pins down the mean conjunction for any month, and the four dehiyyot adjust the theoretical molad into an actual date for Rosh Hashanah. All of that was input processing. This Part is where the calendar produces its output — the full schedule of months, holidays, and Torah readings for an entire year.

The key insight is compression. The Hebrew calendar has twelve months in an ordinary year and thirteen in a leap year, but the lengths of all but two of those months are permanently fixed. The entire variability of the system — everything that makes one year different from another — is packed into two months, Cheshvan and Kislev, which serve as the calendar's adjustment mechanism. Once you know how those two months behave, you know everything.

## Six Possible Year Lengths

A Hebrew year can be exactly one of six lengths. Not approximately, not within a range — exactly one of six integers.[^51]

| Type | Category | Days | Cheshvan | Kislev |
|------|----------|------|----------|--------|
| Ordinary Deficient (<span dir="rtl">חסרה</span>) | Non-leap | 353 | 29 | 29 |
| Ordinary Regular (<span dir="rtl">כסדרה</span>) | Non-leap | 354 | 29 | 30 |
| Ordinary Complete (<span dir="rtl">שלמה</span>) | Non-leap | 355 | 30 | 30 |
| Leap Deficient (<span dir="rtl">חסרה</span>) | Leap | 383 | 29 | 29 |
| Leap Regular (<span dir="rtl">כסדרה</span>) | Leap | 384 | 29 | 30 |
| Leap Complete (<span dir="rtl">שלמה</span>) | Leap | 385 | 30 | 30 |

The names are descriptive. A deficient year (<span dir="rtl">שנה חסרה</span>) is short — it's missing a day. A complete year (<span dir="rtl">שנה שלמה</span>) is long — it has a day added. A regular year (<span dir="rtl">שנה כסדרה</span>) is "in order," meaning the months follow the default alternation without adjustment.[^52]

To see why only these six values are possible, look at how the months are built. Here is the complete month table:

| Month | Days | Fixed? |
|-------|------|--------|
| Tishrei | 30 | Yes |
| Cheshvan | 29 or 30 | Variable |
| Kislev | 29 or 30 | Variable |
| Tevet | 29 | Yes |
| Shevat | 30 | Yes |
| Adar (or Adar I in leap years) | 29 (or 30 in leap years) | Yes |
| Adar II (leap years only) | 29 | Yes |
| Nisan | 30 | Yes |
| Iyar | 29 | Yes |
| Sivan | 30 | Yes |
| Tammuz | 29 | Yes |
| Av | 30 | Yes |
| Elul | 29 | Yes |

The fixed months follow a strict alternation: 30, 29, 30, 29... starting from Tishrei. In a "regular" year, every month keeps this pattern exactly, producing the default sequence: Tishrei 30, Cheshvan 29, Kislev 30, Tevet 29, Shevat 30, Adar 29, Nisan 30, Iyar 29, Sivan 30, Tammuz 29, Av 30, Elul 29. That adds up to 354 — the length of a regular ordinary year. A leap year inserts a 30-day Adar I before the regular 29-day Adar (which becomes Adar II), adding 30 days for a baseline of 384.[^53]

The adjustment mechanism works on Cheshvan and Kislev alone. In a deficient year, Kislev shrinks from 30 to 29, losing one day from the regular baseline. In a complete year, Cheshvan grows from 29 to 30, adding one day. That gives the three ordinary-year totals — 353, 354, 355 — and the three leap-year totals — 383, 384, 385.

No other values are possible. Cheshvan can be 29 or 30. Kislev can be 29 or 30. But a year in which Cheshvan is 30 and Kislev is 29 never occurs — the calendar does not permit Cheshvan to be longer than Kislev.[^54] So instead of four combinations (2 × 2), there are only three, and the six year lengths follow.

This is a beautifully parsimonious design. Twelve or thirteen months, and the entire space of variation collapses to a single three-way choice. Deficient, regular, or complete. That's it.

### Determining the Year Length

How do you know which of the six types applies to a given year? The method is straightforward: compute the day of Rosh Hashanah for year *Y* (using the molad and dehiyyot from Part III), compute the day of Rosh Hashanah for year *Y* + 1, and subtract. The difference in days is the year length.[^55]

This is worth pausing on, because it reveals something about the calendar's architecture. The year type is not computed directly — it is *derived*. The algorithm doesn't decide in advance that year 5784 should be 355 days long. Instead, it independently computes two Rosh Hashanah dates, and the year length falls out as a consequence. The dehiyyot can push Rosh Hashanah forward by one or two days, and those pushes interact with the leap-year pattern in complex ways. The resulting year length is an emergent property of the system, not an input to it.

Maimonides lays this out explicitly: once you have established the day of Rosh Hashanah for the current year and the next, you count the days between them, and the count tells you everything.[^55] If the count is 353, 354, or 355, you have an ordinary year and you know the type. If it's 383, 384, or 385, you have a leap year and again you know the type. From the type, you know whether Cheshvan gets 30 days or 29, whether Kislev gets 30 days or 29. And from that, you can write out the complete month-by-month calendar.

In pseudocode:

> **function** year_type(Y):
>     rh_current = rosh_hashanah(Y)        *// from Part III*
>     rh_next = rosh_hashanah(Y + 1)
>     length = rh_next − rh_current
>     **if** length ∈ {353, 383}: **return** "deficient"
>     **if** length ∈ {354, 384}: **return** "regular"
>     **if** length ∈ {355, 385}: **return** "complete"

That function, combined with knowledge of whether the year is a leap year (determined by its position in the 19-year cycle, as covered in Part II), fully specifies the calendar for the entire year.

## The Fourteen Keviyyot

The year type — deficient, regular, or complete — is one piece of the puzzle. But to fully characterize a year, you also need to know two other things: the day of the week on which Rosh Hashanah falls, and whether the year is ordinary or leap. The combination of all three is called the <span dir="rtl">קביעה</span> (keviyyah), literally the "setting" or "fixing" of the year.[^57]

The keviyyah is a compact type signature. It tells you everything you need to know about the calendar for that year: every holiday, every fast day, every Shabbat Torah reading. Two years with the same keviyyah are calendrically identical — the same schedule, the same doubling of Torah portions, the same day-of-the-week for every occasion.

Start with the theoretical space. Rosh Hashanah can fall on one of four days of the week — Monday, Tuesday, Thursday, or Saturday — because the Lo ADU rule (dehiyyah 1 from Part III) forbids Sunday, Wednesday, and Friday.[^58] The year can be deficient, regular, or complete (three options). And the year can be ordinary or leap (two options). That gives 4 × 3 × 2 = 24 theoretical combinations.

But not all 24 are achievable. The arithmetic of the molad, the dehiyyot, and the constraints on year length rule out ten of them. Only fourteen combinations actually occur in practice.[^59] Here they are:

| # | Keviyyah | RH Day | Type | Ord/Leap | Days | Passover Day |
|---|----------|--------|------|----------|------|--------------|
| 1 | <span dir="rtl">בחג</span> | Monday (2) | Deficient | Ordinary | 353 | Tuesday |
| 2 | <span dir="rtl">בשה</span> | Monday (2) | Complete | Ordinary | 355 | Thursday |
| 3 | <span dir="rtl">גכה</span> | Tuesday (3) | Regular | Ordinary | 354 | Thursday |
| 4 | <span dir="rtl">הכז</span> | Thursday (5) | Regular | Ordinary | 354 | Saturday |
| 5 | <span dir="rtl">השא</span> | Thursday (5) | Complete | Ordinary | 355 | Sunday |
| 6 | <span dir="rtl">זחא</span> | Saturday (7) | Deficient | Ordinary | 353 | Sunday |
| 7 | <span dir="rtl">זשג</span> | Saturday (7) | Complete | Ordinary | 355 | Tuesday |
| 8 | <span dir="rtl">בחה</span> | Monday (2) | Deficient | Leap | 383 | Thursday |
| 9 | <span dir="rtl">בשז</span> | Monday (2) | Complete | Leap | 385 | Saturday |
| 10 | <span dir="rtl">גכז</span> | Tuesday (3) | Regular | Leap | 384 | Saturday |
| 11 | <span dir="rtl">החא</span> | Thursday (5) | Deficient | Leap | 383 | Sunday |
| 12 | <span dir="rtl">השג</span> | Thursday (5) | Complete | Leap | 385 | Tuesday |
| 13 | <span dir="rtl">זחג</span> | Saturday (7) | Deficient | Leap | 383 | Tuesday |
| 14 | <span dir="rtl">זשה</span> | Saturday (7) | Complete | Leap | 385 | Thursday |

Look at what's missing. There is no Monday regular year — ordinary or leap. No Tuesday deficient or complete year. No Thursday deficient ordinary year. No Saturday regular year of any kind. Each absent combination represents a mathematical impossibility given the constraints of the system.[^60]

Consider why a Monday regular ordinary year cannot exist. A regular ordinary year is 354 days long. 354 = 50 × 7 + 4, so Rosh Hashanah of the following year would fall four days later in the week — on Friday. But Friday violates Lo ADU, so the dehiyyot push it to Saturday, which changes the actual year length and means the year was never really "regular" in the first place. The impossibility is baked into the arithmetic.

The Passover column is revealing. In a regular ordinary year, Passover (15 Nisan) falls exactly 191 days after 1 Tishrei — the sum of Tishrei through Adar (30 + 29 + 30 + 29 + 30 + 29 = 177) plus 14 more days to reach 15 Nisan.[^61] Since 191 = 27 × 7 + 2, the day of the week for Passover is always the day of Rosh Hashanah plus 2 (modulo 7) in a regular ordinary year. In a deficient year the offset shrinks by one (to +1), and in a complete year it grows by one (to +3). For leap years, the 30-day Adar I shifts the offset further. But in every case, Passover lands on one of exactly four days: Sunday, Tuesday, Thursday, or Saturday. It never falls on Monday, Wednesday, or Friday — a rule called Lo BaDU (<span dir="rtl">לא בד״ו</span>) for Passover, paralleling the Lo ADU rule for Rosh Hashanah.[^62]

This is not a coincidence. Lo BaDU on Passover is a direct consequence of Lo ADU on Rosh Hashanah — the same constraints, seen from the other end of the year. And the motivations behind Lo ADU are practical. If Rosh Hashanah fell on Sunday, Hoshana Rabbah (21 Tishrei) would land on Shabbat, conflicting with its customs of beating willow branches. If Rosh Hashanah fell on Wednesday, Yom Kippur would fall on Friday, creating back-to-back days of full rest (Yom Kippur and Shabbat) with no opportunity to prepare food or attend to the dead between them. If Rosh Hashanah fell on Friday, Yom Kippur would fall on Sunday, producing the same problem in reverse. The dehiyyot encode these liturgical necessities as arithmetic constraints, and the Lo BaDU pattern on Passover falls out as a downstream consequence.

### The Hebrew Notation

Traditionally, a keviyyah is written as a three-letter Hebrew abbreviation. The first letter gives the day of Rosh Hashanah (using the Hebrew numbering where <span dir="rtl">ב</span> = Monday/2nd day, <span dir="rtl">ג</span> = Tuesday/3rd day, <span dir="rtl">ה</span> = Thursday/5th day, <span dir="rtl">ז</span> = Saturday/7th day). The second letter indicates the year type: <span dir="rtl">ח</span> for deficient (<span dir="rtl">חסרה</span>), <span dir="rtl">כ</span> for regular (<span dir="rtl">כסדרה</span>), <span dir="rtl">ש</span> for complete (<span dir="rtl">שלמה</span>). The third letter gives the day of Passover.[^63]

A few examples:

- <span dir="rtl">בחג</span> — Rosh Hashanah on Monday (<span dir="rtl">ב</span>), deficient (<span dir="rtl">ח</span>), Passover on Tuesday (<span dir="rtl">ג</span>). This is keviyyah #1: an ordinary deficient year beginning on Monday.
- <span dir="rtl">הכז</span> — Rosh Hashanah on Thursday (<span dir="rtl">ה</span>), regular (<span dir="rtl">כ</span>), Passover on Saturday (<span dir="rtl">ז</span>). Keviyyah #4: an ordinary regular year beginning on Thursday.
- <span dir="rtl">בכג</span> — Rosh Hashanah on Monday (<span dir="rtl">ב</span>), regular (<span dir="rtl">כ</span>), Passover on Tuesday (<span dir="rtl">ג</span>). This code doesn't appear in our table — there is no Monday regular year, ordinary or leap. The notation itself serves as a check: if you produce a code that doesn't match one of the fourteen, something went wrong.
- <span dir="rtl">זשד</span> — Rosh Hashanah on Saturday (<span dir="rtl">ז</span>), complete (<span dir="rtl">ש</span>), Passover on Wednesday (<span dir="rtl">ד</span>). Again, not valid — Passover never falls on Wednesday (Lo BaDU).

The notation is compact, memorable, and self-checking. It was designed for a world where calendrical calculations were done by hand and errors had real liturgical consequences. Three letters encode the entire year.

The Tur, the 14th-century halakhic compendium by Rabbi Jacob ben Asher, presents the full list of keviyyot and their associated Torah reading schedules in Orach Chaim 428.[^64] This section of the Tur became the standard reference for synagogue administrators who needed to plan the year's readings. It is, in modern terms, a lookup table indexed by keviyyah.

## The Four Gates

Every step of the calendar algorithm described so far — compute the molad, apply the dehiyyot, find the year length, classify the keviyyah — can be executed as a sequence of calculations. But sequential calculation invites sequential errors. Miss one dehiyyah and the entire downstream calendar is wrong. Forget to carry a remainder in the molad arithmetic and everything after it shifts.

The Four Gates (<span dir="rtl">ארבעה שערים</span>) solve this problem through a technique that will be instantly recognizable to anyone who has ever used a multiplication table: precomputation. Instead of running the algorithm from scratch each time, you compute all possible results in advance, organize them into a table, and look up the answer.[^65]

The structure is elegant. Since Rosh Hashanah can only fall on four days of the week, there are four "gates" — one for Monday, one for Tuesday, one for Thursday, one for Saturday. Within each gate, the molad's time is divided into ranges. Each range corresponds to a specific keviyyah, with separate entries for ordinary and leap years.

The gate for Monday, for instance, might contain entries like this (simplified and illustrative):

> **Gate of Monday (<span dir="rtl">שער ב</span>):**
>
> If the molad of Tishrei falls on Sunday from 18h 0p onward through Monday 9h 203p, and the year is ordinary → keviyyah <span dir="rtl">בשה</span> (Monday Complete, 355 days)
>
> If the molad of Tishrei falls on Monday from 9h 204p through 17h 1079p, and the year is ordinary → keviyyah <span dir="rtl">בחג</span> (Monday Deficient, 353 days)
>
> *[additional ranges for leap years...]*

The boundary values in the table — times like "9h 204p" or "15h 589p" — are not arbitrary. They are the exact molad values at which the dehiyyot flip the outcome from one keviyyah to another. Each boundary encodes one or more dehiyyot. The molad zaken rule (Part III) sets one set of boundaries. The Lo ADU rule sets others. The Gatarad and Betutkapat rules set still others, but only in specific year-type contexts. All of these conditional rules are "compiled" into the table's boundary values, so the user never needs to reason about the dehiyyot directly.

Maimonides presents the complete Four Gates table in Hilkhot Kiddush HaChodesh 8:9–10, with all boundary values specified to the <span dir="rtl">חֵלֶק</span>.[^65] The table is deterministic and exhaustive: every possible molad value for Tishrei maps to exactly one keviyyah. There are no gaps, no overlaps, no ambiguous cases.

This is a pre-modern example of a space-time tradeoff — one of the fundamental ideas in computer science. The sequential algorithm (compute molad, apply dehiyyot, find year length, classify) uses minimal memory but requires multiple computational steps. The Four Gates table uses more memory (you have to store the table) but reduces the computation to a single lookup. The information content is identical. The table produces exactly the same output as the algorithm for every possible input. But the table is faster to use and harder to get wrong.

The analogy to a multiplication table is almost exact. You could, each time you needed to know 7 × 8, perform the multiplication from scratch — add 8 to itself 7 times, or decompose into (7 × 5) + (7 × 3), or whatever method you prefer. Or you could memorize that 7 × 8 = 56. The multiplication table doesn't contain new information; it contains the *same* information in a form optimized for retrieval rather than derivation. The Four Gates are a multiplication table for the Hebrew calendar.

There is a subtlety here worth noting. The Four Gates work because the input space is finite and manageable. The molad of Tishrei is characterized by the day of the week (7 options) and the time within that day (24 × 1080 = 25,920 possible <span dir="rtl">חֲלָקִים</span>). That's a large but bounded space, and the keviyyah function over that space is piecewise constant — it takes one value over a range of molad times, then jumps to a different value at a boundary, and stays there over the next range. This kind of function is a natural candidate for tabulation. If the function were chaotic, with the output changing unpredictably from one <span dir="rtl">חֵלֶק</span> to the next, a table would need to be as large as the input space itself and would offer no advantage. But because the function is well-behaved — long flat stretches separated by sharp boundaries — the table is compact.

The practical value was enormous. A synagogue leader in medieval Cairo or Mainz or Baghdad, tasked with setting the liturgical calendar for the coming year, did not need to understand the derivation of the dehiyyot or the mathematics of the 19-year cycle. He needed the molad of Tishrei (which could be computed by simple addition from a known base value) and access to the Four Gates table. One lookup, and he had the keviyyah. From the keviyyah, the rest of the year unfolded deterministically.

## Torah Portions and the Liturgical Year

The calendar so far has been about dates — which day is Rosh Hashanah, how long is Cheshvan, when does Passover fall. But the calendar's ultimate output is not a grid of dates. It is a schedule of practice. And the most visible piece of that schedule, the one that shapes the rhythm of Jewish life week by week, is the cycle of Torah readings.

The Torah — the Five Books of Moses — is divided into 54 weekly portions, each called a <span dir="rtl">פָּרָשָׁה</span> (parashah). The cycle begins on the Shabbat following Simchat Torah (in the fall) and runs through the following Simchat Torah, at which point the last verses of Deuteronomy and the first verses of Genesis are read back-to-back, and the cycle starts again.

Fifty-four portions, but no year has 54 Shabbatot. An ordinary year has roughly 50 Shabbatot on which the weekly portion is read (a few Shabbatot coincide with holidays and get special readings instead). A leap year, being 30 days longer, has a few more. This means some portions must be doubled — two portions read together on a single Shabbat — in most years. The question is which ones.

The answer depends entirely on the keviyyah. Given the keviyyah, the doubling schedule is fixed. Certain pairs of portions have traditional pairing partners: Vayakhel-Pekudei, Tazria-Metzora, Acharei Mot-Kedoshim, Behar-Bechukotai, Chukat-Balak, Matot-Masei, Nitzavim-Vayelech. In a short ordinary year, most or all of these pairs are doubled. In a long leap year, most or all are read separately. The specific pattern — which pairs are combined and which are split — varies by keviyyah and also by community tradition. The Israeli and diaspora calendars differ slightly, since the second day of festivals observed in the diaspora occasionally causes the readings to diverge for a few weeks before resynchronizing.

Maimonides discusses the reading cycle and its rules in Hilkhot Tefillah 13:1–4.[^56] The Tur and Shulchan Aruch, both in Orach Chaim 428, provide the practical lookup: given the keviyyah, here is the reading schedule for the year.[^64] These tables, printed in the back of many Hebrew calendars and prayer books, are the final output of the entire calendrical system. They translate the abstract machinery of moladot, dehiyyot, and keviyyot into the lived experience of Shabbat morning in synagogue.

Think about the information flow. A single number — the year of creation, <span dir="rtl">שנת בריאת העולם</span> — feeds into the algorithm. From it, you compute the position in the 19-year cycle, which tells you whether the year is ordinary or leap. You compute the molad of Tishrei. You apply the dehiyyot to determine Rosh Hashanah. You compute next year's Rosh Hashanah and derive the year length. You classify the keviyyah. And from the keviyyah, you read off the complete schedule: every month's length, every holiday's date and day of the week, every Shabbat's Torah portion, every fast day's placement. The entire liturgical year — hundreds of specific determinations — flows from one integer input through a deterministic pipeline.

That pipeline is the Hebrew calendar. It is, in a precise and non-metaphorical sense, an algorithm: a finite sequence of well-defined operations that transforms input into output, produces the same result every time for the same input, and terminates. It was designed by human beings, refined over centuries, and frozen into its current form sometime in the early medieval period. It requires no observation, no judgment, no authority. It runs on arithmetic alone.

---

Part V assembles the full algorithm end-to-end — from epoch to calendar date in a single pass — and then turns to the question that modern users encounter most often: how the Hebrew calendar maps onto the Gregorian one, and why converting between them is slightly harder than it looks.

---

---

# Part V: THE COMPLETE ALGORITHM

Parts I through IV built the machinery in pieces. The 19-year cycle. The molad. The dehiyyot. The six year types. Each piece was developed on its own terms, with its own logic. This Part puts them together. A single input — the Hebrew year number — goes in. A complete calendar comes out.

## From Year Number to Complete Calendar

Here is the full algorithm. Eight steps, no ambiguity, no judgment calls.

> **Algorithm: HEBREW YEAR TO COMPLETE CALENDAR**
>
> **INPUT:** Hebrew year *Y*
>
> **Step 1: Position in the Metonic cycle**
>     year_in_cycle = ((*Y* − 1) mod 19) + 1
>     is_leap = year_in_cycle ∈ {3, 6, 8, 11, 14, 17, 19}
>
> **Step 2: Total months from epoch to Tishrei of year *Y***
>     completed_years = *Y* − 1
>     full_cycles = completed_years ÷ 19 (integer division)
>     remaining_years = completed_years mod 19
>     months_in_full_cycles = full_cycles × 235
>     months_in_remaining = Σ (13 if year *k* is leap, else 12) for *k* = 1..remaining_years
>     total_months = months_in_full_cycles + months_in_remaining
>
> **Step 3: Molad of Tishrei for year *Y***
>     molad = total_months × (29d 12h 793p) + BaHaRaD (2d 5h 204p)
>     Extract: day_of_week, hours, chalakim
>
> **Step 4: Apply dehiyyot to find Rosh Hashanah**
>     (a) Lo ADU: if day_of_week ∈ {Sunday, Wednesday, Friday}, postpone 1 day
>     (b) Molad Zaken: if hours ≥ 18, postpone 1 day; then recheck Lo ADU
>     (c) GaTRaD: if NOT leap, day = Tuesday, time ≥ 9h 204p, postpone 2 days
>     (d) BeTUTaKPaT: if previous year WAS leap, day = Monday, time ≥ 15h 589p, postpone 1 day
>
> **Step 5: Repeat Steps 1–4 for year *Y* + 1**
>
> **Step 6: Year length**
>     year_length = RH(*Y* + 1) − RH(*Y*)
>
> **Step 7: Classify year type**
>     If ordinary: 353 = deficient, 354 = regular, 355 = complete
>     If leap: 383 = deficient, 384 = regular, 385 = complete
>
> **Step 8: Assign month lengths**
>     All months fixed except Cheshvan and Kislev:
>     Deficient → Cheshvan 29, Kislev 29
>     Regular → Cheshvan 29, Kislev 30
>     Complete → Cheshvan 30, Kislev 30
>
> **OUTPUT:** Complete calendar for year *Y*

That's the whole machine. Every piece was justified in the preceding Parts; this is the assembly diagram. The algorithm is finite, deterministic, and mechanical. Given the same input, it always produces the same output. Given different inputs, it produces different outputs. No observation required, no authority consulted, no judgment exercised. Pure arithmetic.

Now let's run it.

### Worked Example: Year 5787

Year 5787 begins in the fall of 2026. It's a good test case: it's a leap year, and the dehiyyot interact in an instructive way when we compute the *following* year's Rosh Hashanah.

**Step 1: Position in the Metonic cycle**

year_in_cycle = ((5787 − 1) mod 19) + 1 = (5786 mod 19) + 1 = 10 + 1 = 11

Position 11 falls in the set {3, 6, 8, 11, 14, 17, 19}. Year 5787 is a leap year.[^66]

**Step 2: Total months from epoch to Tishrei 5787**

The number of completed years before 5787 is 5,786. Dividing by 19: 5,786 ÷ 19 = 304 complete cycles with a remainder of 10.

Each complete cycle contains 235 months, so the full cycles contribute 304 × 235 = 71,440 months.

For the remaining 10 years (positions 1 through 10 in the cycle), count the months one by one:

| Position | Leap? | Months |
|----------|-------|--------|
| 1 | No | 12 |
| 2 | No | 12 |
| 3 | Yes | 13 |
| 4 | No | 12 |
| 5 | No | 12 |
| 6 | Yes | 13 |
| 7 | No | 12 |
| 8 | Yes | 13 |
| 9 | No | 12 |
| 10 | No | 12 |

The remaining years contribute 123 months. Total: 71,440 + 123 = 71,563 months from the epoch to Tishrei 5787.[^67]

**Step 3: Molad of Tishrei 5787**

Each month is exactly 29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span>. To avoid fractions entirely, convert everything to <span dir="rtl">חֲלָקִים</span>. One day is 24 × 1,080 = 25,920 <span dir="rtl">חֲלָקִים</span>. One month is therefore:

29 × 25,920 + 12 × 1,080 + 793 = 765,433 <span dir="rtl">חֲלָקִים</span>

The epoch molad — BaHaRaD — is 2 days, 5 hours, 204 <span dir="rtl">חֲלָקִים</span>:

2 × 25,920 + 5 × 1,080 + 204 = 57,444 <span dir="rtl">חֲלָקִים</span>

Multiply and add:

71,563 × 765,433 + 57,444 = 54,776,739,223 <span dir="rtl">חֲלָקִים</span>

Now convert back. Divide by 25,920 to get days:

54,776,739,223 ÷ 25,920 = 2,113,300 days with a remainder of 3,223 <span dir="rtl">חֲלָקִים</span>

Divide the remainder by 1,080 to get hours:

3,223 ÷ 1,080 = 2 hours with a remainder of 1,063 <span dir="rtl">חֲלָקִים</span>

The molad is: day 2,113,300 of the count, 2 hours, 1,063 <span dir="rtl">חֲלָקִים</span>.

Day of the week: 2,113,300 mod 7 = 0 = Shabbat (Saturday).[^68]

In Hebrew timekeeping, the day begins at 6:00 PM. Hour 0 is 6:00 PM, hour 2 is 8:00 PM. And 1,063 <span dir="rtl">חֲלָקִים</span> is 59 minutes and 1 <span dir="rtl">חֵלֶק</span> (since 1,063 ÷ 18 = 59 with remainder 1, and each minute contains 18 <span dir="rtl">חֲלָקִים</span>). So the molad of Tishrei 5787 falls on Friday evening — which is the beginning of Shabbat — at 8:59 PM and 1 <span dir="rtl">חֵלֶק</span>. In civil terms: Friday, September 11, 2026, at about 8:59 PM.[^69]

**Step 4: Dehiyyot**

The molad falls on Shabbat. Check each rule:

*Lo ADU:* Rosh Hashanah cannot fall on Sunday, Wednesday, or Friday. Shabbat is not one of these. No postponement.

*Molad Zaken:* The molad must occur before the 18th hour (noon on the calendar day) for Rosh Hashanah to fall on that day. The molad hour is 2, which is well before 18. No postponement.

*GaTRaD:* Applies only to non-leap years when the molad falls on Tuesday at or after 9 hours and 204 <span dir="rtl">חֲלָקִים</span>. Year 5787 is a leap year, so this rule is irrelevant.

*BeTUTaKPaT:* Applies when the *previous* year was a leap year and the molad falls on Monday at or after 15 hours and 589 <span dir="rtl">חֲלָקִים</span>. Year 5786 is position 10 in the cycle — not a leap year. And the molad isn't on Monday anyway. No postponement.

No dehiyyot fire. Rosh Hashanah 5787 falls on the day of the molad: Shabbat, September 12, 2026.[^70]

**Step 5: Repeat for year 5788**

Year 5788 occupies position 12 in the cycle: ((5788 − 1) mod 19) + 1 = 12. Position 12 is not in the leap-year set, so 5788 is an ordinary year.

Since 5787 is a leap year (13 months), the molad of Tishrei 5788 falls 13 months after the molad of Tishrei 5787. Adding 13 × 765,433 <span dir="rtl">חֲלָקִים</span> to our previous total gives a molad on day 2,113,684, at 0 hours and 572 <span dir="rtl">חֲלָקִים</span>. Day 2,113,684 mod 7 = 6 = Friday.

The molad of Tishrei 5788 falls on Friday evening (the very beginning of Shabbat, in civil terms), at 6:31 PM and 14 <span dir="rtl">חֲלָקִים</span>.[^71]

Now the dehiyyot: the molad falls on Friday. Lo ADU says Rosh Hashanah cannot fall on Friday (day 6). Postpone by one day to Shabbat.

No other dehiyyot apply. Rosh Hashanah 5788 = Shabbat, October 2, 2027.

**Step 6: Year length**

The molad of Tishrei 5787 gives Rosh Hashanah on day 2,113,300. The molad of Tishrei 5788 falls on day 2,113,684, but Lo ADU pushes Rosh Hashanah to day 2,113,685.

Year length = 2,113,685 − 2,113,300 = 385 days.

**Step 7: Classification**

Year 5787 is a leap year, and 385 days is the longest possible leap year length. It is a complete year (<span dir="rtl">שנה שלמה</span>) — both Cheshvan and Kislev receive 30 days.

**Step 8: Month lengths**

| Month | Days |
|-------|------|
| Tishrei | 30 |
| Cheshvan | 30 |
| Kislev | 30 |
| Tevet | 29 |
| Shevat | 30 |
| Adar I | 30 |
| Adar II | 29 |
| Nisan | 30 |
| Iyar | 29 |
| Sivan | 30 |
| Tammuz | 29 |
| Av | 30 |
| Elul | 29 |
| **Total** | **385** |

That is the complete calendar for Hebrew year 5787. Thirteen months, 385 days, every date determined. From a single integer — 5787 — the algorithm produced the full structure: a complete leap year beginning on Shabbat, with Passover falling on a Thursday (April 22, 2027), Yom Kippur on a Monday (September 21, 2026), and every other date falling into place with the inevitability of a machine that has been running for millennia.[^72]

The entire calculation required no tables, no observation, no human judgment. Just arithmetic — large numbers, yes, but exact ones. The same calculation performed anywhere in the world, at any time, by any person with access to the algorithm, produces the identical result. That's what it means for a calendar to be fully determined.

## Converting Between Hebrew and Gregorian Dates

The Hebrew calendar and the Gregorian calendar are two independent deterministic systems, each counting days from a different epoch, each applying a different set of rules to organize those days into months and years. Converting between them requires aligning their epochs and running both algorithms in tandem.

The Hebrew epoch is 1 Tishrei of Year 1, which corresponds approximately to October 7, 3761 BCE in the proleptic Julian calendar. This date was back-calculated by medieval scholars to correspond to the molad BaHaRaD — the first molad, the theoretical new moon at the start of creation. No one is claiming the world was created on that particular Monday evening. The epoch is a computational anchor point, chosen so that the molad arithmetic produces correct results going forward.[^73]

The Gregorian epoch — January 1, 1 CE — has its own history and its own conventions. The two epochs are separated by approximately 1,373,429 days, depending on exactly how you count (Julian versus Gregorian matters here, since the two diverge by the number of dropped leap days).

The basic idea of conversion is simple. Both calendars assign every day a unique position in their respective sequences. If you can express any date as an "absolute day number" — its position on a single continuous timeline — then conversion is just a matter of translating between two coordinate systems. Compute the absolute day number from one calendar's coordinates, then compute the other calendar's coordinates from that absolute day number. It is exactly the same logic as converting between Celsius and Fahrenheit: map to an intermediate representation (absolute temperature, absolute day), then map out again.[^74]

For the Hebrew-to-Gregorian direction: given a Hebrew date (day *d* of month *m* in year *Y*), compute Rosh Hashanah of year *Y* using the algorithm from the From Year Number to Complete Calendar section, then add the appropriate number of days to reach month *m*, day *d*. This gives you the absolute day. Then convert the absolute day to a Gregorian date by finding which Gregorian year, month, and day it falls in — a calculation that requires knowing the Gregorian leap-year rule (divisible by 4, except centuries, except 400-year multiples) but is otherwise straightforward.

For the Gregorian-to-Hebrew direction: reverse the process. From the Gregorian date, compute the absolute day number. Then determine which Hebrew year contains that day (a matter of estimating the year and checking), find Rosh Hashanah of that year, and count forward through the months to locate the exact Hebrew date.

The key insight is that both directions are always possible and always exact. There is no ambiguity, no timezone dependency in the traditional system, and no need for empirical data beyond the algorithms themselves. Two deterministic systems, one shared timeline. Conversion is a solved problem.

### The Gauss Algorithm for Passover

In May 1802, Carl Friedrich Gauss — the mathematician who, by that point in his career, had already proven the fundamental theorem of algebra and predicted the orbit of Ceres from a handful of observations — published a brief paper titled "Berechnung des jüdischen Osterfestes" (Calculation of the Jewish Easter) in the *Monatliche Correspondenz zur Beförderung der Erd- und Himmelskunde*.[^75] The paper contained a compact formula to compute the Julian date of the first day of Passover for any Hebrew year.

The formula is remarkable not for its complexity but for the fact that it exists at all. Gauss took the entire Hebrew calendar — the 19-year cycle, the molad, all four dehiyyot, the year-type classification — and compressed it into a single algebraic expression. No iteration. No case analysis. Just a formula you evaluate.

Here is its structure, adapted slightly for readability:

> **Given:** Hebrew year *Y*
>
> **Step 1.** *a* = (12*Y* + 17) mod 19
>
> **Step 2.** *b* = *Y* mod 4
>
> **Step 3.** *M* + *m* = 32.0440933 + 1.5542418*a* + *b*/4 − 0.0031777*Y*
>
> (where *M* is the integer part and *m* is the fractional part)
>
> **Step 4.** *c* = (3*Y* + 5*b* + *M* + 5) mod 7
>
> **Step 5.** Apply corrections:
>
> If *c* = 2, 4, or 6: add 1 to *M*
>
> If *c* = 1 and *a* > 6 and *m* ≥ 0.632870370: add 2 to *M*
>
> If *c* = 0 and *a* > 11 and *m* ≥ 0.897723765: add 1 to *M*
>
> **Result:** 15 Nisan = *M*th of March (Julian calendar)

The corrections in Step 5 are the dehiyyot in disguise. The first condition (add 1 if *c* is 2, 4, or 6) encodes Lo ADU — if Passover would fall on an impermissible day, shift it. The second and third conditions encode GaTRaD and BeTUTaKPaT, the rare postponement rules that depend on the molad's time and the leap-year status. The decimal constants are the molad and cycle parameters rewritten as rational numbers over the Gregorian cycle length.[^76]

The formula gives the date in the Julian calendar; for modern use, you add the Gregorian correction (currently 13 days). Gauss published it without proof or derivation, as a mathematical curiosity. Almost a century later, M. Hamburger published a proof of its correctness, confirming that the formula agrees with the traditional calendar for every possible input.[^77]

The formula works. For any year, it produces the correct date. Its existence tells you something about the calendar itself: the system is regular enough — deterministic enough, periodic enough — that its entire output can be captured in a closed-form expression. An algorithm that required true observation, genuine judgment, or irreducible case-by-case reasoning could not have been so compressed. Gauss didn't simplify the calendar. He proved it was already simple.

## Implementation Notes

The Hebrew calendar is fully deterministic and computable in constant time — O(1) per query, in the language of computational complexity. Given any Hebrew year, the complete calendar can be computed with a fixed number of arithmetic operations: a modular reduction for the cycle position, a multiplication and addition for the molad, a handful of comparisons for the dehiyyot, and a subtraction for the year length. No iteration, no searching, no external data. The number of steps does not grow with the size of the input.[^78]

Modern implementations exist in multiple forms. The most authoritative reference is Reingold and Dershowitz's *Calendrical Calculations*, now in its fourth edition, which provides rigorously tested algorithms for the Hebrew calendar (and conversions between more than thirty calendar systems) with implementations in Lisp, Java, and Mathematica. Their algorithms handle every edge case and have been validated against centuries of historical calendars.[^79] The open-source project Hebcal is the most widely used practical implementation, powering synagogue calendars, email reminders, and date converters used by millions of people.

The calendar's computability is not just a computational convenience. It is the feature that made it possible to replace the Sanhedrin. A system that required human judgment — that depended on a witness's description of the crescent moon, or a court's assessment of the barley crop — could not survive the loss of the institution that exercised that judgment. The fixed calendar works precisely because it doesn't need anyone to run it. It is self-executing. The arithmetic doesn't care whether there is a Sanhedrin in Jerusalem or a rabbi in your town or even another Jew in your timezone. You have the numbers. You have the rules. You have the calendar.

That self-sufficiency came at a cost. The observation-based system was flexible: the court could adjust, respond to unusual conditions, exercise discretion. The fixed calendar is rigid: it produces the same output regardless of circumstances. But rigidity, in this case, was the point. The calendar needed to run without supervision, in exile, across continents, for centuries. It has now been doing so for roughly 1,700 years, and it has not required a single correction, patch, or update. The algorithm Hillel II published — or whoever finalized the system, if the historical attribution is uncertain — has been producing correct calendars every year since, on its own, automatically, by the sheer force of its mathematics.[^80]

---

# Part VI: SEASONS AND THEIR ARITHMETIC

The Metonic cycle and the dehiyyot solve the lunar problem: months track the moon. But Jewish law also cares about the sun. The Torah demands that Passover fall in spring. Sukkot in autumn. The agricultural rhythms encoded in the festival cycle presuppose a calendar that knows where the earth is in its orbit, not just what the moon is doing.

The Hebrew calendar tracks the solar year implicitly, through the 19-year intercalation cycle. But it also tracks it explicitly, through a concept called the <span dir="rtl">תְּקוּפָה</span> (tekufah, plural tekufot) — literally, a "turning point." The four tekufot mark the solstices and equinoxes: the four moments in the year when the sun's apparent path reaches an extreme or crosses the equator.

Two Talmudic sages proposed two different values for the length of the solar year. Both values are still in use — for different purposes, in different contexts, with different consequences. Their disagreement is not a flaw in the system. It's a feature. And the arithmetic behind it reveals something unexpected about the calendar's deep structure.

## Tekufat Shmuel

Shmuel — Shmuel Yarchinaah, the third-century Babylonian amora who was also a physician and astronomer — held that the solar year is exactly 365 days and 6 hours. Each of the four seasons, from one tekufah to the next, is therefore exactly one-quarter of a year: 91 days and 7½ hours.[^81]

That number — 365.25 days — should look familiar. It is precisely the mean year length of the Julian calendar, the system that Julius Caesar introduced in 46 BCE and that remained the civil calendar of Europe for over 1,600 years. Shmuel and Caesar (or rather, Caesar's astronomer Sosigenes) agreed. Whether Shmuel adopted the Julian value, derived it independently, or both of them inherited it from an older Babylonian tradition is a question the sources don't definitively answer. What matters is the number itself: 365 days, 6 hours, exactly.

The four tekufot according to Shmuel:

- **Tekufat Nisan** (<span dir="rtl">תקופת ניסן</span>): the vernal equinox, marking the beginning of spring
- **Tekufat Tammuz** (<span dir="rtl">תקופת תמוז</span>): the summer solstice
- **Tekufat Tishrei** (<span dir="rtl">תקופת תשרי</span>): the autumnal equinox
- **Tekufat Tevet** (<span dir="rtl">תקופת טבת</span>): the winter solstice

Each tekufah follows the previous one by exactly 91 days and 7 hours 540 <span dir="rtl">חֲלָקִים</span> (since 7.5 hours = 7 hours and 540 <span dir="rtl">חֲלָקִים</span>, another case where the 1,080-based system produces clean integer arithmetic).[^82]

Shmuel's value is too long. The actual tropical year — the time for the sun to return to the same equinox point — is approximately 365.24219 days, about 11 minutes and 15 seconds shorter than 365.25 days. Over a century, the error is roughly 18.75 hours — not quite a full day, but getting there. Over four centuries, it's about three days, which is exactly the discrepancy that motivated the Gregorian reform of 1582 (which dropped three leap days per 400 years to compensate).

But Shmuel's value, slightly wrong though it is, has two properties that keep it in use. First, it's simple — the arithmetic never generates fractions smaller than a <span dir="rtl">חֵלֶק</span>. Second, and more importantly, two significant areas of Jewish law are tied to Shmuel's reckoning and have never been updated.

### Birkat HaChamah

The blessing of the sun. Once every 28 years.

The logic runs like this. Shmuel's year is exactly 365 days and 6 hours, which is exactly 52 weeks plus 1 day and 6 hours. Each year, the tekufah of Nisan occurs 1 day and 6 hours later in the week than the previous year. After four years, it has shifted by 5 days and 0 hours — exactly 5 days. After 28 years, it has shifted by 28 × (1 day, 6 hours) = 35 days = exactly 5 weeks. Which means it returns to the same day of the week and the same time of day.[^83]

According to tradition, creation began on a Wednesday — more precisely, the sun was set in its place on the fourth day of creation, at the beginning of the nighttime period, which in Hebrew reckoning means Tuesday evening. Tekufat Nisan at the epoch, by tradition, coincides with this moment: the beginning of Wednesday night. Every 28 years, by Shmuel's reckoning, the sun returns to this position: Tekufat Nisan falls at the beginning of Wednesday night. When it does, a special blessing is recited — <span dir="rtl">בִּרְכַּת הַחַמָּה</span>, the blessing of the sun — praising God "who makes the work of creation" (<span dir="rtl">עוֹשֶׂה מַעֲשֵׂה בְרֵאשִׁית</span>).

The most recent Birkat HaChamah was on April 8, 2009 — 14 Nisan 5769, which happened to be Erev Pesach, the day before Passover, a coincidence that added considerable excitement. The next will be on April 8, 2037.[^84]

The 28-year cycle is a fiction, in the strict astronomical sense. The real sun does not return to the same equinox position on the same day of the week every 28 years, because the real year is not exactly 365.25 days. The tekufah slowly drifts. But the blessing is tied to Shmuel's calculation, not to the actual equinox, and so it continues on its 28-year schedule regardless. The calendar here is explicitly choosing the legal computation over the astronomical observation — a choice entirely consistent with the principle established in Part I, that the calendar is a legal institution, not an astronomical one.

### The Prayer for Rain

In the Land of Israel, the prayer for rain (<span dir="rtl">וְתֵן טַל וּמָטָר לִבְרָכָה</span>) begins on 7 Cheshvan, a fixed Hebrew date. In the diaspora, it begins later — on the 60th day after Tekufat Tishrei, according to Shmuel's reckoning. This follows the Talmudic ruling that diaspora communities begin requesting rain later than those in Israel, since the Babylonian agricultural season started later.[^85]

Because Shmuel's year is slightly too long, this 60th day has been drifting relative to the Gregorian calendar. In the twentieth century, it typically fell on December 4 or 5. It now falls on December 5 or 6 in most years. Eventually — not for a while, but inevitably — it will drift to December 6 and 7, then later still. The Gregorian calendar corrects for the discrepancy between 365.25 and 365.2422 days; Shmuel's calendar does not. The two systems are slowly coming apart.[^86]

This drift is small enough that no halakhic authority has seen fit to address it. The prayer for rain in early December versus mid-December is a matter of weeks either way, and the agricultural logic that originally motivated the date — the Babylonian rainy season — has been irrelevant for centuries. But the drift is real, and it is a direct consequence of Shmuel's slightly overlong year embedding itself in a halakhic practice that does not have a built-in correction mechanism.

## Tekufat Rav Adda

Rav Adda bar Ahavah, a contemporary of Shmuel's, proposed a more precise value. His solar year: 365 days, 5 hours, 997 <span dir="rtl">חֲלָקִים</span>, and 48 <span dir="rtl">רְגָעִים</span> (rega'im, where one rega is 1/76 of a <span dir="rtl">חֵלֶק</span>).[^87]

The number looks arcane. It is anything but. Watch where it comes from.

The Metonic cycle declares that 19 solar years equal 235 lunar months. That is the cycle's defining assumption — the assertion that after 19 years, the sun and moon return to (approximately) the same relative position. The calendar has already committed to the exact length of the lunar month: 29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span>. So the total duration of 19 years, measured in lunar months, is:

235 × (29d 12h 793p) = 235 × 765,433 <span dir="rtl">חֲלָקִים</span> = 179,876,755 <span dir="rtl">חֲלָקִים</span>

Divide by 19 to get one solar year:

179,876,755 ÷ 19 = 9,467,197 <span dir="rtl">חֲלָקִים</span>, remainder 12

That remainder — 12 <span dir="rtl">חֲלָקִים</span> spread across 19 years — is 12/19 of a <span dir="rtl">חֵלֶק</span> per year. To express it exactly requires a finer unit. Each <span dir="rtl">חֵלֶק</span> is divided into 76 <span dir="rtl">רְגָעִים</span>, so 12/19 of a <span dir="rtl">חֵלֶק</span> is (12 × 76)/19 = 912/19 = 48 <span dir="rtl">רְגָעִים</span>. The division comes out exact.[^88]

Convert the 9,467,197 <span dir="rtl">חֲלָקִים</span> back to days, hours, and <span dir="rtl">חֲלָקִים</span>: 9,467,197 ÷ 25,920 = 365 days, remainder 6,397. Then 6,397 ÷ 1,080 = 5 hours, remainder 997 <span dir="rtl">חֲלָקִים</span>. Plus the 48 <span dir="rtl">רְגָעִים</span> from the remainder.

Rav Adda's year: 365 days, 5 hours, 997 <span dir="rtl">חֲלָקִים</span>, 48 <span dir="rtl">רְגָעִים</span>.

In decimal: approximately 365.2468 days. The modern tropical year is approximately 365.2422 days. Rav Adda's value overshoots by about 6 minutes and 40 seconds per year — an error, but a smaller one than Shmuel's 11 minutes and 15 seconds. As a purely empirical measurement of the tropical year, it is more accurate than any value used in the West before the Gregorian reform.[^89]

But Rav Adda didn't measure anything. That's the remarkable thing. His year length is not an independent astronomical observation. It is a *derived* quantity — the value implied by the combination of two other values the calendar had already adopted: the Metonic cycle (19 years = 235 months) and the molad (29d 12h 793p). The year length is whatever makes those two commitments consistent. Rav Adda simply did the division.

This means that Rav Adda's tekufah is not an alternative to the molad system. It *is* the molad system, viewed from a different angle. Every time the algorithm computes a molad, it implicitly uses Rav Adda's year, because the 19-year cycle with 235 months is built into the calculation. The Metonic relationship links the lunar month and the solar year; if you accept the month length and the cycle, the year length follows by pure algebra.

Maimonides discusses both tekufot in Hilkhot Kiddush HaChodesh, chapters 9 and 10. He presents Shmuel's value first as the simpler calculation, then introduces Rav Adda's value as the more precise one, noting that it is closer to the values determined by the astronomers of his own era. He is explicit that Rav Adda's tekufah is the one embedded in the calendar's actual intercalation mechanism — the one that governs when leap months are added. Shmuel's tekufah, meanwhile, governs the seasonal halakhot: Birkat HaChamah, the prayer for rain.[^90]

Two values, two purposes. Shmuel's is a legal fiction — simple, stable, practical for the halakhic contexts where it's used. Rav Adda's is a mathematical consequence — derived, precise, and already built into the calendar whether anyone invokes it by name or not.

### The Dual Nature

The tekufot reveal the calendar's deepest structural feature: it is simultaneously a lunar calendar and a solar calendar, and the two aspects are coupled through the Metonic cycle.

The lunar component is explicit. Months begin at the molad. Month lengths track the synodic period. Every piece of the algorithm from Parts II through V operates in lunar time.

The solar component is implicit. The 19-year cycle, by fixing the relationship 19 years = 235 months, implicitly defines the solar year as Rav Adda's value. The seven leap years in each cycle are positioned to keep Passover near the vernal equinox — that is, to keep the lunar months anchored to the solar seasons. But the calendar never directly computes a solar event. It never asks "when is the equinox?" It achieves solar alignment indirectly, through the arithmetic of leap months, the way a thermostat achieves a target temperature not by measuring heat but by cycling a switch on and off.[^91]

Shmuel and Rav Adda were measuring the same thing: the sun's annual journey from equinox to equinox. Shmuel measured it simply and got a round number. Rav Adda derived it precisely and got an unround number that happens to be more accurate. Both values survive in the calendar's machinery, doing different jobs, each suited to its role.

The fixed calendar is, in the end, a device for reconciling three incommensurable cycles — the day, the lunar month, and the solar year — using nothing but integer arithmetic and a few carefully chosen constants. The day is exact (it's the calendar's atomic unit). The month is approximate but extraordinarily accurate (off by less than a second per lunation). The year is approximate and somewhat less accurate (off by a few minutes, by either reckoning). But the Metonic cycle couples the month and the year so tightly that the system holds together for millennia before the small errors become large enough to matter.

Whether those errors will eventually require a correction — and who would have the authority to make one, in the absence of a Sanhedrin — is a question the calendar's architects left for the future. So far, the future has not needed to answer it.

How did this elaborate system come into being? Not all at once. The transition from a court that watched the sky and declared the month to an algorithm that runs on its own, needing no court and no sky — that transition is itself a story, and a remarkable one. It is the subject of Part VII.

---

---

# Part VII: THE HISTORY OF THE TRANSITION

## From Sanhedrin to Calculation

The observational system described in Part I worked for centuries. Witnesses came to Jerusalem, the Sanhedrin examined them, the court declared the new month. When the seasons began to drift, the court intercalated — added a second Adar, pushed Passover back into spring, and moved on. The system was flexible, authoritative, and responsive. It was also entirely dependent on a single institution.

That institution needed a court with recognized jurisdiction across the Jewish world. It needed witnesses willing and able to travel to the court's seat. It needed a communication network — first signal fires, then messengers — capable of distributing the court's rulings to communities scattered across the Near East and the Mediterranean. Knock out any one of those pillars and the whole structure wobbles. Knock out all of them and the calendar collapses.

By the fourth century CE, all of them were wobbling.

The Roman Empire had been applying escalating pressure to Jewish self-governance in Palestine since the destruction of the Temple in 70 CE. The Bar Kokhba revolt of 132–135 CE led to the expulsion of Jews from Jerusalem and the relocation of the Sanhedrin to the Galilee — first to Usha, then Shefar'am, then Beit She'arim, then Sepphoris, then Tiberias.[^92] Each move represented a further contraction of authority. By the mid-fourth century, the Roman emperor Constantius II (337–361 CE) was actively restricting the powers of the Jewish patriarchate, and the institution itself was in its final decades — the last nasi, Gamliel VI, died around 425 CE, and the patriarchate was formally abolished shortly after.[^93]

The traditional account of what happened next is clean and dramatic. Hillel II, the nasi of the Sanhedrin, saw the collapse coming and took a radical step: he "published" or "revealed" the fixed calendar in approximately 359 CE, making the algorithm public so that any community, anywhere, could determine the calendar independently.[^94] No more witnesses. No more messengers. No more dependence on a court that might not exist next year. The calendar would run on arithmetic alone.

The logic, if the tradition is accurate, was compelling. A dispersed community cannot depend on a single institution for something as fundamental as the calendar. If the patriarchate disappears — and it was about to disappear — and no successor institution emerges with recognized authority, then communities in Babylonia, North Africa, and the western Mediterranean would have no way to know when to observe the festivals. The calendar would fracture, and with it the unity of Jewish practice. The only insurance against that fracture was to remove the human element entirely: replace the court's judgment with a computation, replace the witnesses' testimony with an algorithm, and make the algorithm available to everyone.

There is a significant problem with this account. The earliest source attributing the calendar to Hillel II is Rav Hai Gaon, writing around 992–1000 CE — more than six centuries after the supposed event.[^95] No contemporary fourth-century source mentions it. The Jerusalem Talmud, redacted in the late fourth century and therefore roughly contemporaneous with Hillel II, says nothing about a calendar reform. The Babylonian Talmud, edited in the fifth and sixth centuries, never credits Hillel II with establishing the fixed calendar. The attribution appears, fully formed, in the Geonic period, and then is taken up by later authorities as established fact. It may be true. But it is not well-attested.

What Hillel II "published" — assuming the attribution is accurate — is also debated. Some scholars read the tradition as claiming that Hillel released the full algorithm in essentially its current form: the molad, the dehiyyot, the 19-year cycle, the complete system described in Parts II through V of this manuscript. Others argue that he released only the intercalation pattern — the fixed sequence of which years within the 19-year cycle receive a leap month — and that the remainder of the system, particularly the dehiyyot, developed gradually over subsequent centuries.[^96]

The evidence, as Sacha Stern has argued in the most thorough modern treatment of this question, supports a more gradual development. The fixed calendar did not spring into existence as a finished product. It crystallized over several hundred years, with different elements reaching their final form at different times.[^97]

## The Evidence of Continued Dispute

If the calendar had been fully fixed in 359 CE, you would expect uniformity from that point forward. One algorithm, one set of results, no room for disagreement. The historical record shows otherwise.

The first category of evidence comes from the Cairo Genizah — a vast repository of over 300,000 manuscript fragments stored in the storeroom (genizah) of the Ben Ezra synagogue in Old Cairo from roughly the ninth century onward. Because Jewish law prohibits the destruction of documents containing God's name, the community deposited worn-out manuscripts, legal documents, letters, and scraps in this storeroom rather than discarding them. The dry Egyptian climate preserved them, and when the collection was brought to scholarly attention in the late nineteenth century, it became a window into centuries of Jewish communal life that had left almost no other trace.[^98]

Among the Genizah fragments are calendar documents — tables, calculations, and correspondence — that reveal continued variation in practice well after the calendar was supposedly fixed. Some fragments indicate that Palestinian and Babylonian communities were not fully aligned on calendar rules as late as the ninth and early tenth centuries. The discrepancies are not large — they involve the precise parameters of the molad calculation and the application of the postponement rules — but they are discrepancies, and they mean that the calendar was still a living, contested system, not a settled algorithm that everyone had agreed upon centuries earlier.[^99]

The second and most dramatic category of evidence is the Ben Meir controversy of 921–922 CE.

Aaron ben Meir was the head of the Palestinian academy — the institutional descendant, however attenuated, of the original Sanhedrin. He announced that the molad zaken threshold — the cutoff time described in Part III, past which Rosh Hashanah must be postponed — should be set 642 <span dir="rtl">חֲלָקִים</span> earlier than the value used by the Babylonian academies. In the Babylonian reckoning (the one that became standard), Rosh Hashanah is postponed if the molad of Tishrei falls at or after 18 hours (i.e., noon on the Hebrew day). Ben Meir argued the threshold was 17 hours and 438 <span dir="rtl">חֲלָקִים</span> — approximately 35 minutes and 40 seconds earlier.[^100]

Thirty-five minutes. In a calendar whose fundamental unit, the <span dir="rtl">חֵלֶק</span>, is three and a third seconds, 642 of those units might sound like a technicality. It was not. For the years 4682 and 4683 (921–922 CE), the difference placed the molad of Tishrei on opposite sides of the threshold. The two systems produced different dates for Rosh Hashanah. Different Rosh Hashanah means different Yom Kippur. Different Yom Kippur means different Sukkot. Different first of Tishrei can cascade forward and alter the date of Passover in the following spring.

For two years, the Jewish world was split. Communities following Ben Meir observed Rosh Hashanah on one day; communities following the Babylonian academies observed it on another. Jews in one city were fasting on Yom Kippur while Jews in the next city were not. The festivals — those fixed points around which all of Jewish communal and religious life is organized — were unfixed.

Think about what that means in practice. A Jewish merchant traveling from a Palestinian community to a Babylonian one might arrive to find that his hosts had already observed Yom Kippur the day before — or had not yet observed it. Torah readings, which follow a fixed annual cycle tied to the calendar, would be out of sync: one community reading one portion, the neighboring community reading another. The entire liturgical infrastructure of Jewish life depends on calendar unity, and for two years, that unity was broken.

The Babylonian side of the dispute was led by Saadia ben Joseph, later known as Saadia Gaon, one of the great intellects of the Geonic period. Saadia wrote extensively against Ben Meir's position, marshaling both mathematical argument and institutional authority. He argued that the Babylonian tradition of the 18-hour threshold was the authoritative one, received and transmitted through an unbroken chain of scholars, and that Ben Meir's variant was an error — either a misunderstanding of the tradition or a deliberate assertion of Palestinian prerogative.[^101]

Ben Meir's own argument rested on a claim of Palestinian priority. The calendar, he maintained, had been established by the Palestinian authorities — by Hillel II, a Palestinian nasi — and therefore the Palestinian tradition regarding its parameters should take precedence. The dispute was as much about institutional authority as it was about arithmetic.[^102]

The Babylonian position prevailed. By 923 CE the controversy was resolved, and the molad zaken threshold was fixed permanently at 18 hours — the value used ever since. But the episode proves something important: as late as 921 CE, more than five and a half centuries after Hillel II's supposed publication of the calendar, the exact parameters of the system were still actively contested. The molad zaken rule — one of the four dehiyyot, the postponement rules that are essential to making the calendar work — was not universally agreed upon until the tenth century.

The Ben Meir controversy is not an obscure footnote. It marks the boundary between the calendar's formative period and its settled one. Before 921, the fixed calendar was a work in progress, its details still subject to dispute between competing authorities. After the resolution of the controversy — and the broader consolidation of Babylonian halakhic authority that accompanied it — the calendar reached its final form. The algorithm described in Parts II through V of this manuscript is the post-Ben Meir calendar, the one that emerged from ten centuries of gradual refinement.[^103]

## Maimonides and the Codification

The definitive treatment of the fixed calendar in Jewish law is Maimonides' <span dir="rtl">הִלְכוֹת קִדּוּשׁ הַחֹדֶשׁ</span> (Laws of the Sanctification of the Month), written approximately 1178 CE as part of the <span dir="rtl">מִשְׁנֶה תּוֹרָה</span>.[^104] The work spans 19 chapters, and its structure is itself an argument.

Chapters 1–5 describe the observational system. How witnesses are examined. How the court proclaims the new month. How the signal system works. How the court decides to intercalate. How the nasi exercises authority. These chapters describe a system that had not functioned for seven hundred years by the time Maimonides wrote. He leads with it anyway.

Chapters 6–10 present the fixed calendar algorithm. The molad. The 19-year Metonic cycle. The four dehiyyot. The year types and the four gates. Every calculation described in Parts II through V of this manuscript is codified here, in precise halakhic language, with worked examples. These are the chapters that govern actual practice — the law that determines when Jews observe Rosh Hashanah, Yom Kippur, Passover, and every other date on the calendar. For a reader who wants only the operating manual, chapters 6–10 are sufficient.

Chapters 11–19 are the surprise. Nine chapters of detailed astronomical calculation: the mean and true longitude of the sun, the mean and true longitude of the moon, the moon's latitude, the elongation between sun and moon, the arc of visibility, the conditions under which the first crescent of the new moon can be seen on a given evening in a given location. This is serious positional astronomy — the kind of work that in the Islamic world was done by professional astronomers attached to observatories and courts.[^105]

Why include it? These nine chapters are among the most technically demanding passages in all of rabbinic literature. They require the reader to work through trigonometric concepts — expressed without trigonometric notation, since Maimonides wrote in the idiom of medieval mathematical astronomy — and to perform multi-step calculations involving mean motions, anomalies, and corrections. Maimonides does not need these chapters to explain the fixed calendar. The fixed calendar does not use crescent visibility; it uses the molad, which is the mean conjunction, not the first sighting. The astronomical chapters serve a different purpose entirely.

Maimonides makes his reasoning explicit in the opening chapters. The sanctification of the new month, he writes, is a commandment given to the Great Court — to the Sanhedrin. The fixed calendar operates only because, in the absence of a Sanhedrin, the calculations serve as a proxy for the court's declarations.[^106] The algorithm produces the same results that a properly functioning court would have reached. But it is a proxy, not a replacement. When a Sanhedrin is reconstituted, the observational system resumes. The fixed calendar was always designed to be temporary.

And when that observational system resumes, the reconstituted court will need to do exactly what Rabban Gamliel did in the second century: examine witnesses, assess their testimony, determine whether the crescent they claim to have seen is astronomically plausible. The court will need to know where the moon is, how far it is from the sun, how wide the crescent should be, whether it could have been visible from a given location at a given time. That knowledge is what chapters 11–19 preserve.

The three-part structure carries a theological claim disguised as a legal code. The observational system (chapters 1–5) comes first because it is the primary law — the calendar as the Torah intends it, responsive to human observation and judicial authority, alive in a way that an algorithm cannot be. The fixed calendar (chapters 6–10) comes second because it is a necessary substitute, brilliant in its engineering but provisional by nature. The astronomical visibility calculations (chapters 11–19) come last because they serve the future — they are a manual for a court that does not yet exist, written by a man who believed it would exist again.

The fixed calendar, in Maimonides' framework, is not a permanent institution. It is an algorithm holding the place of a court, carrying the memory of the system it replaced, and preserving the tools for the system that will one day replace it.

---

# Part VIII: PRECISION, DRIFT, AND THE LONG VIEW

## The Full Cycle

Every clock resets eventually. A twelve-hour clock repeats every 43,200 seconds. A week repeats every 7 days. The Metonic cycle repeats every 19 years. The Hebrew calendar, taken as a whole — with all its moving parts, all its constraints, all its postponement rules and variable month lengths — also repeats. The full cycle is 689,472 years.[^107]

Here is where that number comes from.

The calendar repeats when the total elapsed time, measured in <span dir="rtl">חֲלָקִים</span>, returns to an exact multiple of a full week. A week contains 7 days × 24 hours × 1,080 <span dir="rtl">חֲלָקִים</span> = 181,440 <span dir="rtl">חֲלָקִים</span>. The calendar's state is determined entirely by the molad — and the molad advances by a fixed amount each month. So the calendar repeats when the total number of <span dir="rtl">חֲלָקִים</span> accumulated over some number of complete Metonic cycles is an exact multiple of 181,440.

One Metonic cycle contains 235 months. Each month adds 29 days, 12 hours, and 793 <span dir="rtl">חֲלָקִים</span>, which is (29 × 24 × 1,080) + (12 × 1,080) + 793 = 765,433 <span dir="rtl">חֲלָקִים</span>. One Metonic cycle therefore contains 235 × 765,433 = 179,876,755 <span dir="rtl">חֲלָקִים</span>.

Dividing by 181,440: 179,876,755 ÷ 181,440 = 991 with a remainder of 115,315. The remainder tells you that after one Metonic cycle, the molad has shifted by 115,315 <span dir="rtl">חֲלָקִים</span> within the week — it does not land on the same day-hour-chelek as where it started. The calendar has not yet repeated.

The full cycle requires finding the smallest number of Metonic cycles N such that N × 115,315 is divisible by 181,440. This is a least common multiple problem: find the LCM of 115,315 and 181,440, then divide by 115,315. Working through the prime factorizations and the Euclidean algorithm yields N = 36,288. That is: 36,288 complete Metonic cycles, each 19 years long, for a total of 36,288 × 19 = 689,472 years.[^108]

After 689,472 years, every molad falls on exactly the same day, hour, and <span dir="rtl">חֵלֶק</span> as it did 689,472 years earlier. Every year has the same <span dir="rtl">קְבִיעוּת</span> (keviyyah) — the same year type, the same day of the week for Rosh Hashanah, the same month lengths. The calendar is periodic. It loops, like a clock with an extraordinarily long hand.

One consequence of this periodicity: the distribution of year types over one full cycle is fixed and knowable. The fourteen keviyyot — seven for ordinary years, seven for leap years — do not occur with equal frequency. Some are common; others are rare. Across one complete 689,472-year cycle, the distribution is determined entirely by the arithmetic of the molad and the four dehiyyot. The cycle contains exactly 36,288 × 12 = 435,456 ordinary years and 36,288 × 7 = 254,016 leap years.[^109] Within those totals, each specific keviyyah — each combination of starting day and year length — occurs a fixed number of times, dictated by the fraction of moladot that fall in the relevant windows.

This is a calendar that, despite its complexity, is fully deterministic. Given the molad of any single month, you can compute the calendar backward and forward without limit. There is no randomness, no ambiguity, no room for interpretation. It is the same algorithm producing the same results in the same order, forever, or at least for as long as anyone cares to run it.

The contrast with the observational system is stark. Under the Sanhedrin, the calendar was responsive — the court could add a leap month when conditions warranted it, adjust to unusual circumstances, exercise discretion. The fixed calendar has no discretion. It cannot respond to anything. It is a machine that was set in motion centuries ago and has been running on its own ever since, producing the same outputs from the same inputs with the mechanical reliability of a clock. The gain is uniformity and independence. The loss is the human judgment that the Talmud understood as essential to the calendar's sanctity — the court's proclamation of <span dir="rtl">מְקֻדָּשׁ</span>, the act of human authority that makes a day holy rather than merely computed.

## The Drift

"Forever" is a strong word, and it hides something important. The calendar is periodic — yes, mathematically, it repeats with perfect fidelity. But the calendar's relationship to the sky is not periodic. The two astronomical constants embedded in the algorithm — the month length and the implicit solar year — are both slightly wrong, and both errors accumulate.

**The molad drift.** The calendar's month is 29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span>, or 29.530594 days. The current best estimate of the mean synodic month is approximately 29.530589 days. The calendar's month is too long by about 0.000005 days per month — roughly half a second per lunation.

Half a second per month is nothing in human terms. You could not perceive it. But half a second per month is about 6 seconds per year, 10 minutes per century, and roughly 1 hour and 40 minutes per millennium. Over the approximately 1,650 years since the calendar's traditional establishment, the accumulated excess is somewhere around 2 hours. The molad — the moment the calendar declares as the mean conjunction of sun and moon — now runs, on average, about two hours later than the actual astronomical mean conjunction.

This drift is essentially cosmetic. On Shabbat Mevarekhein, when the upcoming molad is announced in synagogue, the time given is the calendar's molad, not the astronomical one, and the discrepancy matters to no one present. The fixed calendar never depended on the molad being astronomically accurate. It depended on the molad being mathematically consistent — on every community computing the same value and arriving at the same dates. That consistency is unaffected by the drift. The algorithm's internal machinery runs perfectly; it is only the algorithm's claim to track the actual moon that has developed a slight wobble.

**The solar drift.** This one is more consequential.

The calendar's implicit solar year length is embedded in the 19-year Metonic cycle. Nineteen years contain 235 months. Each month is 29 days, 12 hours, 793 <span dir="rtl">חֲלָקِים</span>. Multiply: 235 × (29 + 12/24 + 793/25,920) = 6,939.6896... days. Divide by 19 to get the implied year: 365.24682... days. This is Rav Adda's value, and it exceeds the actual mean tropical year (~365.24219 days) by about 0.00463 days per year — approximately 6 minutes and 40 seconds.

Six minutes and 40 seconds per year. About 11 hours per century. About 4.6 days per millennium. Over the roughly 1,650 years since the calendar's traditional founding, the accumulated excess is approximately 7 to 8 days.

The practical consequence is visible: the calendar's vernal equinox — the spring date around which Passover is anchored — has been drifting later relative to the astronomical equinox. The astronomical vernal equinox currently falls around March 20. The earliest possible date for Passover (15 Nisan) has been moving further from it. In the early centuries of the fixed calendar, Passover occasionally fell quite close to the equinox. Today, it almost never falls before late March and routinely extends into late April.

The drift is slow enough that it has not yet violated the calendar's defining constraint. Passover still falls in spring. Even the latest possible Passover — which can fall as late as April 25 in the Gregorian calendar — is well within the spring season in the northern hemisphere. No halakhic authority has declared the drift a crisis, and no one alive today will live to see it become one.

There is a subtlety worth noting. The Torah's requirement is that Passover fall in <span dir="rtl">חֹדֶשׁ הָאָבִיב</span> — the month of spring, or more literally, the month of ripening barley. Whether "spring" is defined by the astronomical equinox, by agricultural conditions in the Land of Israel, or by some broader seasonal criterion affects when the drift becomes a halakhic problem. If the standard is the equinox, the calendar is already somewhat late — the earliest Passover now falls about two weeks after the equinox rather than near it. If the standard is the broader sense of "spring season," the calendar has centuries of margin remaining. The Talmud itself records multiple opinions about the criteria for intercalation — the equinox, the state of the barley crop, the condition of the roads and ovens for Passover pilgrims — and these different criteria would trigger concern at different thresholds of drift.

But the mathematics is patient. At 6 minutes and 40 seconds per year, the calendar loses one full day against the sun every 216 years. A full month — the point at which Passover would cross the boundary from spring into summer — lies roughly 7,000 years in the future, depending on how strictly you define "spring" and which latitude you use as your reference. That is a long time. It is not forever.

Some context helps calibrate the concern. The Gregorian calendar, with its elegant leap-year correction (skip the leap year in century years not divisible by 400), has a residual drift of about 1 day in 3,236 years — roughly fifteen times more accurate than the Hebrew calendar's solar tracking. But the Gregorian calendar does not track the moon at all. It solved a simpler problem. The Hebrew calendar is trying to track both sun and moon with a single fixed algorithm that requires no external input and no institutional authority. The drift is the price of that ambition.

## The Calendar as Engineering

What kind of object is the Hebrew calendar? It is not quite an astronomical model — it does not aim for observational accuracy, and in the places where it diverges from the sky, it diverges deliberately. It is not quite a religious text — it has no narrative, no theology, no exhortation. It is, as much as anything, a piece of engineering: a system designed to meet a set of requirements under a set of constraints, and its character is best understood by examining the trade-offs it makes.

Compare it to three other systems that faced overlapping problems.

**The Islamic calendar** chose purity. Twelve lunar months, no intercalation, no correction, no attempt to anchor festivals to seasons. The result is simple and self-consistent: every month begins near the new moon, every year has 354 or 355 days, and the calendar advances through the seasons at a steady pace, completing one full revolution in about 33 years. Ramadan in summer, Ramadan in winter, Ramadan in spring — the cycle is egalitarian, and it is deliberate. The Quran explicitly prohibits intercalation (<span dir="rtl">إِنَّمَا ٱلنَّسِيءُ زِيَادَةٌ فِى ٱلْكُفْرِ</span>, "Postponement is an increase in disbelief," Quran 9:37), and the calendar obeys. What the Islamic calendar gains is independence from the sun and from the problem of reconciling two incommensurable cycles. What it sacrifices is seasonal anchoring — no Islamic holiday has a fixed relationship to planting, harvest, equinox, or solstice.

**The Chinese calendar** chose precision. It is lunisolar, like the Hebrew — months track the moon, and intercalary months keep the year aligned with the seasons. But the Chinese system computes its calendar using true astronomical positions: the actual longitude of the sun, the actual moments of new moon, the actual instants of solstice and equinox, all determined by the imperial Bureau of Astronomy using the best available astronomical models of the era. The calendar has been reformed multiple times throughout Chinese history — over a hundred different astronomical systems (<span dir="rtl">曆法</span>, lìfǎ) have been adopted over the centuries — each time updating the computational model to reflect improved astronomical knowledge. What the Chinese system gains is accuracy: its months track the actual moon, its seasons track the actual sun, and its intercalation responds to the actual positions of celestial bodies rather than to a mean-value approximation. What it sacrifices is independence. The Chinese calendar requires a central authority — an institution with the expertise and legitimacy to compute, promulgate, and if necessary reform the calendar. No village scholar with a quill and a table can reproduce it from first principles.

**The Gregorian calendar** chose simplicity. A pure solar calendar: 365 days per year, with a leap day added in years divisible by 4, except century years not divisible by 400. The rule fits in a single sentence. The resulting year averages 365.2425 days, which differs from the tropical year by only 0.0003 days — a drift of 1 day in roughly 3,236 years. The Gregorian calendar is, for solar tracking, an extraordinary achievement of minimalist design. What it sacrifices is the moon. Gregorian months have nothing to do with lunar phases. The new moon falls on a different calendar date each month. The full moon wanders. The word "month" retains its etymological connection to "moon," but the structural connection has been severed completely.

The Hebrew calendar stands in a different place from all three. It refused to abandon the moon (unlike the Gregorian). It refused to abandon the seasons (unlike the Islamic). It refused to rely on a central astronomical authority (unlike the Chinese). Instead, it accepted a set of constraints that no other major calendar has attempted to satisfy simultaneously:

Months must begin near the new moon. The year must stay aligned with the solar seasons. The entire system must be computable from first principles using only integer arithmetic. No external observation, no central authority, no institutional infrastructure is required.

Meeting all of these requirements with a fixed algorithm is only possible if you accept imperfection — if you let the month be slightly too long, let the year drift slightly against the sun, let some months be 29 days and others 30 even though the actual lunation is neither, let the molad announcement in synagogue deviate from the sky it claims to describe.

That is the trade-off. The Hebrew calendar sacrificed accuracy for autonomy. A community in tenth-century Baghdad could compute next year's calendar. A community in fifteenth-century Krakow could compute the same calendar and get the same results. A community in twenty-first-century Buenos Aires can do the same. No letters need to be exchanged. No edicts need to be received. No astronomical observations need to be made. The algorithm is self-contained, self-executing, and — crucially for a diaspora community with no political sovereignty and no guarantee that any particular institution would survive from one century to the next — self-sufficient.

No other lunisolar calendar in history has achieved this. The Chinese calendar is more accurate but requires an institution. The Hindu calendar, also lunisolar, has fragmented into regional variants precisely because it lacked a single authoritative computational standard. The Hebrew calendar's closest competitor in terms of decentralized computation might be the Easter computus used by the medieval Christian church — and even that has splintered into Western and Eastern variants that disagree to this day. The Hebrew calendar stands alone in combining lunisolar tracking with a fully deterministic algorithm that has produced universal agreement across a global diaspora for over a thousand years.

The cost of that self-sufficiency is the drift: a slow, steady divergence between the calendar and the sky that, left uncorrected, will eventually make Passover a summer holiday. The benefit is that for nearly two millennia, Jewish communities separated by oceans, languages, empires, persecutions, and centuries of silence have observed the same holidays on the same days, coordinated by nothing more than a shared algorithm and the integer arithmetic to run it. No one needed to send a message. No one needed to receive one. The calendar carried itself.

Whether that drift will someday demand a correction — whether the calendar can or should be reformed, and what authority could undertake such a reform in the absence of the Sanhedrin that Maimonides understood as its custodian — these are questions that go beyond engineering. Maimonides included nine chapters of astronomical visibility calculations in a code of law for a system that does not currently function. He was writing a manual for a court that does not yet exist, preserving the knowledge it would need, embedding in the law itself the expectation that the fixed calendar is not the last word. Part IX turns to what that expectation means — and what the calendar's imperfections reveal about how the tradition understands its own most intricate creation.

---

---

# Part IX: TWO OPEN QUESTIONS

The fixed calendar is an extraordinary piece of engineering. It has run, unmodified, for something like sixteen centuries. It produces the same output everywhere on earth. It requires no central authority, no communication network, no observation. It is, by any reasonable standard, a success.

It is also imperfect, and it knows it.

## Could the Calendar Be Reformed?

The drift described in Part VIII is real and accumulating. The Hebrew calendar's implicit solar year is about 6 minutes and 40 seconds longer than the actual tropical year.[^110] That sounds negligible, and for centuries it was. But the error compounds. Every 216 years or so, the earliest possible date for Passover shifts one day later relative to the vernal equinox.[^111] In the fourth century, when the fixed calendar was established, the equinox fell around March 21. Today, Passover occasionally begins as late as April 25 in the Gregorian calendar, and its earliest possible occurrence has drifted noticeably past the equinox. By the year 6000 in the Hebrew reckoning (roughly 2240 CE), the drift will amount to about seven or eight additional days. Passover will still fall in spring — but later in spring, and trending later.[^112]

The molad, too, is drifting. The traditional value for the synodic month exceeds the modern astronomical value by about half a second per lunation.[^113] Over the centuries since the calendar was fixed, this has accumulated to roughly two hours. The molad announced in synagogues no longer corresponds to the astronomical conjunction — it runs about two hours late and growing. This is a different kind of error than the seasonal drift, smaller in practical consequence but conceptually troubling: the calendar's own internal clock is falling behind the phenomenon it purports to track.

Could these errors be corrected? In purely mathematical terms, yes, and without great difficulty. The seasonal drift could be eliminated by adjusting the intercalation cycle — adding a leap month slightly less frequently, or modifying the pattern within the 19-year cycle. The molad drift could be corrected by updating the month length by a fraction of a <span dir="rtl">חֵלֶק</span>. Various scholars have proposed exactly these kinds of adjustments. The arithmetic is straightforward.[^114]

The obstacles are not mathematical. They are legal, sociological, and — in a way that resists easy categorization — theological.

**The halakhic obstacle.** The fixed calendar was established, by tradition, by Hillel II acting in his capacity as <span dir="rtl">נָשִׂיא</span>, the head of the Sanhedrin.[^115] His authority to do so derived from his position: the calendar is, at its root, an act of the court, as the Talmudic stories in Part I made vivid. Changing the calendar — modifying its parameters, adjusting its rules — would arguably require a court of comparable authority. Since no Sanhedrin currently exists, and the conditions for reconstituting one are themselves a matter of unresolved halakhic debate, the calendar is effectively frozen. It cannot be updated because the institution authorized to update it does not operate.

Some authorities push the argument further. Even if a Sanhedrin were reconstituted, they suggest, the fixed calendar may have acquired the status of an accepted communal practice — a <span dir="rtl">מִנְהָג</span> — with binding force that even a court cannot unilaterally override.[^116] On this view, the calendar is no longer merely a technical instrument that the court maintains. It has become something closer to settled law, ratified by centuries of universal acceptance. The Netziv was among the first major halakhic authorities to raise the question of what happens when the drift becomes practically significant; the responses he received ranged from dismissive (the Messiah will come before it matters) to serious engagement with the jurisprudential puzzle.[^117]

It is a genuine legal impasse. The calendar contains errors everyone can quantify. The tools to fix those errors are understood. But the authority to apply those tools may not exist.

**The sociological obstacle.** The calendar's primary function is coordination. Jewish communities worldwide observe the same holidays on the same days because they all run the same algorithm. Any reform that is not universally adopted would split the community — one group observing Passover on one date, another group a day earlier or later. The practical and religious consequences of such a split would be severe. Marriages, conversions, Shabbat observance, the validity of testimony — all depend on a shared calendar.

This is the same logic that governs technical standards in engineering: a mediocre standard that everyone uses is often more valuable than a superior standard that only some adopt. The cost of a protocol fork is high in any coordination system; in a religious community that defines its sacred time by shared observance, the cost is existential. The Hebrew calendar is, among other things, a coordination protocol, and the value of universal adoption outweighs the value of marginal accuracy.[^118]

**The theological dimension.** Some thinkers have suggested that the calendar's imperfection is not a bug to be patched but a feature with meaning. A calendar that needs eventual human correction preserves the principle established in Part I: the calendar belongs to the court, not to the stars. An eternally self-correcting algorithm would need no Sanhedrin. It would be a purely astronomical instrument, running on celestial mechanics, requiring no human authority at all. But the tradition insists that <span dir="rtl">אַתֶּם</span> — "you," the court, the human community — are the ones who declare the appointed times.[^119] A calendar with a built-in expiration date, one that will eventually need a human institution to step in and recalibrate it, keeps that principle alive. The imperfection is a placeholder for human authority, a reminder that the algorithm is a substitute, not a replacement, for the court.

Whether this reading is apologetics or genuine insight is a question each reader will answer differently. But it is worth noticing that Maimonides, who understood the calendar's limitations as well as anyone, never suggested correcting them. He recorded the parameters as given and moved on.

## The Return to Observation

The most striking structural feature of Maimonides' *Hilkhot Kiddush HaChodesh* is its ending. The work has nineteen chapters. The first five deal with the observational system: how the court receives witnesses, examines their testimony, sanctifies the new month, and communicates its decisions.[^120] Chapters six through ten lay out the fixed calendar: the molad, the 19-year cycle, the dehiyyot, the keviyyot, the Four Gates table — all the machinery described in Parts II through IV of this manuscript. If Maimonides had stopped there, the work would have been complete. Every rule needed to operate the calendar as it has functioned since the fourth century is contained in those ten chapters.

He did not stop there. Chapters eleven through nineteen — nine chapters, nearly half the work — are devoted to astronomical visibility calculations.[^121] Maimonides explains how to compute the sun's mean longitude and true longitude, the moon's mean longitude, its anomaly, its latitude, its parallax. He works through the geometry of the lunar crescent: its angular distance from the sun at sunset, its altitude above the horizon, the width and orientation of the visible sliver, the atmospheric conditions that affect visibility in Jerusalem. He provides tables of arc-sines, interpolation methods, step-by-step procedures for determining whether, on a given evening, the new crescent will be visible from the Land of Israel.

None of this is currently operative. No Sanhedrin sits. No witnesses testify. No court declares <span dir="rtl">מְקֻדָּשׁ</span>. The fixed calendar handles everything. These nine chapters describe a system that has been dormant for over a millennium and a half.

Why, then, did Maimonides include them? The *Mishneh Torah* is a law code, not an encyclopedia. Maimonides explicitly states in his introduction that he intends to record only material with practical legal application — this is what distinguishes his project from a theoretical treatise.[^122] He would not have devoted nearly half of *Hilkhot Kiddush HaChodesh* to an academic exercise. He included the visibility chapters because he believed they would have practical application. The fixed calendar is temporary. When the conditions that necessitated it no longer obtain — when a Sanhedrin is reconstituted and Jewish institutional life is re-centered in the Land of Israel — the observational system will return. The court will need to know how to verify whether a witness really saw what he claims to have seen. The nine chapters carry that knowledge forward.

Consider what the nine chapters contain. The astronomical models Maimonides used were drawn from Ptolemaic astronomy as transmitted through Arabic intermediaries, particularly al-Battani's work from the ninth century.[^123] He adapted these models — originally designed for general astronomical prediction — to the specific problem of crescent visibility over Jerusalem. The calculations are not trivial. They involve computing the true (as opposed to mean) positions of both the sun and moon, accounting for the moon's latitude and parallax, determining the angular separation between the two bodies at the moment of local sunset, and then comparing that separation to empirically established thresholds for naked-eye visibility under various atmospheric conditions. Maimonides walks through every step, provides numerical tables for interpolation, and gives worked examples. A competent reader can follow the procedure from raw calendar data to a yes-or-no determination: will the crescent be visible tonight?

There is something arresting about this. Maimonides, writing in Fustat in the late twelfth century, encoded in a law code the technical specifications for a system he knew would not operate in his lifetime. He was writing for a reader who did not yet exist — a future judge sitting on a future court, who would need to evaluate testimony about the new crescent over Jerusalem. He had no way of knowing when that reader would arrive. It might be centuries. It might be longer. But Maimonides treated the eventuality as certain enough to warrant nine chapters of detailed astronomical instruction, complete with worked examples and numerical tables.

The nine chapters are an act of preservation across time. They are a message in a bottle, addressed to a recipient the author trusted would eventually arrive.[^124]

This puts the fixed calendar in a different light. Seen from inside the tradition, the algorithm is not the endpoint of the calendar's development. It is an interlude — a mathematically elegant, operationally brilliant interlude that has lasted nearly two millennia and may last centuries more. But the tradition regards it as a bridge, not a destination. It connects an observational past to an anticipated observational future, maintaining continuity across however long the interval turns out to be.

The calendar that the tradition considers most fundamental is not the one that runs on arithmetic alone. It is the older system, the one that depends on human beings standing outside at dusk, scanning the western horizon for a sliver of light — and then walking into a courtroom to say what they saw. The fixed calendar holds the place of that system. It does so with extraordinary precision and reliability. But it holds the place; it does not take it.

That is, perhaps, the most interesting thing about the Hebrew calendar: it was built to be replaced.

---

# Glossary

**Adar** (<span dir="rtl">אֲדָר</span>): The twelfth month of the Hebrew calendar (sixth from Tishrei). In a leap year, Adar is split into Adar I (<span dir="rtl">אֲדָר א׳</span>), a 30-day intercalary month, and Adar II (<span dir="rtl">אֲדָר ב׳</span>), a 29-day month that retains the legal status of the "real" Adar. Purim is observed in Adar II in leap years.

**BaHaRaD** (<span dir="rtl">בהר״ד</span>): An acronym encoding the epoch of the Hebrew calendar — the molad of the first Tishrei in year 1. It stands for <span dir="rtl">ב׳</span> (Monday, the second day), <span dir="rtl">ה׳</span> (5 hours), <span dir="rtl">רד</span> (204 <span dir="rtl">חֲלָקִים</span>). In conventional notation: Monday, 5 hours, 204 parts after the start of the day (Saturday evening at 6:00 p.m. in the Hebrew reckoning). This is the fixed reference point from which all subsequent moladot are calculated by repeated addition.

**BeTUTKaPoT** (<span dir="rtl">בטותכפ״ת</span>): A mnemonic for the dehiyyah that applies when the molad of Tishrei in a year following a leap year falls on Tuesday at or after 9 hours and 589 <span dir="rtl">חֲלָקִים</span>. In such cases, Rosh Hashanah is postponed from Tuesday to Thursday. The name encodes the relevant day, time, and parts threshold. See *dehiyyah*.

**Birkat HaChamah** (<span dir="rtl">בִּרְכַּת הַחַמָּה</span>): The "Blessing of the Sun," a rare ceremony performed once every 28 years when, according to the calendar's reckoning, the sun returns to the position it occupied at creation. The 28-year cycle derives from the <span dir="rtl">תְּקוּפָה</span> of Shmuel (a solar year of exactly 365.25 days). The ceremony was last observed in 2009.

**Chelek** (<span dir="rtl">חֵלֶק</span>, pl. <span dir="rtl">חֲלָקִים</span>): The fundamental time unit of the Hebrew calendar. One hour is divided into 1,080 <span dir="rtl">חֲלָקִים</span>, making each <span dir="rtl">חֵלֶק</span> equal to 3 and 1/3 seconds. The number 1,080 was chosen for its extraordinary divisibility, enabling all calendar calculations to be performed using integer arithmetic with no rounding errors.

**Dehiyyah** (<span dir="rtl">דְּחִיָּה</span>, pl. <span dir="rtl">דְּחִיּוֹת</span>): Literally "postponement." One of four rules that can delay the date of Rosh Hashanah by one or two days from the day indicated by the raw molad calculation. The four dehiyyot are: Lo ADU, molad zaken, GaTRaD, and BeTUTKaPoT. They ensure that Rosh Hashanah falls only on Monday, Tuesday, Thursday, or Saturday, and prevent certain problematic year-length configurations.

**GaTRaD** (<span dir="rtl">גטר״ד</span>): A mnemonic for the dehiyyah that applies when the molad of Tishrei in a non-leap year falls on Tuesday at or after 9 hours and 204 <span dir="rtl">חֲלָקִים</span>. Rosh Hashanah is postponed from Tuesday to Thursday. The name encodes the day (<span dir="rtl">ג׳</span>, Tuesday), hour (<span dir="rtl">ט׳</span>, 9), and parts (<span dir="rtl">רד</span>, 204).

**GUCHADZaT** (<span dir="rtl">גוחאדז״ט</span>): A mnemonic for the pattern of leap years within the 19-year Metonic cycle. The letters encode years 3, 6, 8, 11, 14, 17, and 19 as the seven years in each cycle that receive an additional month (Adar I).

**Keviyyah** (<span dir="rtl">קְבִיעָה</span>, pl. <span dir="rtl">קְבִיעוֹת</span>): Literally "setting" or "fixing." The complete type-signature of a Hebrew year, specified by three parameters: the day of the week on which Rosh Hashanah falls, whether the year is deficient, regular, or complete, and whether it is ordinary or leap. Only fourteen of the twenty-four theoretical combinations actually occur. Two years with the same keviyyah have identical calendrical schedules.

**Lo ADU** (<span dir="rtl">לֹא אד״ו</span>): The first and most fundamental dehiyyah: Rosh Hashanah may not fall on Sunday (<span dir="rtl">א׳</span>), Wednesday (<span dir="rtl">ד׳</span>), or Friday (<span dir="rtl">ו׳</span>). The restriction prevents Yom Kippur from falling adjacent to Shabbat (which would create two consecutive days of full rest with no food preparation) and prevents Hoshana Rabbah from falling on Shabbat.

**Metonic cycle**: The 19-year cycle, discovered independently by the Babylonians and the Greek astronomer Meton (432 BCE), exploiting the near-coincidence that 235 synodic months equal approximately 19 solar years. The Hebrew calendar uses this cycle to determine the pattern of ordinary and leap years, inserting 7 leap years in every cycle of 19.

**Molad** (<span dir="rtl">מוֹלָד</span>, pl. <span dir="rtl">מוֹלָדוֹת</span>): Literally "birth." The calculated mean conjunction of the moon — the moment when the moon is positioned between the earth and sun, marking the astronomical new moon. The molad is computed by adding the fixed synodic month length (29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span>) to the previous month's molad. It is an arithmetic mean, not an observation, and may differ from the actual conjunction by several hours.

**Molad zaken** (<span dir="rtl">מוֹלָד זָקֵן</span>): Literally "old molad." The second dehiyyah: if the molad of Tishrei falls at or after noon (18 hours in the Hebrew day-reckoning), Rosh Hashanah is postponed to the next day (or further, if the next day is forbidden by Lo ADU). The rule reflects the principle that a molad occurring after midday cannot produce a visible crescent on that evening.

**Nasi** (<span dir="rtl">נָשִׂיא</span>): The president or patriarch of the Sanhedrin. Hillel II, the <span dir="rtl">נָשִׂיא</span> in approximately 358/359 CE, is traditionally credited with publishing the rules of the fixed calendar.

**Rosh Hashanah** (<span dir="rtl">רֹאשׁ הַשָּׁנָה</span>): The Jewish New Year, observed on 1–2 Tishrei. The date of 1 Tishrei is the primary output of the calendar algorithm: from it, the entire year's schedule is derived.

**Sanhedrin** (<span dir="rtl">סַנְהֶדְרִין</span>): The supreme rabbinical court, traditionally composed of 71 members, that held authority over calendrical decisions including the sanctification of the new month and the intercalation of leap years. Its cessation is the historical condition that necessitated the fixed calendar.

**Shanah me'uberet** (<span dir="rtl">שָׁנָה מְעֻבֶּרֶת</span>): A leap year — literally a "pregnant year." A year containing thirteen months rather than twelve, achieved by inserting Adar I (30 days) before the regular Adar. Seven of every nineteen years are leap years, following the pattern encoded in the mnemonic GUCHADZaT.

**Tekufah** (<span dir="rtl">תְּקוּפָה</span>, pl. <span dir="rtl">תְּקוּפוֹת</span>): Literally "cycle" or "turning point." Refers to the four solar seasons (equinoxes and solstices). Two different values for the tekufah are used in Jewish law: the tekufah of Shmuel (a solar year of exactly 365 days and 6 hours, identical to the Julian year) and the tekufah of Rav Adda (a more precise value derived from the 19-year cycle). The tekufah of Shmuel is used for Birkat HaChamah; the tekufah of Rav Adda underlies the calendar's intercalation logic.

**Yom tov sheni shel galuyot** (<span dir="rtl">יוֹם טוֹב שֵׁנִי שֶׁל גָּלֻיּוֹת</span>): The "second festival day of the diaspora." The practice, originating in the Talmudic period, of observing an additional day of each biblical festival (except Yom Kippur) outside the Land of Israel. It arose from the uncertainty experienced by distant communities that could not receive timely notification of the court's new-month declaration. Though the fixed calendar eliminated the original uncertainty, the practice was retained as binding custom.

---

# Bibliography

## Biblical Sources

**Exodus 12:1–2.** The foundational command establishing the month of the Exodus as "the first of months," from which the Talmud derives the lunar basis of the calendar and the court's obligation to sanctify the new moon.

**Deuteronomy 16:1.** "Observe the month of spring and make the Passover offering" — the solar constraint that requires Passover to fall in spring, generating the need for intercalation.

**Numbers 10:10; 28:11–15.** The new-moon offerings and the trumpet blasts on Rosh Chodesh, attesting to the liturgical significance of the lunar month in the sacrificial system.

## Talmudic and Rabbinic Sources

**Mishnah, Rosh Hashanah, chapters 1–4.** The primary source for the observational calendar system: witness examination, the beacon chain and its sabotage, the court's procedures for sanctifying the month, and the famous dispute between Rabban Gamliel and Rabbi Yehoshua.

**Babylonian Talmud, Rosh Hashanah 20a–25b.** Extended discussions of the court's calendrical authority, the examination of witnesses, the molad, and the legal principle that the court's declaration constitutes the calendar regardless of astronomical accuracy.

**Babylonian Talmud, Sanhedrin 10b–13b.** The rules of intercalation: who may intercalate, on what grounds, and the derivation from Deuteronomy 16:1 that the court must ensure Passover falls in its proper season.

**Babylonian Talmud, Eruvin 56a.** Astronomical calculations relevant to the tekufot, including the length of the solar year according to Shmuel.

**Pirkei de-Rabbi Eliezer, chapters 6–8.** The earliest Hebrew text to describe the 19-year intercalation cycle explicitly, with discussions of lunar and solar astronomy tied to the creation narrative. Dating is debated, likely eighth or ninth century CE.

## Rishonim and Halakhic Codes

**Maimonides (Rabbi Moshe ben Maimon).** *Mishneh Torah*, *Hilkhot Kiddush HaChodesh* (Laws of Sanctification of the New Month), composed c. 1178. Nineteen chapters covering the observational system (chs. 1–5), the fixed calendar algorithm (chs. 6–10), and astronomical visibility calculations for the new crescent (chs. 11–19). The definitive halakhic codification of the calendar and, in its later chapters, a remarkable work of mathematical astronomy preserved within a legal text.

**Abraham bar Hiyya.** *Sefer ha-Ibbur* (Book of Intercalation), 1122–1123. The first Hebrew work devoted exclusively to the calendar, explaining the principles of intercalation and providing conversion methods between the Hebrew and other calendar systems. Published by H. Filipowski (London, 1851). Influential on Maimonides and on later calendrical literature.

**Abraham ibn Ezra.** *Sefer ha-Ibbur* (Treatise on the Calendar), composed in Verona, 1146; a second version, now lost, was written somewhat later in Provence. Treats the mathematical and astronomical foundations of the intercalation cycle, with attention to the relationship between the Hebrew calendar and other Near Eastern systems.

**Tur (Rabbi Jacob ben Asher).** *Arba'ah Turim*, Orach Chaim 427–428, composed early fourteenth century. Presents the keviyyot, the Torah-reading schedules associated with each year type, and practical rules for synagogue calendar administration. The standard reference that later codes, including the Shulchan Aruch, follow.

**Shulchan Aruch (Rabbi Joseph Karo).** Orach Chaim 427–428, published 1565. Codifies the calendar rules for practical observance, including the Lo BaDU constraint on Passover and the keviyyah-based reading schedules, drawing on the Tur's framework.

## Modern Scholarship

**Stern, Sacha.** *Calendar and Community: A History of the Jewish Calendar, 2nd Century BCE – 10th Century CE.* Oxford: Oxford University Press, 2001. The most rigorous historical study of the calendar's development. Stern argues that the fixed calendar emerged gradually over several centuries rather than through a single act of promulgation by Hillel II, marshaling evidence from Geonic correspondence, liturgical poetry, and the Cairo Genizah. Essential for any serious engagement with the calendar's history.

**Reingold, Edward M. and Nachum Dershowitz.** *Calendrical Calculations: The Ultimate Edition.* 4th ed. Cambridge: Cambridge University Press, 2018. A comprehensive treatment of calendar algorithms across civilizations, with full implementations in Lisp. The Hebrew calendar chapters provide modern computational verification of the fourteen keviyyot, the Four Gates table, and the molad arithmetic. The standard reference for anyone implementing the calendar in software.

**Feldman, W.M.** *Rabbinical Mathematics and Astronomy.* 3rd ed. New York: Sepher-Hermon Press, 1978. Originally published London, 1931. A survey of mathematical and astronomical knowledge embedded in Talmudic and medieval rabbinic literature, including detailed treatment of the calendar's arithmetic. Dated in some of its historical claims but still valuable as a compendium of primary-source references.

**Burnaby, Sherrard Beaumont.** *Elements of the Jewish and Muhammadan Calendars: With Rules and Tables and Explanatory Notes on the Julian and Gregorian Calendars.* London: George Bell and Sons, 1901. A meticulous Victorian-era treatment of the calendar's mechanics, including extensive worked tables. Remarkable for its thoroughness and clarity, particularly on the relationship between the Hebrew and Islamic lunar systems.

**Ajdler, J. Jean.** "A Short History of the Jewish Fixed Calendar." *Hakirah* 20 (Winter 2015): 133–190. Also: "The Future of the Jewish Calendar." *BDD* 25 (September 2011). Ajdler, a civil engineer and historian of Jewish astronomy, has published extensively on the mathematical structure of the calendar, the historical evolution of the molad, and the long-term drift problem. His articles in *Hakirah*, *BDD* (Bar-Ilan), and *Tradition* are among the most technically precise modern treatments.

**Neugebauer, Otto.** *Ethiopic Astronomy and Computus.* Vienna: Verlag der Osterreichischen Akademie der Wissenschaften, 1979. A study of Ethiopian Christian calendar computation with significant implications for understanding the Alexandrian Jewish calendar of late antiquity. Neugebauer reconstructs the Alexandrian Jewish calendar as it existed around the fourth century, providing comparative context for the Hebrew calendar's development during the same period.

**Gauss, Carl Friedrich.** "Berechnung des judischen Osterfestes" (Calculation of the Jewish Passover). *Monatliche Correspondenz zur Beforderung der Erd- und Himmelskunde*, vol. 5 (1802): 435–437. A compact algebraic formula for computing the date of Passover in any year, presented without proof. Einstein reportedly remarked that not only could no one but Gauss have produced it, but it would never have occurred to anyone else that such a formula was possible.

**Malter, Henry.** *Saadia Gaon: His Life and Works.* Morris Loeb Series. Philadelphia: Jewish Publication Society of America, 1921. The standard biography of Saadia Gaon, including detailed treatment of his role in the tenth-century calendar dispute with the Palestinian academy — a controversy that tested the unity of the fixed calendar and demonstrated the political stakes of calendrical authority.

---

---

[^1]: The mean synodic month is approximately 29.53059 days. Individual lunations vary due to the eccentricity of the lunar orbit, ranging from about 29.27 to 29.83 days.

[^2]: The mean tropical year — the time for the sun to return to the same equinox point — is approximately 365.2422 days. The sidereal year (return to the same stellar position) is slightly longer at approximately 365.2564 days. The Hebrew calendar's implicit solar year length, derived from its 19-year intercalation cycle, is closer to 365.2468 days.

[^3]: More precisely: the ratio of the synodic month to the tropical year is approximately 12.36827, an irrational number. The 19-year Metonic cycle exploits the fact that 235 synodic months is very close to 19 tropical years — the best rational approximation with a small denominator.

[^4]: The Islamic (Hijri) calendar consists of 12 lunar months totaling 354 or 355 days per year, with no intercalary month. See Quran 9:36–37, which has been interpreted as prohibiting intercalation.

[^5]: The Gregorian calendar, introduced by Pope Gregory XIII in 1582, refined the Julian calendar's leap-year rule to better approximate the tropical year. Its months have no relationship to the lunar cycle.

[^6]: Other lunisolar calendars include the Chinese, Hindu, and Tibetan calendars. Each solves the reconciliation problem differently, though several share the 19-year (Metonic) cycle with the Hebrew calendar.

[^7]: Exodus 12:2.

[^8]: Deuteronomy 16:1.

[^9]: Babylonian Talmud, Sanhedrin 13b. The Talmud derives from <span dir="rtl">שָׁמוֹר אֶת חֹדֶשׁ הָאָבִיב</span> that the court must ensure Passover falls in the spring season, which requires periodic intercalation of a thirteenth month.

[^10]: "Synodic" from the Greek *synodos*, meaning meeting or conjunction — the period between successive conjunctions of the moon with the sun as seen from earth.

[^11]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:3. The value appears in the Talmud at Rosh Hashanah 25a in the context of calendrical testimony, though its most explicit formulation as a precise value used for calculation is in the post-Talmudic codification. The same value appears in Ptolemy's *Almagest* (2nd century CE) and traces ultimately to Babylonian astronomical records; see Otto Neugebauer, *The Exact Sciences in Antiquity* (1957), ch. 5. [Verify: whether the exact figure 29d 12h 793p appears explicitly in the Babylonian Talmud at Rosh Hashanah 25a, or whether it is inferred from the discussion there and stated explicitly only in later sources such as Pirkei de-Rabbi Eliezer ch. 7 and the Baraita de-Shmuel]

[^12]: The current IAU-adopted mean synodic month is 29.530589 days (29d 12h 44m 2.88s). See Jean Meeus, *Astronomical Algorithms*, 2nd ed. (1998), ch. 49. The traditional Jewish value of 29d 12h 44m 3.33s exceeds this by approximately 0.45 seconds per lunation.

[^13]: The attribution to Hillel II and the dating to approximately 358/359 CE is traditional but not without scholarly dispute. Sacha Stern, *Calendar and Community: A History of the Jewish Calendar, 2nd Century BCE–10th Century CE* (Oxford, 2001), argues that the fixed calendar emerged gradually over several centuries rather than through a single act of promulgation. What is clear is that by the period of the Geonim (roughly 7th–11th centuries), the fixed calendar was universally accepted.

[^14]: Mishnah, Rosh Hashanah, chapters 1–3. Chapter 1 discusses who may testify, chapter 2 describes the examination of witnesses and the beacon system, and chapter 3 addresses the court's procedures.

[^15]: Mishnah, Rosh Hashanah 2:8; Babylonian Talmud, Rosh Hashanah 24a–b.


[^16]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:2. The *chelek* is defined as 1/1,080 of an hour. The term <span dir="rtl">חלק</span> literally means "portion" or "part." The number 1,080 = 2³ × 3³ × 5 has 32 divisors — an exceptionally high count for a number of its magnitude (by comparison, 1,000 has 16 and 1,024 has 11). Maimonides does not explain the choice of 1,080 explicitly, but the arithmetic convenience is evident throughout Hilkhot Kiddush HaChodesh chapters 6–10.

[^17]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:3. This value — 29 days, 12 hours, and 793 chalakim — is stated as the duration of the mean synodic month and is the single most important constant in the calendar.

[^18]: This comparison is structural, not evaluative. The Gregorian calendar was designed for simplicity: its arithmetic uses no unit smaller than the day, and its corrections (leap years, century rules) are easy to remember and apply. The Hebrew calendar was designed for precision: its finer unit eliminates rounding error at the cost of more complex calculation. Each design reflects its priorities.

[^19]: The modern measured mean synodic month is approximately 29.53058868 days. The calendar's value of 29 days, 12 hours, 793 chalakim equals 29.53059414 days. The difference is about 0.6 seconds per month. See Jean Meeus, *Astronomical Algorithms*, 2nd ed. (Richmond, VA: Willmann-Bell, 1998), ch. 49. [Verify: exact current value of mean synodic month from a 2020s astronomical reference.]

[^20]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:1–3. The term <span dir="rtl">מולד</span> derives from the root <span dir="rtl">י-ל-ד</span> ("to give birth"); the new moon is the "birth" of the lunar month. Maimonides distinguishes sharply between the *molad ha-amiti* (the true, astronomical conjunction) and the *molad ha-emtza'i* (the mean conjunction used in the calendar). The former varies due to the elliptical shape of the lunar orbit; the latter is a mathematical idealization. See also the extended astronomical discussion in chapters 11–17.

[^21]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:8. BaHaRaD (<span dir="rtl">בהר״ד</span>) encodes the three components of the epoch: <span dir="rtl">ב</span> = 2 (day of week), <span dir="rtl">ה</span> = 5 (hours), <span dir="rtl">ר״ד</span> = 204 (chalakim). The name is a mnemonic, not an acronym.

[^22]: The correspondence of Year 1 to 3761 BCE follows the traditional rabbinic chronology of *Seder Olam Rabbah*, attributed to the Tanna Rabbi Yose ben Halafta (2nd century CE). This chronology counts years from creation (<span dir="rtl">בריאת העולם</span>). The epoch was fixed retrospectively; no one used the calculated calendar in 3761 BCE. See *Seder Olam Rabbah*, chapters 1–30.

[^23]: The algorithm as presented follows Maimonides, Hilkhot Kiddush HaChodesh 6:8–14. Maimonides gives the computation in a slightly different form, using pre-computed remainders for 1, 10, 100, and 1,000 months (6:11–12), but the mathematical content is identical. The component-by-component method (multiply separately by 29, 12, and 793, then cascade the carries) is equivalent to multiplying by the full month-length in chalakim and decomposing the result.

[^24]: This result can be verified by any standard Hebrew calendar calculator. September 11, 2026 is a Friday; the molad on Friday evening at approximately 8:59 PM falls within the Hebrew day of Shabbat, which begins at sunset on Friday. [Verify: cross-check against hebcal.com or a similar calculator for molad Tishrei 5787.]

[^25]: The Islamic (Hijri) calendar is a purely lunar calendar with no intercalation. Its year of 354 or 355 days is roughly 11 days shorter than the solar year, causing its months to cycle through all seasons over approximately 33 years. For the prohibition of intercalation in Islamic law, see Qur'an 9:36–37.

[^26]: 235 × 29.53059 days = 6,939.69 days; 19 × 365.24682 days = 6,939.69 days. The calendar's implicit solar year (365.24682 days) differs slightly from the modern tropical year (365.24219 days). Using the modern value, 19 tropical years = 6,939.60 days, yielding a discrepancy of about 0.09 days (approximately 2 hours and 7 minutes) per 19-year cycle, or about 6 minutes 41 seconds per year — one full day every 216 years.

[^27]: The mnemonic GUCHADZaT (<span dir="rtl">גו״ח אדז״ט</span>) is widely cited in halakhic works on the calendar. See, e.g., Tur, *Orach Chaim* 428; Maimonides, Hilkhot Kiddush HaChodesh 6:11. Equivalently, year *Y* is a leap year if (7*Y* + 1) mod 19 < 7.

[^28]: The claim that GUCHADZaT achieves optimal uniformity can be verified by exhaustive enumeration of the C(19,7) = 50,388 possible placements of 7 leap years in 19 slots, or more elegantly by observing that it is the unique Euclidean distribution (up to rotation and reflection) of 7 items in 19 positions. On Euclidean rhythms and their optimality, see Godfried Toussaint, "The Euclidean Algorithm Generates Traditional Musical Rhythms," *Proceedings of BRIDGES* (2005), 47–56.

[^29]: On the Metonic cycle's origins: Diodorus Siculus, *Bibliotheca Historica* 12.36.2, places Meton's announcement at the Olympic games of 432 BCE. On the relationship to Babylonian intercalation schemes, see John P. Britton, "Treatments of Annual Phenomena in Cuneiform Sources," in *Under One Sky: Astronomy and Mathematics in the Ancient Near East*, ed. J. M. Steele and A. Imhausen (Münster: Ugarit-Verlag, 2002), 21–78. For the argument that the Jewish calendar adopted Babylonian practices, see Sacha Stern, *Calendar and Community: A History of the Jewish Calendar, 2nd Century BCE–10th Century CE* (Oxford: Oxford University Press, 2001), ch. 2. The cycle appears in *Pirkei de-Rabbi Eliezer*, chapter 8, which describes <span dir="rtl">מחזור החמה</span>, the "cycle of the sun," as completing in 19 years.

[^30]: Babylonian Talmud, Sanhedrin 10b–13b. The Talmudic discussion addresses the criteria for intercalation (adding a second Adar), including agricultural conditions (the state of the barley crop, the ripeness of fruits) and calendrical considerations. The fixed calendar's mechanical intercalation pattern replaced this deliberative process. See also Rosh Hashanah 20a–25a on the declaration of new months by the court. By the time of Maimonides (Hilkhot Kiddush HaChodesh 6:10–14), the Metonic cycle's parameters were presented as settled law, not as astronomical findings subject to revision.


[^31]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:1. The Talmudic basis appears in Rosh Hashanah 20a.

[^32]: The willow ceremony on Hoshanah Rabbah is discussed in Mishnah Sukkah 4:5–6 and elaborated in Talmud Bavli, Sukkah 43b–44a. When Hoshanah Rabbah falls on Shabbat, the ceremony must be omitted, which the calendar's designers considered unacceptable.

[^33]: The prohibition of burial on Yom Kippur follows from the general rule that Yom Kippur carries all the restrictions of Shabbat (Mishnah Megillah 1:5; Maimonides, *Mishneh Torah*, Hilkhot Shevitat Asor 1:1). Two consecutive days without burial — Yom Kippur followed by Shabbat — was deemed an intolerable burden on the community.

[^34]: The same burial logic applies in reverse: Shabbat followed by Yom Kippur creates a two-day barrier. Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:1, lists both the Wednesday and Friday prohibitions under the same rationale.

[^35]: Tur, Orach Chaim 428; Shulchan Aruch, Orach Chaim 428:3. The AT BASH mnemonic appears in both sources with six pairs. A seventh pair (<span dir="rtl">ז״ע</span>) linking the 7th day of Pesach to Yom Ha'atzmaut (5 Iyar) — 14 days apart, same day of the week — is a modern addition. [Verify: exact attribution of the 7th pair; some sources credit 20th-century Israeli rabbinical authorities.]

[^36]: The interval from 15 Nisan to 9 Av is exactly 112 days. Since 112 = 16 × 7, the two dates always fall on the same day of the week. When Tisha B'Av coincides with Shabbat, the fast is postponed to Sunday (10 Av), but the underlying calendrical equivalence holds regardless.

[^37]: The interval from 16 Nisan (the second day of Pesach) to 6 Sivan (Shavuot) is exactly 49 days — the seven weeks of the Omer count. Since 49 = 7 × 7, the two dates always share a weekday.

[^38]: Each pair in the AT BASH mnemonic reflects a fixed interval divisible by 7: Pesach to Tisha B'Av = 112 days; 2nd Pesach to Shavuot = 49 days; 6th day of Pesach to Purim = a fixed interval within the same year dependent on month lengths, but always divisible by 7. The mnemonic works because the calendar's month lengths are fixed (with the sole variations in Cheshvan and Kislev, which do not fall between any of the paired holidays).

[^39]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:2. The threshold of 18 hours corresponds to noon because the Hebrew day begins at 6:00 PM: hour 0 = 6:00 PM, hour 6 = midnight, hour 12 = 6:00 AM, hour 18 = noon.

[^40]: The astronomical rationale is discussed in Talmud Bavli, Rosh Hashanah 20b, which states that the "old moon" is hidden for 24 hours around the conjunction — approximately 6 hours before and 18 hours after. If the molad occurs before noon, the new crescent may be visible by sunset (about 6 hours later). If it occurs at noon or after, the crescent will not appear until the *following* sunset. Maimonides provides a detailed astronomical treatment of lunar visibility in Hilkhot Kiddush HaChodesh chapters 15–19.

[^41]: The cascading of molad zaken into Lo ADU produces the only two-day postponement in the standard (non-GaTRaD) system. Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:2–3, treats these as sequential applications of independent rules.

[^42]: Aaron ben Meir argued for a threshold of 642 chalakim before 18 hours, which equals approximately 35 minutes and 40 seconds. His tradition appears to have been a local Palestinian practice. The standard Babylonian threshold of exactly 18h 0p is the one preserved in all subsequent calendar calculations.

[^43]: The primary source for the Ben Meir controversy is reconstructed from the genizah fragments edited by Henry Malter, *Saadia Gaon: His Life and Works* (Philadelphia, 1921), and more recently in Sacha Stern, *The Jewish Calendar Controversy of 921/2 CE* (Leiden: Brill, 2019). The dispute demonstrates that the calendar parameters, though seemingly abstract, had immediate practical consequences for the entire Jewish world.

[^44]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:4. The time 9h 204p corresponds to 3:11:20 AM on Tuesday morning: hour 9 = 3:00 AM (since hour 0 = 6:00 PM), and 204 chalakim = 204 × 3⅓ seconds = 680 seconds = 11 minutes and 20 seconds.

[^45]: The arithmetic: 12 × 29d 12h 793p = 354d 8h 876p. Dividing by 7: 354 = 50 × 7 + 4, so the day-of-week offset is 4 days, plus 8 hours and 876 chalakim carried forward from the sub-day remainder.

[^46]: The six valid year lengths — 353, 354, 355, 383, 384, and 385 — arise from the two variable months, Cheshvan and Kislev. In a deficient (<span dir="rtl">חסרה</span>) year, both have 29 days. In a regular (<span dir="rtl">כסדרה</span>) year, Cheshvan has 29 and Kislev has 30. In a complete (<span dir="rtl">שלמה</span>) year, both have 30. The base lengths are 354 (ordinary) and 384 (leap), with ±1 day of adjustment in each direction. Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 8:5–6.

[^47]: GaTRaD occurrences cluster at intervals related to the 19-year cycle. Recent and upcoming instances include 5718 (1957–58), 5745 (1984–85), 5789 (2028–29), and 5796 (2035–36).

[^48]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:5. The time 15h 589p corresponds to 9:32:43 AM on Monday morning: hour 15 = 9:00 AM, and 589 chalakim = 589 × 3⅓ seconds ≈ 1963 seconds = 32 minutes and 43 seconds.

[^49]: BeTUTKaPoT occurrences include 5715 (1954–55), 5766 (2005–06), and 5813 (2052–53). The intervals between occurrences are irregular and can span several decades.

[^50]: These frequencies apply over the full 689,472-year cycle of the Hebrew calendar. In any given century, the distribution may vary slightly. The 39/47/14 percent breakdown (no postponement / one day / two days) is from the complete cycle statistics. See Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 7:1–7, for the authoritative statement of all four rules.


[^51]: Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 8:5–6. The six possible year lengths and their relationship to Cheshvan and Kislev are stated explicitly.

[^52]: The terminology appears throughout the medieval calendrical literature. "Deficient" (<span dir="rtl">חסרה</span>) and "complete" (<span dir="rtl">שלמה</span>) describe the year relative to the "regular" (<span dir="rtl">כסדרה</span>) baseline of strict alternation (30-29-30-29...). Maimonides, HKH 8:5.

[^53]: The arithmetic: a regular ordinary year follows strict alternation: Tishrei 30, Cheshvan 29, Kislev 30, Tevet 29, Shevat 30, Adar 29, Nisan 30, Iyar 29, Sivan 30, Tammuz 29, Av 30, Elul 29 = 354 days. A deficient year changes Kislev from 30 to 29, yielding 353. A complete year changes Cheshvan from 29 to 30, yielding 355. In a leap year, Adar I (30 days) is inserted before Adar II (29 days), adding 30 to each baseline: 383, 384, 385. Maimonides, HKH 8:5–6.

[^54]: This constraint is not stated explicitly by Maimonides as a separate rule but follows from the structure: the adjustment mechanism first extends Cheshvan (to make a complete year) or shortens Kislev (to make a deficient year), never shortens Cheshvan while extending Kislev. See HKH 8:6.

[^55]: Maimonides, HKH 8:7. "Once you know the day on which Rosh Hashanah of a given year falls, and the day on which Rosh Hashanah of the following year falls, you will know the character of that year."

[^56]: Maimonides, *Mishneh Torah*, Hilkhot Tefillah 13:1–4. The reading cycle, its division into weekly portions, and the rules for doubling portions in shorter years are discussed here. The connection between year type and reading schedule is made explicit.

[^57]: The term <span dir="rtl">קביעה</span> derives from the root <span dir="rtl">ק-ב-ע</span>, meaning to fix or establish. In calendrical usage, it refers to the complete characterization of the year type. See Tur, Orach Chaim 428; Maimonides, HKH 8:7.

[^58]: The four permitted days for Rosh Hashanah — Monday, Tuesday, Thursday, Saturday — are a consequence of dehiyyah Lo ADU, discussed in Part III. In Hebrew numerical notation, these are days <span dir="rtl">ב, ג, ה, ז</span> of the week.

[^59]: The fourteen keviyyot are enumerated in Maimonides, HKH 8:7–9, and in the Tur, Orach Chaim 428. Reingold and Dershowitz, *Calendrical Calculations: The Ultimate Edition* (Cambridge, 2018), pp. 92–95, provide a modern tabulation and verify computationally that exactly fourteen types occur. [Verify: confirm the exact list of 14 keviyyot matches — cross-check Passover days against Reingold-Dershowitz Table 8.1 and Maimonides HKH 8:7–9]

[^60]: The impossibility of certain combinations can be demonstrated arithmetically. A Monday regular ordinary year would have 354 days; since 354 mod 7 = 4, the following Rosh Hashanah would fall on Friday (Monday + 4), violating Lo ADU. A Tuesday deficient ordinary year (353 days; 353 mod 7 = 3) would push the next Rosh Hashanah to Friday (Tuesday + 3), also violating Lo ADU. A Saturday regular ordinary year (354 days; 354 mod 7 = 4) gives Wednesday (Saturday + 4), violating Lo ADU; a Saturday regular leap year (384 days; 384 mod 7 = 6) gives Friday (Saturday + 6), again violating Lo ADU. Each impossible keviyyah can be excluded by this kind of modular arithmetic argument.

[^61]: In an ordinary regular year, Passover (15 Nisan) falls 191 days after 1 Tishrei: Tishrei(30) + Cheshvan(29) + Kislev(30) + Tevet(29) + Shevat(30) + Adar(29) = 177 days through the end of Adar, plus 14 more days to reach 15 Nisan = 191. Since 191 = 27 × 7 + 2, the day-of-week offset is +2. A deficient year (Kislev drops to 29) reduces this to 190 days, offset +1. A complete year (Cheshvan gains to 30) increases it to 192 days, offset +3. In a leap year, the 30-day Adar I adds 30 to each: 220, 221, or 222 days, with offsets +3, +4, or +5 respectively.

[^62]: The Lo BaDU rule for Passover — that the first day of Passover never falls on Monday (<span dir="rtl">ב</span>), Wednesday (<span dir="rtl">ד</span>), or Friday (<span dir="rtl">ו</span>) — is documented in the Tur, Orach Chaim 428, and is a well-known mnemonic in traditional calendrical instruction. It is a consequence, not a separate rule: it falls out automatically from the Lo ADU rule for Rosh Hashanah combined with the constraints on year length. See also Shulchan Aruch, Orach Chaim 428:1.

[^63]: The three-letter keviyyah notation is described in the Tur, Orach Chaim 428, and used extensively in traditional Hebrew calendar tables (<span dir="rtl">לוחות</span>). Maimonides does not use this particular shorthand but his presentation in HKH 8:7–9 contains all the same information.

[^64]: Tur, Orach Chaim 428. The Tur's treatment of the keviyyot and their associated Torah reading schedules became the basis for the Shulchan Aruch's parallel discussion and for the calendar tables printed in standard prayer books.

[^65]: Maimonides, HKH 8:9–10. The term "Four Gates" (<span dir="rtl">ארבעה שערים</span>) appears in the commentarial literature on Maimonides and in medieval calendrical treatises. The four gates correspond to the four permitted days for Rosh Hashanah.

[^66]: The 19-year cycle and its leap-year positions {3, 6, 8, 11, 14, 17, 19} are discussed in Part II. The mnemonic GUCHADZaT (<span dir="rtl">גו״ח אדז״ט</span>) encodes these positions.

[^67]: The counting of total months from the epoch is described in Maimonides, *Mishneh Torah*, Hilkhot Kiddush HaChodesh 6:10–11. The procedure — count completed 19-year cycles, multiply by 235, add the months in remaining years — is a standard technique for reducing a large calculation to a manageable one.

[^68]: The day-of-week convention used here follows the traditional Hebrew reckoning: day 1 = Sunday (<span dir="rtl">יום ראשון</span>), day 2 = Monday, through day 7 = Shabbat. In modular arithmetic with the epoch starting on day 2 (Monday), a result of 0 mod 7 corresponds to Shabbat. See Maimonides, HKH 6:7–8.

[^69]: The molad times announced in synagogues — typically given in hours and minutes after some reference point — correspond to this same calculation. For Tishrei 5787, the molad announcement would state: <span dir="rtl">מולד תשרי ליל שבת קדש בשעה שמונה בערב חמישים ותשע דקות וחלק אחד</span> — "The molad of Tishrei: the night of holy Shabbat, at eight o'clock in the evening, fifty-nine minutes and one <span dir="rtl">חֵלֶק</span>."

[^70]: The absence of any dehiyyah for year 5787 is itself noteworthy. Roughly 39% of years require at least one postponement; the remaining 61% have Rosh Hashanah fall directly on the day of the molad. Maimonides, HKH 7:1–8, describes the complete dehiyyah procedure.

[^71]: The molad for the following year is computed by adding the appropriate number of months (12 for an ordinary year, 13 for a leap year) to the current molad. Since each month is exactly 29d 12h 793p, the calculation is a single multiplication and addition. Maimonides, HKH 6:11–12.

[^72]: The keviyyah for year 5787 is <span dir="rtl">זש״ה</span>: Rosh Hashanah on Shabbat (<span dir="rtl">ז</span>), complete (<span dir="rtl">ש</span>), Passover on Thursday (<span dir="rtl">ה</span>). This is keviyyah #14 in the table from Part IV.

[^73]: The epoch of 1 Tishrei Year 1 = approximately October 7, 3761 BCE (Julian) is discussed in Maimonides, HKH 6:8. The correspondence to BaHaRaD — the molad falling on Monday (day 2), 5 hours, 204 <span dir="rtl">חֲלָקִים</span> — is a mathematical anchoring, not a historical claim about the date of creation. See also Seder Olam Rabbah, chapter 1, for the traditional chronology.

[^74]: Reingold and Dershowitz formalize this approach through the concept of a "fixed date" (Rata Die), a continuous day count that serves as the intermediate representation for all calendar conversions. See Edward M. Reingold and Nachum Dershowitz, *Calendrical Calculations: The Ultimate Edition*, 4th ed. (Cambridge University Press, 2018), ch. 1.

[^75]: Carl Friedrich Gauss, "Berechnung des jüdischen Osterfestes," *Monatliche Correspondenz zur Beförderung der Erd- und Himmelskunde*, vol. 5 (May 1802), pp. 435–437. Reprinted in Gauss's *Werke*, vol. 6, pp. 80–81. [Verify: exact page numbers in the Werke — some sources cite vol. 6 pp. 80–81, others cite vol. 11.]

[^76]: The decimal constants in the Gauss formula encode the calendar's fundamental parameters. The value 1.5542418 derives from the ratio of the molad excess (the amount by which 12 lunar months fall short of a solar year) to the Metonic cycle correction. The value 0.0031777 captures the drift between the Julian and Hebrew year lengths. See the derivation in Wolfgang Alexander Shocken, *The Calculated Confusion of Calendars* (New York, 1976), pp. 51–56.

[^77]: M. Hamburger published his proof of Gauss's formula in 1896. Albert Einstein reportedly remarked that not only could no one but Gauss have produced the formula, but it would never have occurred to anyone but Gauss that such a formula was possible. [Verify: exact citation for Hamburger's proof — some sources give *Journal für die reine und angewandte Mathematik*, 1896. Also verify the Einstein attribution, which may be apocryphal.]

[^78]: The O(1) computational complexity of the Hebrew calendar is noted in Reingold and Dershowitz, *Calendrical Calculations*, 4th ed., p. 89. No iteration or recursion is required; every step of the algorithm involves a fixed number of arithmetic operations regardless of the year number.

[^79]: Edward M. Reingold and Nachum Dershowitz, *Calendrical Calculations: The Ultimate Edition*, 4th ed. (Cambridge University Press, 2018). The Hebrew calendar algorithms appear in chapters 8–9. The book covers conversions between more than 30 calendar systems, all implemented and cross-validated.

[^80]: The traditional dating of the fixed calendar to Hillel II, circa 358–359 CE, is discussed in Part I, footnote 13. On the calendar's uninterrupted operation since that period, see Sacha Stern, *Calendar and Community: A History of the Jewish Calendar, 2nd Century BCE–10th Century CE* (Oxford University Press, 2001), who argues that the system reached its final form somewhat later but agrees that it has been stable and universal since at least the Geonic period.

[^81]: Babylonian Talmud, Eruvin 56a. Shmuel states that each tekufah lasts 91 days and 7½ hours, yielding a solar year of 365 days and 6 hours. Maimonides codifies this in Hilkhot Kiddush HaChodesh 9:1–3.

[^82]: The calculation: 91 days × 4 = 364 days; 7h 540p × 4 = 30 hours 2,160p = 30 hours + 2 hours (since 2,160 ÷ 1,080 = 2) = 32 hours = 1 day 8 hours. Wait: 30 hours = 1 day 6 hours. Total: 364 + 1 = 365 days, 6 hours. The arithmetic works cleanly. Maimonides, HKH 9:3. [Verify: confirm that 7h 540p × 4 = 30h 2160p = 32h 0p = 1d 8h. Actually 7h 540p × 4 = 28h 2160p. 2160p = 2h. So 28+2 = 30h = 1d 6h. 364d + 1d 6h = 365d 6h. Correct.]

[^83]: The 28-year solar cycle: 28 × (1d 6h) = 28d + 168h = 28d + 7d = 35 days = 5 complete weeks. Therefore the tekufah returns to the same day of the week and same time of day after 28 years. This is known as <span dir="rtl">מַחֲזוֹר גָּדוֹל</span> (the "great cycle") or <span dir="rtl">מַחֲזוֹר הַחַמָּה</span> (the "solar cycle"). See Maimonides, HKH 9:2; Babylonian Talmud, Berakhot 59b.

[^84]: Birkat HaChamah was last recited on Wednesday, April 8, 2009 (14 Nisan 5769 = Erev Pesach). The next occurrence is Wednesday, April 8, 2037 (23 Nisan 5797). The Shulchan Aruch, Orach Chaim 229:2, codifies the blessing. The coincidence with Erev Pesach in 2009 is itself noteworthy: it occurs only four times in the current era of the 28-year cycle.

[^85]: Babylonian Talmud, Ta'anit 10a. The Talmud rules that the diaspora begins requesting rain from the 60th day after Tekufat Tishrei, based on the Babylonian climate. Shulchan Aruch, Orach Chaim 117:1.

[^86]: The drift rate is approximately one day every 128 years (since the difference between Shmuel's year and the Gregorian year is about 11 minutes and 15 seconds per year, and 128 × 11.25 minutes ≈ 1 day). In the 16th century, the 60th day after Tekufat Tishrei typically fell on or around November 22 (Julian) or December 2 (Gregorian, after 1582). By the 21st century it typically falls on December 4–6 (Gregorian). See Ephraim Tabory, "The Controversy Concerning the Date of Beginning the Recitation of the Prayer for Rain," *Sidra* 2 (1986), pp. 171–186. [Verify: exact citation for Tabory article.]

[^87]: Rav Adda bar Ahavah's year length is not stated explicitly in the Babylonian Talmud but is derived by later authorities from the Metonic cycle parameters. Maimonides presents the value in Hilkhot Kiddush HaChodesh 9:1 and 10:1–6, noting it as the more accurate of the two tekufot. The <span dir="rtl">רֶגַע</span> (rega, plural <span dir="rtl">רְגָעִים</span>) — 1/76 of a <span dir="rtl">חֵלֶק</span> — is the finest unit in the calendar's arithmetic.

[^88]: The derivation: 235 × 765,433 = 179,876,755. Then 179,876,755 ÷ 19 = 9,467,197 remainder 12. The 12 remaining <span dir="rtl">חֲלָקִים</span> over 19 years means 12/19 <span dir="rtl">חֲלָקִים</span> per year. Since 1 <span dir="rtl">חֵלֶק</span> = 76 <span dir="rtl">רְגָעִים</span>, this fraction equals (12 × 76) / 19 = 912 / 19 = 48 <span dir="rtl">רְגָעִים</span> exactly. The choice of 76 as the subdivision of the <span dir="rtl">חֵלֶק</span> is not arbitrary — 76 = 4 × 19, ensuring this division comes out exact.

[^89]: Rav Adda's year: 365.24682 days. The modern tropical year: 365.24219 days. Shmuel's year: 365.25000 days. The errors are approximately 6.67 minutes/year (Rav Adda) and 11.25 minutes/year (Shmuel). For comparison, the Julian calendar's year (identical to Shmuel's) accumulated an error of about 13 days by the time of the Gregorian reform in 1582. Rav Adda's value would have accumulated only about 7.7 days over the same period.

[^90]: Maimonides, HKH 9:1–4 (Shmuel's tekufah) and 10:1–6 (Rav Adda's tekufah). In 10:6, Maimonides states that Rav Adda's value is the one relied upon by the Great Court (<span dir="rtl">בית דין הגדול</span>) for purposes of intercalation — that is, for determining the leap-year pattern. This is the passage that establishes Rav Adda's tekufah as the one embedded in the calendar's actual structure. [Verify: exact halakha number in chapter 10 — some editions number differently.]

[^91]: The thermostat analogy is apt in another way: like a thermostat, the Hebrew calendar exhibits a form of negative feedback. If the lunar months drift too far ahead of the solar year, a leap month (the extra Adar) pulls them back. If they fall behind, the absence of a leap month in an ordinary year lets them catch up. The Metonic cycle ensures this feedback operates on a 19-year schedule, with seven corrections (leap months) per cycle. The result is bounded oscillation: Passover wanders within a roughly 30-day window centered on the equinox, never escaping, always returning.


[^92]: The Sanhedrin's migrations are enumerated in the Babylonian Talmud, Rosh Hashanah 31a–b. The sequence reflects the progressive dislocation of Jewish institutional life from Jerusalem following the destruction of the Second Temple in 70 CE and the failed Bar Kokhba revolt of 132–135 CE.

[^93]: The abolition of the patriarchate is documented in a series of Roman imperial edicts. Theodosius II's *Novella* 3 (issued 438 CE) is commonly cited as formalizing the end of the institution, though its practical authority had been declining for decades. See Lee I. Levine, *The Rabbinic Class of Roman Palestine in Late Antiquity* (Jerusalem, 1989), ch. 7, for the broader context of the patriarchate's decline.

[^94]: The dating of approximately 358/359 CE appears in multiple medieval sources and has become the conventional date in rabbinic literature. See also Part I, footnote 13, and the discussion in Stern, *Calendar and Community*, pp. 157–175. [Verify: exact page range in Stern for the Hillel II discussion — the chapter "The Nasi and the Calendar" is the relevant section but page numbers should be confirmed against the 2001 Oxford edition]

[^95]: The key text is a responsum of Rav Hai Gaon (939–1038 CE), head of the academy at Pumbedita, written in response to a question about the calendar's origins. Hai Gaon attributes the fixed calendar to "Hillel the son of Rabbi Yehuda, in the year 670 of the Seleucid era" (≈ 358/359 CE). The responsum is preserved in several medieval collections. See Stern, *Calendar and Community*, pp. 175–178, for the text and discussion. Also discussed in Abraham Ibn Daud, *Sefer HaQabbalah* (1161 CE), which relies on Hai Gaon's testimony. [Verify: exact citation format for Hai Gaon's responsum — it is commonly referenced but the original text survives only in fragmentary or secondary sources, and the precise manuscript tradition should be confirmed]

[^96]: The minimalist view — that Hillel II fixed the intercalation sequence but not the full dehiyyah system — is argued by Stern, *Calendar and Community*, ch. 8. The maximalist view, that the full system was published at once, is the traditional position found in most rabbinic sources from the medieval period onward.

[^97]: Sacha Stern, *Calendar and Community: A History of the Jewish Calendar, 2nd Century BCE – 10th Century CE* (Oxford University Press, 2001). Stern's argument rests on three pillars: the silence of contemporary sources regarding Hillel II's reform, the evidence of continued calendar variation in the Geonic period, and the implausibility of a single promulgation producing a system whose parameters were still contested in the tenth century. The book remains the definitive scholarly treatment of the calendar's historical development.

[^98]: The Cairo Genizah was brought to European scholarly attention primarily through Solomon Schechter's visit to Cairo in 1896–1897, during which he acquired approximately 140,000 fragments for the Cambridge University Library (the Taylor-Schechter Collection). The total number of fragments across all collections worldwide exceeds 300,000. See Stefan C. Reif, *A Jewish Archive from Old Cairo: The History of Cambridge University's Genizah Collection* (Richmond, 2000), for the discovery and its significance.

[^99]: Stern, *Calendar and Community*, ch. 9, discusses the Genizah calendar documents in detail. Key fragments include liturgical calendars and calendar tables that reflect different computational assumptions from those of the settled Babylonian tradition. [Verify: specific T-S (Taylor-Schechter) fragment numbers for the calendar documents discussed by Stern — e.g., T-S K 2.28, T-S 6H 3.5, and others referenced in his chapter on the Genizah evidence]

[^100]: The 642-<span dir="rtl">חֲלָקִים</span> figure and Ben Meir's proposed threshold are discussed in detail in Henry Malter, *Saadia Gaon: His Life and Works* (Philadelphia: Jewish Publication Society, 1921), pp. 69–88, and in Stern, *Calendar and Community*, ch. 10. Ben Meir's claim may have been based on an older Palestinian tradition — possibly a variant reading of the molad zaken rule that differed from the Babylonian version. [Verify: Malter's exact page numbers for the Ben Meir controversy; also confirm whether Ben Meir's threshold was 17h 438p or whether the 642p offset should be computed differently — the literature contains some inconsistency in how the variant is expressed]

[^101]: Saadia Gaon's arguments against Ben Meir survive in fragments discovered in the Cairo Genizah. See Malter, *Saadia Gaon*, pp. 69–88; also Alexander Marx, "The Correspondence between the Rabbis of Southern France and Maimonides about Astrology," *HUCA* 3 (1926), which provides context for how calendar disputes were resolved through correspondence and scholarly authority.  [Verify: Marx's article may not be the best citation for the Ben Meir controversy specifically — the primary Genizah texts of Saadia's anti-Ben Meir writings are published in various collections; confirm the most appropriate citation]

[^102]: The institutional dimension of the Ben Meir controversy — Palestinian claims to calendar authority versus Babylonian claims — is analyzed in Stern, *Calendar and Community*, ch. 10, and in Robert Brody, *The Geonim of Babylonia and the Shaping of Medieval Jewish Culture* (New Haven: Yale University Press, 1998), pp. 45–48. [Verify: Brody's exact page references for the Ben Meir discussion]

[^103]: The argument that the fixed calendar reached its final, universally accepted form only in the tenth–twelfth century period is Stern's central thesis. The Ben Meir controversy of 921–922 CE is the last documented dispute over the calendar's parameters; after its resolution, the system described by Maimonides in the twelfth century appears to have been universally accepted.

[^104]: Maimonides, <span dir="rtl">מִשְׁנֶה תּוֹרָה</span>, <span dir="rtl">הִלְכוֹת קִדּוּשׁ הַחֹדֶשׁ</span>. The work was completed approximately 1178 CE. It is placed in the <span dir="rtl">סֵפֶר זְמַנִּים</span> (Book of Seasons), the third book of the fourteen-book <span dir="rtl">מִשְׁנֶה תּוֹרָה</span>.

[^105]: Maimonides' astronomical chapters draw on Ptolemaic methods as transmitted through Arabic astronomical traditions, particularly the work of al-Battānī (c. 858–929 CE). See Y. Tzvi Langermann, "Maimonides' Repudiation of Astrology," *Maimonidean Studies* 2 (1991): 123–158, and José Luis Mancha, "The Latin Translation of Levi ben Gerson's Astronomy," in *Studies on Gersonides*, ed. Gad Freudenthal (Leiden, 1992), for the broader context of Jewish engagement with Ptolemaic astronomy. Neugebauer provides a technical comparison of Maimonides' parameters with those of his Islamic predecessors in Otto Neugebauer, "The Astronomy of Maimonides and Its Sources," *HUCA* 22 (1949): 321–363. [Verify: Neugebauer HUCA article — confirm exact title, volume, and page numbers]

[^106]: Maimonides, <span dir="rtl">הִלְכוֹת קִדּוּשׁ הַחֹדֶשׁ</span> 5:2–3. Maimonides writes that when there is no Sanhedrin, the calendar calculations serve in place of the court's declarations, and that all of Israel relies on these calculations. The implication — stated more explicitly in his introduction to the section — is that when a Sanhedrin is reconstituted, the observational system resumes and the fixed calendar becomes unnecessary.

[^107]: The 689,472-year cycle is discussed in Edward M. Reingold and Nachum Dershowitz, *Calendrical Calculations: The Ultimate Edition* (Cambridge University Press, 2018), §9.1, and in Sherrard Beaumont Burnaby, *Elements of the Jewish and Muhammadan Calendars* (London, 1901), ch. 9. [Verify: exact section/page references in Reingold-Dershowitz for the full cycle discussion]

[^108]: The key factorizations: 181,440 = 2⁶ × 3⁴ × 5 × 7 (since 181,440 = 7 × 25,920 = 7 × 24 × 1,080). The remainder per Metonic cycle is 115,315 <span dir="rtl">חֲלָקִים</span>. The smallest N such that N × 115,315 ≡ 0 (mod 181,440) is N = 181,440 / GCD(115,315, 181,440). Computing the GCD via the Euclidean algorithm yields N = 36,288. See Burnaby, *Elements of the Jewish and Muhammadan Calendars*, ch. 9, and Reingold-Dershowitz, *Calendrical Calculations*, §9.1, for the complete calculation. [Verify: confirm the prime factorization of 115,315 and the resulting GCD computation — the result of 36,288 Metonic cycles is widely cited but the intermediate arithmetic should be double-checked]

[^109]: In each 19-year Metonic cycle, there are 12 ordinary years and 7 leap years (years 3, 6, 8, 11, 14, 17, and 19 of the cycle). Over 36,288 Metonic cycles, this produces 36,288 × 12 = 435,456 ordinary years and 36,288 × 7 = 254,016 leap years. The distribution of specific keviyyot within these totals is tabulated in Reingold and Dershowitz, *Calendrical Calculations*, §9.1, and in Arthur Spier, *The Comprehensive Hebrew Calendar*, 3rd ed. (Jerusalem: Feldheim, 1986), appendix. [Verify: confirm that Spier's appendix contains the full keviyyah frequency distribution, and check Reingold-Dershowitz for the same data — the exact counts for each of the 14 keviyyot should be verified against these sources]

[^110]: The Hebrew calendar's implicit solar year, derived from the 19-year Metonic cycle (235 lunations = 19 years), is approximately 365.2468 days. The actual mean tropical year is approximately 365.2422 days. The difference of about 0.0046 days per year amounts to roughly 6 minutes and 40 seconds annually. Maimonides, *Hilkhot Kiddush HaChodesh* 9:1–3, discusses the tekufah of Rav Adda, which produces this implicit year length. See Reingold and Dershowitz, *Calendrical Calculations*, 4th ed. (2018), pp. 103–105.

[^111]: The rate of drift is approximately one day every 216–231 years, depending on the calculation method. See Ajdler, "The Future of the Jewish Calendar," *BDD* 25 (2011), for a detailed analysis of the drift rate and its long-term consequences.

[^112]: The year 6000 in the Hebrew calendar corresponds to 2239/2240 CE. By that point, the accumulated drift from the fourth century will be approximately seven to eight days. Passover will still fall within the astronomical spring in most years, but the margin of safety will have narrowed considerably. Several halakhic authorities have noted this looming problem; see note 108 below.

[^113]: The traditional synodic month (29 days, 12 hours, 793 <span dir="rtl">חֲלָקִים</span> = 29.530594 days) exceeds the modern IAU value (29.530589 days) by approximately 0.000005 days per lunation, or about 0.43 seconds. Over approximately 1,650 years since the calendar was fixed, this accumulates to roughly 100 minutes. See Part I, notes 11–12.

[^114]: For a survey of proposed reforms and their mathematical details, see Ajdler, "The Future of the Jewish Calendar," *BDD* 25 (2011). Reingold and Dershowitz, *Calendrical Calculations*, 4th ed. (2018), pp. 103–107, discuss the drift quantitatively without proposing specific reforms.

[^115]: The attribution to Hillel II and the approximate date of 358/359 CE is the traditional account. As noted in Part I (note 13), Stern, *Calendar and Community* (2001), argues the fixed calendar emerged more gradually. What matters for the reform question is the consensus that the calendar was established by an authority that no longer exists.

[^116]: The halakhic concept of <span dir="rtl">מִנְהָג</span> acquiring binding force is discussed in multiple contexts; its application to the calendar is explored in the responsa literature. The argument is that sixteen centuries of universal acceptance have given the calendar a quasi-legislative status independent of its original promulgation by the Sanhedrin. [Verify: specific responsa addressing whether the fixed calendar has the status of binding <span dir="rtl">מִנְהָג</span> — commonly discussed in the context of <span dir="rtl">יוֹם טוֹב שֵׁנִי</span> but less clearly documented for the calendar parameters themselves]

[^117]: The Netziv (Rabbi Naftali Zvi Yehuda Berlin, 1816–1893) raised the question of the calendar's long-term accuracy. Among the responses: some authorities held that the Messianic era would arrive before the drift became halakhically significant (i.e., before the year 6000), rendering the question moot; others acknowledged that the problem would eventually require a reconstituted Sanhedrin. [Verify: exact source in the Netziv's writings where this discussion appears — commonly cited but the precise reference varies in secondary literature]

[^118]: The analogy to coordination standards is not merely illustrative. The calendar functions as a consensus protocol in the technical sense: it produces agreement among distributed agents (Jewish communities worldwide) without requiring a central coordinator. The value of such a protocol lies primarily in its universality, not its precision. On the economics of coordination and standards, cf. the broader literature on network effects and switching costs, though the application to the Hebrew calendar is the present author's.

[^119]: Leviticus 23:4 — <span dir="rtl">אֲשֶׁר תִּקְרְאוּ אֹתָם</span>, "which you shall proclaim." The Talmud (Rosh Hashanah 25a) reads <span dir="rtl">אֹתָם</span> as <span dir="rtl">אַתֶּם</span> ("you"), emphasizing that the appointed times are whatever the court — "you" — declares them to be. See Part I for the full discussion.

[^120]: Maimonides, *Hilkhot Kiddush HaChodesh*, chapters 1–5. Chapter 1 establishes the court's obligation and authority. Chapter 2 addresses witness qualifications and testimony procedures. Chapter 3 covers the timing of court sessions and the sanctification declaration. Chapter 4 discusses intercalation — the criteria for adding a leap month. Chapter 5 treats the geographic reach of the court's decisions and the origin of the second festival day in the diaspora.

[^121]: Maimonides, *Hilkhot Kiddush HaChodesh*, chapters 11–19. Chapter 11 provides an overview and explains why these calculations are included. Chapters 12–13 treat the sun's position. Chapters 14–15 treat the moon's mean and true longitude. Chapter 16 addresses the moon's latitude. Chapter 17 covers the "arc of sighting" — the critical angular separation between moon and sun required for crescent visibility. Chapters 18–19 synthesize the preceding calculations into a decision procedure: given all the computed values, will the crescent be visible from Jerusalem on a particular evening? See Ajdler, "A Historical Outline of the Understanding of Maimonides' Astronomical Chapters," available at ajdler.com; also Bernard R. Goldstein, "Astronomy of Maimonides and Its Arabic Sources," in *Astronomical Society of the Pacific Conference Series* 409 (2009): 188–197.

[^122]: Maimonides, *Mishneh Torah*, introduction. He writes that his purpose is to compile all the laws "so that no person will need any other work at all regarding any law of the laws of Israel." The practical orientation of the *Mishneh Torah* is one of its defining features and distinguishes it from theoretical compendia. That Maimonides devoted nine chapters to currently inoperative visibility calculations, within a code designed for practical use, is significant evidence that he regarded those calculations as practically relevant for the future.

[^123]: Maimonides composed the *Mishneh Torah* in Fustat (Old Cairo) between approximately 1170 and 1180. His astronomical sources for the visibility chapters drew on Ptolemaic astronomy as transmitted through Arabic intermediaries, particularly al-Battani. See Goldstein (2009), note 112 above.

[^124]: The idea that the fixed calendar is a temporary measure pending the restoration of the Sanhedrin is not unique to Maimonides; it is implicit in any halakhic framework that ties calendrical authority to the court. But Maimonides makes it architecturally visible by structuring his code so that the observational chapters *follow* the fixed-calendar chapters, as if the algorithm is a waystation on the path back to observation.

