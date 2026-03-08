# DIVIDING DISPUTED PROPERTY IN RABBINIC LITERATURE

*Every algorithm for splitting what isn't enough, from the Mishnah to modern game theory*

A comprehensive treatment of claims problems across the full arc of rabbinic thought — Tannaitic through Acharonic — and the twentieth-century mathematics that revealed their hidden unity

# Table of Contents

- [Part I: The Garment on the Table](#part-i-the-garment-on-the-table)
  - [I.A. Two People, One Garment](#ia-two-people-one-garment)
  - [I.B. When Claims Are Unequal](#ib-when-claims-are-unequal)
  - [I.C. Concede and Divide](#ic-concede-and-divide)
  - [I.D. What a Claims Problem Is](#id-what-a-claims-problem-is)
- [Part II: The Three Widows](#part-ii-the-three-widows)
  - [II.A. The Puzzle That Stumped Everyone for Two Thousand Years](#iia-the-puzzle-that-stumped-everyone-for-two-thousand-years)
  - [II.B. Rabbi Natan and the Amoraic Discussion](#iib-rabbi-natan-and-the-amoraic-discussion)
  - [II.C. The Rishonim Struggle with the Table](#iic-the-rishonim-struggle-with-the-table)
- [Part III: Maimonides' Three Rules](#part-iii-maimonides-three-rules)
  - [III.A. Constrained Equal Awards](#iiia-constrained-equal-awards)
  - [III.B. Constrained Equal Losses](#iiib-constrained-equal-losses)
  - [III.C. The Proportional Rule](#iiic-the-proportional-rule)
  - [III.D. Ravad's Two Algorithms](#iiid-ravads-two-algorithms)
- [Part IV: What Makes a Rule Fair?](#part-iv-what-makes-a-rule-fair)
  - [IV.A. Basic Requirements](#iva-basic-requirements)
  - [IV.B. Equal Treatment of Equals](#ivb-equal-treatment-of-equals)
  - [IV.C. Resource Monotonicity](#ivc-resource-monotonicity)
  - [IV.D. Consistency](#ivd-consistency)
  - [IV.E. Duality](#ive-duality)
  - [IV.F. Claims Monotonicity and Population Monotonicity](#ivf-claims-monotonicity-and-population-monotonicity)
- [Part V: Beyond the Basic Three](#part-v-beyond-the-basic-three)
  - [V.A. Piniles' Rule](#va-piniles-rule)
  - [V.B. Run on the Bank](#vb-run-on-the-bank)
  - [V.C. The Shapley Value and Its Flaw](#vc-the-shapley-value-and-its-flaw)
  - [V.D. Ibn Ezra's Layered Cost-Sharing](#vd-ibn-ezras-layered-cost-sharing)
  - [V.E. Ketzos HaChoshen](#ve-ketzos-hachoshen)
  - [V.F. Shulchan Aruch: Codified Division Rules](#vf-shulchan-aruch-codified-division-rules)
  - [V.G. Hai Gaon's Methodology](#vg-hai-gaons-methodology)
- [Part VI: The Aumann-Maschler Breakthrough](#part-vi-the-aumann-maschler-breakthrough)
  - [VI.A. Two Economists Read the Talmud](#via-two-economists-read-the-talmud)
  - [VI.B. The Talmud Rule](#vib-the-talmud-rule)
  - [VI.C. The Recursive Formulation](#vic-the-recursive-formulation)
  - [VI.D. Three Regimes](#vid-three-regimes)
- [Part VII: The Game-Theoretic Foundation](#part-vii-the-game-theoretic-foundation)
  - [VII.A. Cooperative Games](#viia-cooperative-games)
  - [VII.B. The Nucleolus](#viib-the-nucleolus)
  - [VII.C. The Talmud Rule Is the Nucleolus](#viic-the-talmud-rule-is-the-nucleolus)
  - [VII.D. What the Mishnah Could Not Have Known](#viid-what-the-mishnah-could-not-have-known)
- [Part VIII: Other Division Problems in Rabbinic Law](#part-viii-other-division-problems-in-rabbinic-law)
  - [VIII.A. Inheritance: The Firstborn's Double Portion](#viiia-inheritance-the-firstborns-double-portion)
  - [VIII.B. Land Division and Heterogeneous Goods](#viiib-land-division-and-heterogeneous-goods)
  - [VIII.C. Partnership Dissolution](#viiic-partnership-dissolution)
  - [VIII.D. Damages with Insufficient Assets](#viiid-damages-with-insufficient-assets)
  - [VIII.E. Shuda D'Dayanei: When No Algorithm Applies](#viiie-shuda-ddayanei-when-no-algorithm-applies)
- [Part IX: The Modern Conversation](#part-ix-the-modern-conversation)
  - [IX.A. Thomson's Axiomatics](#ixa-thomsons-axiomatics)
  - [IX.B. Dagan's Alternative Characterizations](#ixb-dagans-alternative-characterizations)
  - [IX.C. Balinski's "What Is Just?"](#ixc-balinskis-what-is-just)
  - [IX.D. Connections Forward](#ixd-connections-forward)
- [Part X: Synthesis and Reflection](#part-x-synthesis-and-reflection)
  - [X.A. A Map of the Algorithms](#xa-a-map-of-the-algorithms)
  - [X.B. What the Tradition Teaches About Fairness](#xb-what-the-tradition-teaches-about-fairness)
  - [X.C. Open Questions](#xc-open-questions)
- [Glossary](#glossary)
- [Bibliography](#bibliography)

---

# Part I: THE GARMENT ON THE TABLE

## I.A. Two People, One Garment

Two people walk into a courtroom holding a single garment. Each one says: I found it. It is all mine.

The scene is from the opening Mishnah of Tractate Bava Metzia, and its ruling is the kind of thing that sounds obvious until you realize it isn't. The Mishnah says: each takes an oath that they own no less than half, and then they divide it equally.[^1]

A garment worth 200 zuz, two claimants each saying "all mine" — each receives 100. Half. The ruling feels like common sense: when two people make identical claims to the same thing and neither can prove their case, split down the middle. Shlomo HaMelekh knew this instinct. Parents settling disputes between children know it. The Mishnah is encoding something older than law.

The Gemara (Bava Metzia 2a) adds a procedural requirement: before the division, each party must swear an oath that they own no less than half. The oath serves two functions. It deters false claims — if you're lying about ownership, you must compound the wrong with a false oath. And it establishes a *minimum claim*: by swearing you own at least half, you formally state that your claim is not for a trivial amount. The oath transforms a vague assertion of ownership into a precise claim, suitable for algorithmic processing.

The equal-split ruling also conceals a choice. The Mishnah could have said: since neither claimant can prove ownership, the garment goes to neither — it remains in limbo, or it goes to the court, or it is destroyed. Some legal systems do handle contested property this way. The Mishnah's decision to split rather than withhold reflects a commitment to resolution: the goal is to divide the disputed resource among the claimants, not to punish them for having a dispute.

But the Mishnah isn't finished.

## I.B. When Claims Are Unequal

The second case is where things get interesting. One person claims the entire garment — "It is all mine." The other claims only half — <span dir="rtl">חציה שלי</span> — "Half of it is mine." The Mishnah rules: the one claiming all receives three-fourths; the one claiming half receives one-fourth.[^2]

Pause on those numbers. Three-fourths and one-fourth. The person claiming all gets *more* than the person claiming half — that seems fair enough — but the *ratio* is 3:1, not 2:1 (which would track the ratio of claims) and not infinity (which you might expect if "claiming all" simply trumped "claiming half"). The ratio is specific, and it demands explanation. Not two-thirds and one-third, which you might expect if the division tracked the relative size of the claims. Not half and half, which you might expect if the court simply threw up its hands. Three-fourths and one-fourth.

The Tosefta extends this further. When one person claims the whole and the other claims only a third, the first receives five-sixths and the second receives one-sixth.[^3] Again, the numbers are precise. Again, they follow a pattern that isn't immediately obvious.

Here is the garment problem laid out as a table, with the garment worth 200 zuz:

| Claim of A | Claim of B | Award to A | Award to B |
|:---:|:---:|:---:|:---:|
| 200 | 200 | 100 | 100 |
| 200 | 100 | 150 | 50 |
| 200 | 67 | 167 | 33 |

The numbers are doing something consistent. The question is what.

## I.C. Concede and Divide

Rashi, commenting on Bava Metzia 2a, explains the logic behind the Mishnah's ruling with an algorithm so clean it practically names itself.[^4]

The idea: look at what each party *concedes* belongs to the other. Whatever isn't in dispute, hand it over. Then split the contested remainder equally.

In the second case of the Mishnah — one claims all, one claims half — the logic unfolds like this. The person claiming half implicitly concedes the other half to his opponent. He is saying: half of this garment is yours, I have no argument with that. The person claiming all concedes nothing. So of the 200-zuz garment, 100 zuz are conceded by B to A, and 0 zuz are conceded by A to B. That leaves 100 zuz genuinely in dispute. Split that equally: 50 to each. Add the concessions back in. A receives 100 (conceded) + 50 (half the contested) = 150. B receives 0 (conceded) + 50 (half the contested) = 50.

Three-fourths and one-fourth, exactly as the Mishnah prescribes.

The algorithm generalizes cleanly to any pair of claims against any estate:

> **Algorithm: Concede and Divide (CnD)**
>
> INPUT: An estate E, two claims c₁ and c₂ where c₁ + c₂ ≥ E
>
> 1. Compute concessions:
>    - Concession of claimant 1 to claimant 2: max(E − c₁, 0)
>    - Concession of claimant 2 to claimant 1: max(E − c₂, 0)
> 2. Compute the contested portion:
>    - Contested = E − concession₁ − concession₂
> 3. Each claimant receives their concession plus half the contested portion:
>    - Award₁ = max(E − c₂, 0) + Contested / 2
>    - Award₂ = max(E − c₁, 0) + Contested / 2
>
> OUTPUT: (Award₁, Award₂)
>
> end.

Check it against the first case in the Mishnah: both claim 200, estate is 200. Concession of each to the other: max(200 − 200, 0) = 0. Contested: 200 − 0 − 0 = 200. Each gets 0 + 100 = 100. Equal split, as expected. The algorithm recovers the obvious case without needing a special rule for it.

Check it against the Tosefta case: A claims 200, B claims 67, estate is 200. Concession of A to B: max(200 − 200, 0) = 0. Concession of B to A: max(200 − 67, 0) = 133. Contested: 200 − 0 − 133 = 67. Each gets half of that: 33.5. So A receives 133 + 33.5 = 166.5, and B receives 0 + 33.5 = 33.5. Five-sixths and one-sixth (rounding to the nearest whole in the Tosefta's framing).[^5]

Concede and Divide is elegant, intuitive, and it perfectly explains every two-person case in the Mishnah and Tosefta. Its logic is the kind of thing a fair-minded person might arrive at independently — first give each side what isn't in dispute, then split the remainder. Rashi's genius was to see that the Mishnah's specific numbers all flow from this single principle.

The algorithm has a revealing structure when you trace it across different estate values. Take two claimants with claims of 100 and 200, and vary the estate from 0 to 300:

| Estate | Concession of A (claim 100) | Concession of B (claim 200) | Contested | Award A | Award B |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 0 | 0 | 0 |
| 50 | 0 | 0 | 50 | 25 | 25 |
| 100 | 0 | 0 | 100 | 50 | 50 |
| 150 | 50 | 0 | 100 | 50 | 100 |
| 200 | 100 | 0 | 100 | 50 | 150 |
| 250 | 150 | 50 | 50 | 75 | 175 |
| 300 | 200 | 100 | 0 | 100 | 200 |

Three distinct regimes emerge. When the estate is smaller than both claims (E ≤ 100), neither side concedes anything — the entire estate is contested and split equally. When the estate exceeds the smaller claim but not the larger one (100 < E ≤ 200), the smaller claimant concedes the excess while the larger claimant concedes nothing — the contested portion stays fixed at the smaller claim, and additional estate flows entirely to the larger claimant. When the estate exceeds both claims (E > 200), both claimants concede — the contested portion shrinks, and additional estate again flows equally.

The first regime is Constrained Equal Awards. The third regime is Constrained Equal Losses. The middle regime is a linear interpolation connecting the two. CnD doesn't just combine these rules — it *is* these rules, stitched together at the claim values. This observation, due to Aumann and Maschler, will turn out to be the key to the entire theory.

One more edge case worth noting: what happens when the estate exceeds the sum of claims? If the estate is 350 but the claims total only 300, the problem is no longer a genuine claims dispute — there's enough for everyone and 50 left over. CnD assumes the estate is at most the sum of claims; the surplus isn't addressed by the algorithm. In practice, rabbinic law handles surplus through inheritance rules or return to the original owner's estate.

There's also the question of *when the estate equals the sum of claims exactly*. CnD gives each claimant their full claim: concessions from each side to the other exactly cover the other's claim, the contested portion is zero, and everyone goes home satisfied. The algorithm handles this gracefully — it doesn't need a special rule for the case where there's exactly enough. The general formula produces the right answer at both extremes (estate = 0, estate = sum of claims) and everywhere in between.

But Concede and Divide, as stated, handles exactly two claimants. What happens when there are three?

A natural first attempt: compute what the other claimants collectively concede to each claimant, then split the contested remainder equally among all. For claims (100, 200, 300) and E = 200: the concession to Claimant 1 from the others is max(200 − 500, 0) = 0. Similarly, concessions to Claimants 2 and 3 are both 0. The entire estate is contested and split three ways: (66⅔, 66⅔, 66⅔). This is just equal division — it ignores the differences between claims. Worse, for larger estates or more extreme claim distributions, this naive extension can produce nonsensical results, violating order-preservation (a claimant with a larger claim receiving a smaller award).

The failure of the naive extension is precisely why the Ketuboth problem is hard. CnD is a two-person algorithm, and scaling it to three or more people requires something more subtle than applying it to everyone at once. That subtlety is the subject of the next eight parts.

## I.D. What a Claims Problem Is

Before pushing further, it helps to name what we're looking at. The garment cases are instances of a general structure that appears across rabbinic literature and, independently, across modern economics.

A *claims problem* consists of three things: an estate (or resource) of value E, a list of claims c₁, c₂, ..., cₙ against that estate, and the condition that the total claims exceed the estate — there isn't enough to satisfy everyone.[^6]

A *division rule* (or *allocation rule*) is any systematic method for computing an awards vector: how much each claimant receives. A valid awards vector must satisfy two constraints that are so natural they barely need stating. First, no one receives a negative amount or more than their claim. Second, the awards sum to the full estate — nothing is left on the table and nothing is conjured from thin air.[^7]

The garment worth 200 claimed by two people asserting "all mine" is the claims problem (E = 200, claims = [200, 200]). Concede and Divide is a division rule. Its output for this problem — (100, 100) — is a valid awards vector.

These names don't add new ideas. They organize the ones already on the table.

A few observations about the structure. First, the condition that total claims exceed the estate is what makes the problem nontrivial. If there's enough to pay everyone in full, the "algorithm" is trivial: give each person what they're owed. The interesting case — the one that generates two thousand years of analysis — is the case of insufficiency.

Second, the definition is silent about *why* the claims exist. The garment claimants assert ownership. The Ketuboth creditors hold ketubot. The reneging bidders in Erakhin created obligations through their bids. The algorithm doesn't care. A claims problem is defined by its numbers, not its narrative. This abstraction is what makes the same mathematical tools applicable across tractates, across legal categories, across centuries.

Third, a division rule is deterministic: given the same inputs, it always produces the same output. There's no randomness, no discretion, no case-by-case judgment. This is what makes it an *algorithm* rather than a *guideline*. When the halakha reserves room for judicial discretion — <span dir="rtl">שודא דדייני</span> — it is explicitly stepping outside the algorithmic framework and acknowledging that some problems resist deterministic solutions.

These names prepare us for the central puzzle of this manuscript: a claims problem with three claimants, three different estate sizes, and a table of numbers that no one could explain for two thousand years.

---

# Part II: THE THREE WIDOWS

## II.A. The Puzzle That Stumped Everyone for Two Thousand Years

The contested garment, for all its elegance, is a two-person problem. Two claimants, one garment, a clean algorithm. But the world has more than two people, and estates have more than two creditors. What happens when the algorithm must scale?

The Mishnah in Ketuboth provides the test case. It is the problem that defined the field, and it remained unsolved longer than almost any problem in the history of mathematics.

A man dies leaving three creditors.[^8] The first is owed 100, the second is owed 200, the third is owed 300. The total debt is 600. The Mishnah in Ketuboth 10:4, as discussed in the Babylonian Talmud Ketuboth 93a, considers three scenarios depending on the size of the estate.[^9]

The results are given in a table:

| Estate | Creditor 1 (claim 100) | Creditor 2 (claim 200) | Creditor 3 (claim 300) |
|:---:|:---:|:---:|:---:|
| 100 | 33⅓ | 33⅓ | 33⅓ |
| 200 | 50 | 75 | 75 |
| 300 | 50 | 100 | 150 |

The first row looks like equal division. The third row looks like proportional division. But the middle row is strange — and none of the obvious rules can produce all three rows.

This needs to be seen concretely.

**Testing Equal Division.** Equal division says: split the estate into equal shares regardless of claims. For E = 100, that gives (33⅓, 33⅓, 33⅓). Correct. For E = 200, that gives (66⅔, 66⅔, 66⅔). Wrong — the Mishnah says (50, 75, 75). Equal division fails at the second row.[^10]

**Testing Proportional Division.** Proportional division says: divide in proportion to claims. The claims ratio is 1:2:3. For E = 100, that gives (16⅔, 33⅓, 50). Wrong — the Mishnah says equal shares. For E = 300, proportional gives (50, 100, 150). Correct. But it fails at the first row.[^11]

**Testing Constrained Equal Awards.** This rule (which we'll develop fully in Part III) gives everyone the same amount, capped at their claim. For E = 100, the equal share is 33⅓, and all claims exceed that, so everyone gets 33⅓. Correct. For E = 200, the equal share is 66⅔, but Creditor 1 claims only 100, so she gets 66⅔, and the other two split the remaining 133⅓ equally at 66⅔ each. That gives (66⅔, 66⅔, 66⅔) — still wrong. Actually, let's be more careful: equal share would be 66⅔, Creditor 1's claim of 100 exceeds 66⅔, so all three get 66⅔. That's (66⅔, 66⅔, 66⅔). Wrong.[^12]

**Testing Constrained Equal Losses.** This rule (also developed in Part III) says everyone bears equal losses from their claims. Total claims are 600, estate is 200, total loss is 400. Equal loss is 400/3 = 133⅓. Awards: Creditor 1 gets 100 − 133⅓ = negative, which isn't allowed. So Creditor 1 gets 0, and the remaining 200 is split between the other two with equal losses. Their combined claims are 500, loss is 300, equal loss is 150 each. Awards: 200 − 150 = 50, 300 − 150 = 150. That gives (0, 50, 150). Wrong.[^13]

No single obvious rule produces all three rows.

Robert Aumann and Michael Maschler put it precisely in their landmark 1985 paper: "The figures for E = 200 look mysterious; but whatever they may mean, they do not fit any obvious extension of either equal *or* proportional division. A common rationale for all three cases is not apparent."[^14]

Over two millennia, this Mishnah spawned a vast literature. Many authorities disagreed with it outright. Others attributed the numbers to special circumstances not made explicit in the text. Some attempted direct rationalizations of the figures, mostly with limited success. One modern scholar, exasperated by his inability to make sense of the passage, suggested errors in transcription.[^15] The Rif — Rabbi Isaac Alfasi, the great eleventh-century codifier — wrote that he and his predecessors had discussed this Mishnah and its Gemara at length "and were unable to make sense of it."[^16]

The passage is, in brief, notoriously difficult.

## II.B. Rabbi Natan and the Amoraic Discussion

The Gemara on Ketuboth 93a attributes the Mishnah to Rabbi Natan, and the discussion that follows provides a crucial clue — one that went largely unappreciated until the twentieth century.[^17]

The Gemara examines the middle case, E = 200, by breaking it into pairs. Creditors 1 and 2 between them receive 50 + 75 = 125. Creditors 1 and 3 receive 50 + 75 = 125. Creditors 2 and 3 receive 75 + 75 = 150. The Gemara invokes the contested garment principle — Concede and Divide — to justify these pairwise totals.[^18]

Take Creditors 1 and 2, whose combined award is 125. Their claims are 100 and 200. Apply CnD to (E = 125, claims = [100, 200]). Concession of Creditor 1 to Creditor 2: max(125 − 100, 0) = 25. Concession of Creditor 2 to Creditor 1: max(125 − 200, 0) = 0. Contested: 125 − 25 − 0 = 100. Half each: 50. Awards: Creditor 1 gets 0 + 50 = 50. Creditor 2 gets 25 + 50 = 75. These match the Mishnah exactly.[^19]

Take Creditors 1 and 3, whose combined award is 125. Claims: 100 and 300. Concession of 1 to 3: max(125 − 100, 0) = 25. Concession of 3 to 1: max(125 − 300, 0) = 0. Contested: 100. Awards: 50 and 75. Again, Creditor 1 gets 50, Creditor 3 gets 75 — correct.

Take Creditors 2 and 3, whose combined award is 150. Claims: 200 and 300. Concession of 2 to 3: max(150 − 200, 0) = 0. Concession of 3 to 2: max(150 − 300, 0) = 0. Contested: 150. Awards: 75 and 75. Correct.

The Gemara is saying: whatever rule generated these numbers, it has the property that any pair of creditors, if they took their combined award and divided it between themselves using Concede and Divide, would arrive at exactly the shares the rule already assigned them. The three-person solution is *consistent* with the two-person rule.

This observation — that the three-person Ketuboth table is CnD-consistent — is the thread that two millennia of scholarship couldn't quite follow to its conclusion. The Jerusalem Talmud preserves a related idea in the name of Samuel: the Mishnah takes it that the creditors "empower each other" — specifically, that the third creditor empowers the second to deal with the first.[^20] Samuel's language hints at a coalitional structure, as if the creditors form temporary alliances to press their claims. The reasoning is remarkably close to the coalitional procedure that Aumann and Maschler would formalize in 1985.

The CnD-consistency check extends to the other two rows as well, though the Gemara focuses on E = 200.

For **E = 100**, awards are (33⅓, 33⅓, 33⅓):
- Pair (1,2): combined 66⅔. CnD(66⅔, [100, 200]): neither concedes anything (both claims exceed the estate). Contested: 66⅔. Split: 33⅓ each. ✓
- Pair (1,3): combined 66⅔. CnD(66⅔, [100, 300]): same logic. Split: 33⅓ each. ✓
- Pair (2,3): combined 66⅔. CnD(66⅔, [200, 300]): same. Split: 33⅓ each. ✓

For **E = 300**, awards are (50, 100, 150):
- Pair (1,2): combined 150. CnD(150, [100, 200]): Creditor 1 concedes max(150 − 100, 0) = 50 to Creditor 2. Creditor 2 concedes 0. Contested: 100. Split: 50 each. Awards: (50, 100). ✓
- Pair (1,3): combined 200. CnD(200, [100, 300]): Creditor 1 concedes 100. Creditor 3 concedes 0. Contested: 100. Split: 50. Awards: (50, 150). ✓
- Pair (2,3): combined 250. CnD(250, [200, 300]): Creditor 2 concedes 50. Creditor 3 concedes 0. Contested: 200. Split: 100. Awards: (100, 150). ✓

Every pair in every row checks out. The Mishnah's numbers are CnD-consistent throughout.

But at the time, neither the Babylonian nor the Jerusalem Talmud could articulate a general rule that extended beyond these specific numbers. They showed that the numbers were consistent. They could not show why those numbers, and no others, had to be the answer.

## II.C. The Rishonim Struggle with the Table

The medieval commentators — the Rishonim — engaged the Ketuboth table with the full weight of their analytical brilliance, and the difficulty of the passage is reflected in the diversity of their approaches.

**Rashi** on Ketuboth 93a follows the Gemara's pairwise logic closely. He explains each row by showing how the numbers can be decomposed into CnD-consistent pairs. His commentary clarifies the mechanism but does not propose a general algorithm — he describes *what* the numbers satisfy without explaining *how* to generate them for an arbitrary claims problem.[^21]

**Tosafot** on Ketuboth 93a raise a fundamental objection that goes beyond textual interpretation to the logical structure of the problem. The contested garment in Bava Metzia involves *mutually exclusive claims* — both people cannot own the same garment, so at least one is wrong or lying. The bankruptcy in Ketuboth involves *valid but unsatisfiable claims* — all three debts are real, all three ketubot are binding, but the estate simply doesn't have enough. Tosafot question whether the CnD principle, designed for the first situation, applies to the second.

The distinction matters because it affects the moral basis of the division. In the garment case, the equal split of the contested portion rests on genuine uncertainty about ownership — we don't know who is telling the truth, so we split the doubt. In the bankruptcy case, there's no doubt about the debts; the only question is allocation. Why should the garment rule govern bankruptcy?

Aumann and Maschler address this objection directly. While the *legal contexts* differ, the *mathematical structure* of CnD — concede what you can't claim, split the remainder — is not logically dependent on uncertainty about ownership. It works just as well as a principle of fair allocation: each creditor "concedes" the portion of the estate that exceeds her claim (she can't take what she doesn't claim), and the genuinely contested portion is shared equally. The shift from "uncertainty about truth" to "competing valid claims" changes the legal reasoning but not the algorithm.[^22]

Tosafot also explore alternative readings of the Gemara's discussion and consider whether Rabbi Natan's rule might apply only in limited circumstances — perhaps only when the estate is exactly 200, or only when the creditors hold ketubot of specific denominations.

**The Rif** (Rabbi Isaac Alfasi, 1013–1103) includes this Mishnah in his halakhic compendium but notes, with characteristic honesty, that the passage remains poorly understood. His admission that "we were unable to make sense of it" became one of the most-cited confessions of difficulty in rabbinic literature.[^23] The **Ravad** (Rabbi Abraham ben David, 1125–1198), in his glosses on the Rif, proposes his own interpretation — we will examine his distinctive algorithms in Part III.

**The Ran** (Rabbenu Nissim of Gerona, 1320–1376) offers an alternative explanation that attempts to reconcile the numbers through a priority-based reading of the creditors' positions. His approach has the virtue of internal consistency but does not generalize to arbitrary claims problems.[^24]

**The Rosh** (Rabbenu Asher ben Yechiel, 1250–1327) focuses on the practical implications: which rule should courts actually apply? His ruling, which influenced the Shulchan Aruch's later codification, effectively sidesteps the theoretical puzzle by adopting specific division procedures for different circumstances rather than seeking a unified algorithm.[^25]

**Ramban** (Nachmanides, 1194–1270) engages with the passage in the context of broader creditor-law principles, exploring how the Ketuboth table relates to established rules about the ordering of creditor claims and the circumstances under which proportional division applies.[^26]

What emerges from the Rishonim is not a solution but a map of the difficulty. These were not scholars easily stumped. Their collective inability to produce a single algorithm that generates all three rows from first principles is itself evidence: the problem is genuinely hard. The Mishnah's numbers encode something that required tools — mathematical tools — that did not yet exist.

The Rishonim established, through the depth of their struggle, that the Ketuboth table was not a scribal error, not a special case dressed up as a general rule, and not reducible to any simple principle then available. Something real was hidden in those numbers. Finding it would take another eight hundred years.

---

# Part III: MAIMONIDES' THREE RULES

The Rishonim could not solve the Ketuboth puzzle. But in their attempts — and in their treatments of other division problems scattered across the Talmud — they developed a toolkit of algorithms that would later prove to be the essential components of the solution.

Three rules became dominant, each with a clear intuition and a specific rabbinic pedigree. Each rule captures a different moral instinct about fairness. Understanding them individually is necessary before seeing how the Talmud Rule unifies them — and understanding *why* they fail individually is necessary for appreciating *why* the unification required a genuinely new idea (the half-claim threshold).

A note on terminology: "Constrained Equal Awards" and "Constrained Equal Losses" are modern names given by Thomson and the economics literature. Maimonides did not use these terms. He described the rules through specific examples and general principles, as was the convention of halakhic codification. The formal names are anachronistic but useful.

## III.A. Constrained Equal Awards

Maimonides, in Hilkhot Malveh v'Loveh (Laws of Lending and Borrowing) 20:4, codifies a rule for dividing an estate among creditors: give each creditor an equal share, but never more than her claim.[^27]

The intuition is direct. Fairness, in this view, means treating each *dollar of debt* as equally worthy of payment. If the estate is small relative to the claims, everyone gets the same amount. As the estate grows, smaller claimants hit their ceiling first — they're fully satisfied — and additional funds flow to the remaining claimants in equal shares.

Here is the algorithm:

> **Algorithm: Constrained Equal Awards (CEA)**
>
> INPUT: An estate E, claims c₁ ≤ c₂ ≤ ... ≤ cₙ
>
> 1. Set equal share = E / n.
> 2. For each claimant i:
>    - If cᵢ ≤ equal share, award cᵢ (fully satisfied).
>    - Remove satisfied claimants. Subtract their awards from E.
>    - Recompute equal share among remaining claimants.
> 3. Repeat until all remaining claimants receive the equal share.
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Worked example.** Estate E = 100, claims (60, 40, 30). Start with equal share = 100/3 ≈ 33.33. Claimant 3's claim is 30, which is less than 33.33, so Claimant 3 is fully satisfied at 30. Remaining estate: 70. Remaining claimants: 2. New equal share: 35. Both remaining claims (60 and 40) exceed 35. Awards: (35, 35, 30).[^28]

**Testing against the Ketuboth table.** Claims (100, 200, 300).

For E = 100: Equal share = 33⅓. All claims exceed 33⅓. Awards: (33⅓, 33⅓, 33⅓). **Matches row 1.**

For E = 200: Equal share = 66⅔. All claims exceed 66⅔. Awards: (66⅔, 66⅔, 66⅔). **Fails row 2.** The Mishnah says (50, 75, 75).

For E = 300: Equal share = 100. Creditor 1's claim is exactly 100, satisfied. Remaining: 200 between two claimants. Equal share: 100. Awards: (100, 100, 100). **Fails row 3.** The Mishnah says (50, 100, 150).

CEA matches the Ketuboth table only when the estate equals the smallest claim. It treats creditors too symmetrically for larger estates, ignoring the differences in what they're owed.

There is another way to visualize CEA: imagine filling up identical cups, each with a different maximum capacity (the claim). Pour water (the estate) simultaneously into all cups. The water level rises equally in all cups until the smallest cup overflows — that claimant is fully satisfied. Then the water continues rising in the remaining cups, and so on.

This "water-filling" metaphor makes CEA's appeal clear. Every additional dollar of estate is shared equally among all active claimants. No one gets a second helping until everyone has had a first. It is the algorithm of a careful host at a dinner table: serve everyone a small portion first, then go around again.

**Second worked example.** Estate E = 250, claims (100, 200, 300). Equal share = 83⅓. Creditor 1's claim (100) exceeds 83⅓, so in the first pass, all three get 83⅓. But wait — Creditor 1's claim is 100, which is less than 83⅓? No: 100 > 83⅓. So all three get 83⅓. Awards: (83⅓, 83⅓, 83⅓). But this totals 250 and respects all claim bounds. ✓

**Third worked example.** Estate E = 400, claims (100, 200, 300). Equal share = 133⅓. Creditor 1's claim is 100 < 133⅓, so she is fully satisfied at 100. Remaining: 300 between two claimants. Equal share: 150. Creditor 2's claim is 200 ≥ 150, Creditor 3's claim is 300 ≥ 150. Awards: (100, 150, 150).

## III.B. Constrained Equal Losses

Where CEA equalizes what people *receive*, Constrained Equal Losses equalizes what they *lose*. Maimonides describes this approach in a different context — Hilkhot Erkhei HaKdesh (Laws of Appraisal) 8:4 — through a scenario involving bidders at an auction who renege on their bids.[^29]

The Talmud (Erakhin 27b) considers an auction where the high bidder reneges and the object is sold to the next-highest bidder. The difference in price is a loss that the reneging bidder must cover. Maimonides extends this: if *all* bidders renege, the total loss — the highest bid, since that's what the seller should have received — must be shared among them. His ruling: divide the loss equally, capped so that no one pays more than their bid.

The Ravad notes that this is the dual of CEA — instead of equalizing gains, it equalizes losses.[^30] The algorithm:

> **Algorithm: Constrained Equal Losses (CEL)**
>
> INPUT: An estate E, claims c₁ ≤ c₂ ≤ ... ≤ cₙ
>
> 1. Compute total loss = (c₁ + c₂ + ... + cₙ) − E.
> 2. Set equal loss = total loss / n.
> 3. For each claimant i:
>    - If cᵢ ≤ equal loss, set award to 0 (loses everything).
>    - Remove wiped-out claimants. Subtract their claims from total loss.
>    - Recompute equal loss among remaining claimants.
> 4. Repeat until all remaining claimants can absorb the equal loss.
> 5. Each remaining claimant i receives cᵢ − equal loss.
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Worked example.** Estate E = 100, claims (60, 40, 30). Total claims = 130, total loss = 30. Equal loss = 10. All claims exceed 10. Awards: (60 − 10, 40 − 10, 30 − 10) = (50, 30, 20).[^31]

**Testing against the Ketuboth table.** Claims (100, 200, 300), total claims = 600.

For E = 100: Total loss = 500. Equal loss = 166⅔. Creditor 1's claim (100) is less than 166⅔, so she gets 0. Remaining loss: 400. Two claimants. Equal loss: 200. Creditor 2's claim (200) equals 200, so she gets 0. Remaining: Creditor 3 alone gets 100. Awards: (0, 0, 100). **Fails row 1.**

For E = 300: Total loss = 300. Equal loss = 100. Awards: (0, 100, 200). **Fails row 3.** The Mishnah says (50, 100, 150).

CEL fails badly for small estates — it wipes out smaller creditors entirely. It works better when the estate is large relative to the claims, treating the division as primarily about sharing losses rather than distributing gains.

The asymmetry is clear: CEA starts from zero and builds up; CEL starts from full claims and trims down. CEA is the algorithm of distribution — pouring water into cups. CEL is the algorithm of sacrifice — cutting equally from each person's allotment. For small estates, distribution thinking is natural ("how much does each person get?"). For large estates, sacrifice thinking is natural ("how much does each person lose?").

**Second worked example.** Estate E = 400, claims (100, 200, 300). Total claims = 600, total loss = 200. Equal loss = 66⅔. All claims exceed 66⅔. Awards: (33⅓, 133⅓, 233⅓). Every claimant loses the same amount — 66⅔ — from their full claim.

**Third worked example.** Estate E = 500, claims (100, 200, 300). Total loss = 100. Equal loss = 33⅓. All claims exceed 33⅓. Awards: (66⅔, 166⅔, 266⅔). Very close to full satisfaction, with each losing a modest equal share.

This asymmetry between CEA (good for small estates) and CEL (good for large estates) will turn out to be the key to the Talmud Rule. The Talmud Rule's central insight is that both intuitions are correct — in their respective domains — and the half-claim is the natural dividing line between them.

## III.C. The Proportional Rule

The proportional rule predates rabbinic literature. Aristotle articulated it in Book V, Chapter 3 of the *Nicomachean Ethics*: "The just is the proportional."[^32] Each claimant receives a share of the estate proportional to their claim. Modern secular bankruptcy law typically follows this principle — each dollar of debt is treated identically, regardless of which creditor holds it.

> **Algorithm: Proportional Rule**
>
> INPUT: An estate E, claims c₁, c₂, ..., cₙ
>
> 1. Compute total claims D = c₁ + c₂ + ... + cₙ.
> 2. For each claimant i: Award xᵢ = (cᵢ / D) × E
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Worked example.** Estate E = 100, claims (60, 40, 30). Total claims = 130. Proportions: 60/130, 40/130, 30/130. Awards: (46.15, 30.77, 23.08).[^33]

**Testing against the Ketuboth table.** Claims (100, 200, 300), total claims = 600, proportions 1:2:3.

For E = 100: Awards = (16⅔, 33⅓, 50). **Fails row 1.** The Mishnah says equal shares.

For E = 200: Awards = (33⅓, 66⅔, 100). **Fails row 2.** The Mishnah says (50, 75, 75).

For E = 300: Awards = (50, 100, 150). **Matches row 3.**

The proportional rule matches only the largest estate. Its failure at smaller estates is instructive: when the estate is very small relative to claims, proportional division seems unfair — it gives the smallest creditor a pittance while the largest creditor receives a substantial payment, even though neither is getting much of what they're owed. The Mishnah's instinct to equalize at E = 100 reflects a different moral intuition: when everyone is losing badly, share the pain equally.

The proportional rule has a distinctive graphical signature. Plot each creditor's award as a function of the estate: you get straight lines from the origin, each with a slope equal to the creditor's fraction of total claims. Creditor 3's line has slope 300/600 = 1/2; Creditor 1's has slope 100/600 = 1/6. The lines never curve, never kink, never interact. Each creditor's award tracks the estate linearly, independent of the others.

Compare this with CEA, whose graph has kinks where creditors hit their ceilings, or CEL, whose graph has kinks where creditors hit zero. The proportional rule's smoothness is mathematically elegant but morally tone-deaf to the creditors' differing situations. The creditor who claims 100 and receives 16⅔ from an estate of 100 has been paid one-sixth of her claim. The creditor who claims 300 and receives 50 has also been paid one-sixth. Equal *rates* of satisfaction, but dramatically different *amounts* — and the small creditor may argue that when everyone is losing, the absolute amount matters more than the rate.

This tension between rate-based and amount-based fairness is fundamental. The proportional rule says: every dollar of debt is equal. CEA says: every creditor is equal. CEL says: every dollar of shortfall is equal. Different commitments, different algorithms, different numbers.

Modern secular bankruptcy law has overwhelmingly chosen the proportional rule. When a company goes bankrupt, unsecured creditors receive *pro rata* distributions — each gets the same fraction of their claim. The moral logic is clear and the administration is simple. But the Mishnah rejected proportionality for the Ketuboth case (it fails rows 1 and 2). The Mishnah's numbers suggest a different, more nuanced view of fairness — one that treats the size of the estate as a morally relevant factor, not just the claims.

Here is a summary of how each rule performs against the three rows:

| Estate | Mishnah | CEA | CEL | Proportional |
|:---:|:---:|:---:|:---:|:---:|
| 100 | (33⅓, 33⅓, 33⅓) | (33⅓, 33⅓, 33⅓) ✓ | (0, 0, 100) ✗ | (16⅔, 33⅓, 50) ✗ |
| 200 | (50, 75, 75) | (66⅔, 66⅔, 66⅔) ✗ | (0, 50, 150) ✗ | (33⅓, 66⅔, 100) ✗ |
| 300 | (50, 100, 150) | (100, 100, 100) ✗ | (0, 100, 200) ✗ | (50, 100, 150) ✓ |

Three rules, three rows, and no rule matches more than one. The Mishnah is doing something none of these algorithms can capture alone.

## III.D. Ravad's Two Algorithms

The Ravad — Rabbi Abraham ben David of Posquières — was Maimonides' most formidable critic, and on the question of estate division he proposed not one but two distinct algorithms, each in a different context.

### Ravad's Layered Equal Division

In his glosses on the Rif's treatment of Ketuboth 51a, the Ravad offers a layered approach.[^34] The idea: the estate is divided in stages corresponding to the claim levels. The first layer, up to the smallest claim, is divided equally among all claimants. The second layer, from the smallest claim to the next, is divided equally among the remaining claimants. And so on.

> **Algorithm: Ravad's Layered Equal Division**
>
> INPUT: An estate E, claims c₁ ≤ c₂ ≤ ... ≤ cₙ
>
> 1. Set remaining = E. Set awards = (0, 0, ..., 0).
> 2. For each layer k from 1 to n:
>    - The layer's width = cₖ − c_{k−1} (with c₀ = 0)
>    - Active claimants in this layer = n − k + 1
>    - Layer capacity = width × (n − k + 1)
>    - If remaining ≥ layer capacity:
>      - Each active claimant receives width
>      - remaining = remaining − layer capacity
>    - Else:
>      - Each active claimant receives remaining / (n − k + 1)
>      - remaining = 0
>      - STOP
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Worked example.** Claims (100, 200, 300), E = 200.

Layer 1 (0 to 100): width = 100, 3 active claimants, capacity = 300. Remaining (200) < 300. Each gets 200/3 = 66⅔. Awards: (66⅔, 66⅔, 66⅔). Stop.

That gives (66⅔, 66⅔, 66⅔) for E = 200 — the same as CEA, and wrong.

For E = 300: Layer 1 capacity = 300. Remaining = 300 ≥ 300. Each of the 3 claimants gets 100. Remaining = 0. Awards: (100, 100, 100). Also wrong.

Ravad's layered rule coincides with CEA. Aumann and Maschler note this equivalence: the layered construction is simply another way of computing constrained equal awards.[^35] Its interest lies not in producing different numbers but in offering a different *intuition* — the idea that all creditors have a claim on the first dollars of the estate (up to the smallest claim), and only the larger creditors have a claim on subsequent dollars. This intuition of layered entitlement will resurface in Ibn Ezra's approach and, ultimately, in the Talmud Rule itself.

### Ravad's Bidding Rule

In his glosses on Maimonides' Laws of Lending and Borrowing 20:4, the Ravad proposes a second algorithm, this one for the auction-renege scenario.[^36] Where Maimonides says all bidders share the loss equally (CEL on the bids), the Ravad says the loss should be divided in layers matching the incremental structure of the bids.

Suppose bidders bid 40, 50, and 60 on an object. All renege. The seller's loss is 60 (the highest bid). The Ravad divides this loss as follows: the first 40 is shared equally among all 3 bidders (each pays 13⅓). The next 10 (from 40 to 50) is shared by bidders 2 and 3 (each pays 5). The final 10 (from 50 to 60) falls on bidder 3 alone.

> **Algorithm: Ravad's Bidding Rule**
>
> INPUT: Total loss L, bids b₁ ≤ b₂ ≤ ... ≤ bₙ
>
> 1. Set remaining = L. Set losses = (0, 0, ..., 0).
> 2. Divide L into increments: b₁, b₂ − b₁, b₃ − b₂, ..., bₙ − b_{n−1}
> 3. For each increment k:
>    - Active bidders = n − k + 1
>    - If remaining ≥ increment:
>      - Each active bidder's loss increases by increment / (n − k + 1)
>      - remaining = remaining − increment
>    - Else:
>      - Each active bidder's loss increases by remaining / (n − k + 1)
>      - STOP
>
> OUTPUT: Loss vector (loss₁, loss₂, ..., lossₙ)
>
> end.

**Worked example.** Bids (40, 50, 60), total loss = 60.

Increment 1 (0 to 40): 40 / 3 = 13⅓ each. Increment 2 (40 to 50): 10 / 2 = 5 each (bidders 2 and 3). Increment 3 (50 to 60): 10 / 1 = 10 (bidder 3 only). Losses: (13⅓, 18⅓, 28⅓). These sum to 60. ✓[^37]

**Second worked example.** Bids (100, 200, 300), total loss = 300 (the full highest bid, since the seller expected 300 from the winning bidder and received nothing).

Increment 1 (0 to 100): 100 / 3 = 33⅓ each. Increment 2 (100 to 200): 100 / 2 = 50 each (bidders 2 and 3). Increment 3 (200 to 300): 100 / 1 = 100 (bidder 3 only). Losses: (33⅓, 83⅓, 183⅓). Sum = 300. ✓

Now convert losses to "awards" (i.e., how much of each bidder's liability is *not* imposed): Awards = claims − losses = (100 − 33⅓, 200 − 83⅓, 300 − 183⅓) = (66⅔, 116⅔, 116⅔).

Compare with the Ravad's layered equal division applied as a *gains* rule to the same numbers — E = 300, claims (100, 200, 300):

Layer 1 (0 to 100): 100 × 3 = 300. Remaining (300) = 300. Each gets 100. Done. Awards: (100, 100, 100).

The two rules produce different numbers on the same inputs — (66⅔, 116⅔, 116⅔) for the bidding rule versus (100, 100, 100) for the layered gains rule. This is because they're *duals*, not copies. The bidding rule applied to bids (100, 200, 300) with total loss 300 gives the same awards as CEL applied to an estate of 300 with claims (100, 200, 300) — except that CEL distributes losses equally across all claimants, while the Ravad distributes losses in layers.

The precision here is the Ravad's contribution. He saw that the structure of the bids — their *incremental* differences — should determine the loss allocation, not just their absolute sizes. The first 100 of the seller's loss was created equally by all three bidders (all bid at least 100). The next 100 was created by only two bidders (only bidders 2 and 3 bid above 100). The final 100 was created by bidder 3 alone. Assigning losses based on who created them is a causal analysis of the shortfall — a surprisingly modern approach to cost allocation.

This is precisely the dual of the layered equal division rule — one divides gains in layers, the other divides losses in layers. Together, the two Ravad rules form a matched pair: CEA for gains, its structural dual for losses. The duality between them will become a central theme. Aumann and Maschler note the remarkable fact that these dual rules appear in the *same legal tradition*, attributed to the *same authorities* — a sign that the Rishonim understood duality intuitively, even without the formal concept.

---

# Part IV: WHAT MAKES A RULE FAIR?

We now have four distinct algorithms — CEA, CEL, the Proportional Rule, and Concede and Divide — plus Ravad's two layered variants. They produce different numbers for the same problem. On what grounds might we prefer one to another?

The approach developed by modern economists, particularly William Thomson, is axiomatic: identify properties that a "fair" rule should satisfy, then ask which rules satisfy which properties.[^38] Each property captures a specific moral or structural intuition about what fairness requires. None of them, by itself, determines a unique rule — but the combinations are powerful.

The properties are abstract, so we'll ground each one in a concrete scenario before stating it formally.

## IV.A. Basic Requirements

Before comparing algorithms on specific properties, we need to clear the ground. The axiomatic approach works by specifying a list of desirable properties and then asking: which rules satisfy all of them? The properties range from the nearly trivial (no one gets a negative award) to the deeply substantive (consistency, self-duality). The trivial ones are starting conditions; the substantive ones do the real work.

Three properties are so fundamental they're almost always assumed rather than argued for.

**Non-negativity.** No claimant receives a negative award. This is not a deep moral principle; it's a definitional constraint. A "division" that requires someone to contribute money to the pot isn't dividing the estate — it's extracting a tax. Every rule we've encountered satisfies this.[^39]

**Claim-boundedness.** No claimant receives more than their claim. If you're owed 100 and the estate has plenty to go around, you get 100 — not 150. Again, this is definitional. Paying someone more than they're owed doesn't resolve the bankruptcy; it creates a new one.[^40]

**Balance (efficiency).** The awards sum to the full estate. Nothing left over, nothing created. Every dollar the estate contains goes to some claimant. Withholding funds would be punitive; creating funds would be fictional. All four of our rules satisfy balance.[^41]

Together, these three properties define what it means to produce a *valid* awards vector. They are the minimum requirements for any rule to be taken seriously.

They're also, in halakhic terms, so natural that they barely need arguing. Non-negativity corresponds to the basic principle that a court doesn't create obligations through its division — it only distributes what exists. Claim-boundedness corresponds to the principle that a creditor cannot collect more than she is owed (<span dir="rtl">אין נפרעין יותר מן החוב</span>). Balance corresponds to the principle that the entire estate must be distributed — the court doesn't withhold funds that belong to someone.

That these three properties are universally satisfied makes them invisible in most discussions. But they do rule out some conceivable approaches. For instance, a rule that says "destroy 10% of the estate as a penalty for having a dispute, then divide the rest" would violate balance. A rule that says "if a creditor is also a debtor to another creditor, subtract one from the other" would potentially violate non-negativity. The properties are the silent guardrails of the theory.

## IV.B. Equal Treatment of Equals

Imagine two creditors, each owed 100, facing an estate of 120. A rule that gives one creditor 80 and the other 40 would be hard to defend. Equal claims should yield equal awards.

**Property:** If cᵢ = cⱼ, then xᵢ = xⱼ.[^42]

This property is sometimes called *anonymity* or *symmetry*. It says: the rule looks only at the claims, not at the identities of the claimants. Creditor A and Creditor B, if they have the same claim, receive the same award — regardless of who they are, when they filed, or what their relationship to the debtor was.

In rabbinic law, equal treatment of equals is complicated by the concept of *shibud* (lien): earlier debts may take priority over later ones, creating an ordering among creditors with identical claims. Two creditors both owed 100, but one who lent money earlier has her debt secured by property the debtor acquired before the second loan. The first creditor's claim has *temporal priority* — it's the same amount but a stronger claim. The pure claims problem abstracts away this priority; the halakhic system preserves it.

All four of our rules satisfy equal treatment of equals in the pure model. It's hard to imagine a useful rule that doesn't, though we'll encounter contexts (like the Shapley Value, in Part V) where duplicating claimants can subtly violate it.

## IV.C. Resource Monotonicity

A man dies leaving an estate of 200 and three creditors. The awards are computed. The next day, a previously unknown bank account is discovered, bringing the estate to 250. Should any creditor receive *less* from the larger estate?

Clearly not. More estate, no one worse off.

**Property:** If E increases (with claims fixed), no claimant's award decreases.[^43]

This sounds obvious, but not every conceivable rule satisfies it. Consider a hypothetical rule: "if E < 100, use CEA; if E ≥ 100, use CEL." At E = 99, claims (50, 200): CEA gives (49.5, 49.5). At E = 101, CEL gives: total loss = 149, equal loss = 74.5, but Creditor 1's claim is only 50 < 74.5, so she gets 0. Remaining 101 goes to Creditor 2, with loss = 99. So CEL gives (0, 101). Creditor 1 went from 49.5 to 0 when the estate *increased* by 2. That's a violation of resource monotonicity — more money, less award. The discontinuous switch between rules at E = 100 creates a cliff.

The Talmud Rule avoids this because its transition from CEA-like to CEL-like behavior is smooth. The switch occurs at the half-claims, and the CEA and CEL computations are applied to the half-claims (which themselves ensure continuity). The award functions are continuous and non-decreasing in E.

CEA, CEL, the Proportional Rule, and CnD all satisfy resource monotonicity. So does the Talmud Rule. It is one of the properties that any serious candidate must pass.

## IV.D. Consistency

This property is the most powerful, and its rabbinic roots are the deepest.

Suppose a rule assigns awards to three creditors. Now creditor 1 takes her award and leaves. The remaining two creditors face a reduced estate (the original estate minus creditor 1's award) with their original claims. If we reapply the rule to this two-person problem, should the awards change?

A *consistent* rule says no. Paying off one creditor and reapplying the rule to the rest leaves everyone else's award unchanged.[^44]

**Property:** If x = f(E; c₁, c₂, ..., cₙ), then for any subset S of creditors, applying f to the problem (x(S); claims of S) gives the same awards as x restricted to S.

We verified this for the Ketuboth table in Part II — the Gemara's pairwise CnD verification was exactly a consistency check. Each pair of creditors, dividing their combined award using CnD, recovers their individual awards.

Consistency is powerful because it connects the n-person problem to the 2-person problem. If you accept CnD as the right rule for two people, and you demand consistency, then for each claims problem there is at most one possible answer for any number of claimants. Aumann and Maschler prove this as their Theorem A: *each bankruptcy problem has a unique CG-consistent solution*.[^45]

**Worked example: testing CEA for self-consistency.** Claims (100, 200, 300), E = 400. CEA gives: equal share 133⅓, Creditor 1 capped at 100, remaining 300 / 2 = 150 each. Awards: (100, 150, 150).

Now pay off Creditor 1 (she takes her 100 and leaves). Remaining estate: 300. Remaining claims: (200, 300). Apply CEA: equal share 150. Both claims exceed 150. Awards: (150, 150). Same as before. ✓

**Worked example: testing CEA for CnD-consistency.** Same problem. Creditors 2 and 3 together received 300. Their claims are 200 and 300. Apply CnD to (300, [200, 300]): Concession of 2 to 3: max(300 − 200, 0) = 100. Concession of 3 to 2: max(300 − 300, 0) = 0. Contested: 200. Split: 100 each. Awards: (100, 200). But CEA gave (150, 150). These don't match — CEA is *not* CnD-consistent.

This is the critical distinction. A rule can be self-consistent (paying off a player doesn't change others' awards) without being CnD-consistent (the pairwise divisions don't match CnD). Self-consistency is about the rule's relationship with *itself* across problem sizes. CnD-consistency is about the rule's relationship with a *specific* two-person rule.

CEA is self-consistent (paying off a creditor and reapplying CEA gives the same result). So is CEL. So is the Proportional Rule. Each is consistent with *itself*. But only one rule is consistent with Concede and Divide for two people — and that rule is the Talmud Rule.[^46]

## IV.E. Duality

Some problems feel like they're about dividing what's *there*. Others feel like they're about dividing what's *missing*. A creditor who receives 80 out of a claimed 100 can think of it as gaining 80 or as losing 20. The two framings are mathematically related.

Given a rule f, its *dual* f* is defined by:

> f*(E; d) = d − f(D − E; d)

where D is the sum of all claims. The dual of a rule "divides what's missing" in the same way the original rule "divides what's there."[^47]

A rule is *self-dual* if f* = f — if it treats gains and losses identically. This is a strong symmetry condition. It says the rule doesn't privilege either perspective.

The Proportional Rule is self-dual. Dividing 100 proportionally among claims of (60, 40, 30) gives (46.15, 30.77, 23.08). Dividing the *shortfall* of 30 proportionally gives losses of (13.85, 9.23, 6.92), which yields awards of (46.15, 30.77, 23.08). Same answer either way.

CEA is *not* self-dual. Its dual is CEL, and vice versa. To see this, apply CEA to claims (100, 200, 300) with E = 200: awards are (66⅔, 66⅔, 66⅔). Now compute the dual: apply CEA to the losses, with the *dual* estate D − E = 400. CEA(400; [100, 200, 300]): equal share 133⅓, Creditor 1 capped at 100. Remaining 300 / 2 = 150. Awards: (100, 150, 150). These are the *losses*, so the dual's awards = claims − losses = (0, 50, 150).

Compare: CEA gives (66⅔, 66⅔, 66⅔). The dual of CEA gives (0, 50, 150). These are different — CEA is not self-dual. But notice that (0, 50, 150) is exactly what CEL gives for E = 200: total loss 400, equal loss 133⅓, Creditor 1 wiped out at 0, remaining loss 300 between two, equal loss 150 each, awards (0, 50, 150). The dual of CEA is CEL.

CEA and CEL are a matched pair — one equalizes gains, the other equalizes losses — but neither treats both perspectives the same.[^48]

The Talmud Rule (which we'll meet in Part VI) is self-dual. This is its second defining property, after CnD-consistency. Aumann and Maschler prove it as Theorem B: *the CG-consistent rule is the unique self-dual rule that assigns CEA of the half-claims when E ≤ D/2*.[^49]

To verify self-duality for the Talmud Rule on the Ketuboth table: claims (100, 200, 300), D = 600.

At E = 200: awards = (50, 75, 75). At the dual estate D − E = 400: Talmud Rule gives awards = (50, 125, 225). Losses at E = 400: (100 − 50, 200 − 125, 300 − 225) = (50, 75, 75). Same as the awards at E = 200. ✓

At E = 100: awards = (33⅓, 33⅓, 33⅓). At D − E = 500: awards = (66⅔, 166⅔, 266⅔). Losses = (33⅓, 33⅓, 33⅓). ✓

The pattern: what the Talmud Rule *gives* at estate E is exactly what it *takes away* at estate D − E. Gains and losses are mirror images.

The Talmudic roots of duality run deep. Aumann and Maschler point to the principle <span dir="rtl">רובו ככולו</span> — "more than half is like the whole" (Hullin 27a) — as a conceptual precursor. When a creditor has received more than half her claim, she's on the "gains" side of the divide; her psychological frame is about what she lost. When she's received less than half, she's on the "losses" side; her frame is about what she gained. The halfway point is a psychological watershed, and the Talmud Rule respects it by switching between CEA-like behavior (for small estates) and CEL-like behavior (for large ones).[^50]

## IV.F. Claims Monotonicity and Population Monotonicity

Two more properties complete the standard toolkit.

**Claims monotonicity.** If one creditor's claim increases (all else equal), her award should not decrease. A larger claim entitles you to at least as much, never less.[^51]

This is satisfied by CEA, CEL, the Proportional Rule, and the Talmud Rule. Violations would create perverse incentives — creditors would benefit from understating their claims.

**Population monotonicity.** If a new creditor arrives (with the estate and existing claims unchanged), no existing creditor should receive *more* than before. Adding a mouth to feed means less for everyone, not more for some.[^52]

**Worked example of a violation.** Estate E = 100, claims (40, 80). CEL: total loss = 20, equal loss = 10. Awards: (30, 70). Now a third creditor arrives with claim 10. New claims: (40, 80, 10). Total loss = 30. Equal loss = 10. Creditor 3's claim (10) equals the equal loss: she gets 0. Remaining: 100 between claims (40, 80). Total loss = 20, equal loss = 10. Awards: (30, 70, 0).

No violation here — awards stayed the same. Let's try a different example. E = 100, claims (60, 80). CEL: total loss = 40, equal loss = 20. Awards: (40, 60). Add a third creditor with claim 15. Claims: (60, 80, 15). Total loss = 55. Equal loss = 18⅓. Creditor 3's claim (15) < 18⅓: she gets 0. Remaining: 100 between (60, 80). Loss = 40, equal loss = 20. Awards: (40, 60, 0). Again no change.

The population monotonicity violations for CEL tend to arise in more subtle configurations. The intuition for why it can fail: adding a small creditor who gets wiped out shouldn't change anything (and usually doesn't). But adding a medium-sized creditor can shift the loss distribution in ways that benefit some existing creditors. The Talmud Rule avoids these pathologies.

This is a strong condition and not universally satisfied. The Proportional Rule satisfies it. CEA satisfies it. CEL does not always satisfy it — adding a medium-sized creditor can redirect funds in unexpected ways.

Here is a summary of which rules satisfy which properties:

| Property | CEA | CEL | Proportional | CnD (2-person) | Talmud Rule |
|:---|:---:|:---:|:---:|:---:|:---:|
| Non-negativity | ✓ | ✓ | ✓ | ✓ | ✓ |
| Claim-boundedness | ✓ | ✓ | ✓ | ✓ | ✓ |
| Balance | ✓ | ✓ | ✓ | ✓ | ✓ |
| Equal treatment | ✓ | ✓ | ✓ | ✓ | ✓ |
| Resource monotonicity | ✓ | ✓ | ✓ | ✓ | ✓ |
| Consistency | ✓ | ✓ | ✓ | ✓ | ✓ |
| Self-duality | ✗ | ✗ | ✓ | ✓ | ✓ |
| Claims monotonicity | ✓ | ✓ | ✓ | ✓ | ✓ |
| Population monotonicity | ✓ | ✗ | ✓ | — | ✓ |

The Talmud Rule satisfies every property in this table. So does the Proportional Rule. The difference is that the Talmud Rule is CnD-consistent while the Proportional Rule is not. And CnD-consistency — the property the Gemara itself verified — is the one the Mishnah demands.

---

# Part V: BEYOND THE BASIC THREE

CEA, CEL, and Proportional are the most commonly discussed rules, but the landscape of proposed algorithms is much richer. Some were proposed by Rishonim in specific halakhic contexts. Others emerged from modern economics. Each adds a piece to the picture.

What makes this section different from the previous ones is that these algorithms were not developed as general-purpose division rules. Piniles' rule was an attempt to decode the Ketuboth table. The Shapley Value was designed for cooperative games in general, not bankruptcy in particular. Ibn Ezra was solving a cost-sharing problem, not a creditor dispute. The Ketzos was analyzing the interaction between evidence law and property law. Each algorithm arrived from a different direction, carrying its own assumptions and blind spots — and each illuminates something about the claims problem that the basic three rules do not.

## V.A. Piniles' Rule

In 1863, the Lithuanian scholar Zvi Menahem Piniles published *Darkah Shel Torah*, in which he proposed what may be the closest historical predecessor to the Talmud Rule.[^53]

Piniles' insight: apply CEA not to the full claims, but to the *half-claims*. Each creditor's effective entitlement, in this view, is half of what she's owed — the idea being that when the estate is insufficient, a creditor should expect at most half her due, and the division of that expectation should be equalized.

> **Algorithm: Piniles' Rule**
>
> INPUT: An estate E, claims c₁, c₂, ..., cₙ
>
> 1. Compute half-claims: h₁ = c₁/2, h₂ = c₂/2, ..., hₙ = cₙ/2.
> 2. Let H = h₁ + h₂ + ... + hₙ (sum of half-claims).
> 3. If E ≤ H: Apply CEA to (E; h₁, h₂, ..., hₙ).
> 4. If E > H: Each claimant receives hᵢ plus a share of the surplus (E − H), allocated by applying CEA to (E − H; h₁, h₂, ..., hₙ).
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Testing against the Ketuboth table.** Half-claims: (50, 100, 150). H = 300.

For E = 100 ≤ 300: CEA on half-claims. Equal share = 33⅓. All half-claims exceed 33⅓. Awards: (33⅓, 33⅓, 33⅓). **Matches.**

For E = 200 ≤ 300: CEA on half-claims. Equal share = 66⅔. Creditor 1's half-claim is 50 < 66⅔, so she gets 50. Remaining: 150 between two claimants. Equal share: 75. Both remaining half-claims (100, 150) exceed 75. Awards: (50, 75, 75). **Matches.**

For E = 300 = 300: CEA on half-claims. Everyone gets their full half-claim: (50, 100, 150). **Matches.**

Piniles' rule produces all three rows of the Ketuboth table — a remarkable achievement for 1863, more than a century before Aumann and Maschler. The reason it works: for E ≤ D/2 (where D is total claims), Piniles' rule coincides exactly with the Talmud Rule, because the Talmud Rule applies CEA to half-claims in this regime.[^54]

Where Piniles' rule diverges from the Talmud Rule is for estates larger than D/2. Piniles' rule continues applying CEA logic to the surplus above half-claims, while the Talmud Rule switches to a CEL-based approach for dividing losses. The difference matters: Piniles' rule is *not* self-dual, and it is not CnD-consistent for large estates.

Still, Piniles came remarkably close. Aumann and Maschler acknowledge his priority: "The earliest reference we have been able to find is Piniles (1861), who does not seem to have been widely noticed."[^55]

**Testing Piniles on the Bava Metzia garment cases.** Two claimants, claims (200, 100), E = 200. Half-claims: (100, 50). H = 150. E = 200 > 150. Each gets their half-claim plus surplus: surplus = 50, apply CEA to (50; [100, 50]). Equal share = 25. Both half-claims exceed 25. Each gets 25 more. Awards: 100 + 25 = 125 and 50 + 25 = 75. That gives (125, 75). But the Mishnah says (150, 50). Piniles' rule fails the contested garment.[^56]

What went wrong? For E > D/2, Piniles' rule continues applying CEA logic to the surplus above the half-claims. But the Talmud Rule switches to CEL logic for the losses. Let's verify: Talmud Rule for claims (200, 100), E = 200. D = 300. D/2 = 150. E > D/2. L = 100. Half-claims: (100, 50). CEA(100; [100, 50]): equal loss = 50. Both half-claims ≥ 50. Loss vector: (50, 50). Awards: (200 − 50, 100 − 50) = (150, 50). Correct.

The difference: Piniles distributes the surplus (E − D/2 = 50) by adding to half-claims using CEA. The Talmud Rule distributes the losses (D − E = 100) by subtracting from full claims using CEA of half-claims. For two claimants, this is exactly the distinction between Piniles giving (125, 75) and the Talmud Rule giving (150, 50). The 25 that Piniles adds to each claimant's half-claim is not the same operation as the 50 that the Talmud Rule subtracts from each full claim. The Talmud Rule's operation preserves CnD-consistency; Piniles' does not.

This failure is telling. A rule that matches the Ketuboth table but fails the Bava Metzia garment is not the rule the Talmud has in mind — or at least, it cannot be the full story. And historically, it was Hai Gaon's insight — that Ketuboth should be explained through Bava Metzia — that pointed to the correct requirement: CnD-consistency across *both* tractates.

## V.B. Run on the Bank

Imagine three creditors lined up outside a bank that's about to fail. The first one through the door grabs what she can — up to her claim. The second grabs from what's left. The third takes whatever remains. The division depends entirely on who arrived first.

This is random serial dictatorship: each ordering of the creditors produces a different allocation. The *run-on-the-bank* rule averages over all possible orderings.[^57]

> **Algorithm: Run on the Bank (Random Serial Dictatorship)**
>
> INPUT: An estate E, claims c₁, c₂, ..., cₙ
>
> 1. Enumerate all n! orderings of the claimants.
> 2. For each ordering:
>    - Process claimants in order.
>    - Each claimant takes min(remaining estate, their claim).
> 3. Average each claimant's take across all orderings.
>
> OUTPUT: Awards vector (x₁, x₂, ..., xₙ)
>
> end.

**Worked example with two claimants.** Claims (200, 100), E = 200.

Ordering 1 (A first): A takes min(200, 200) = 200. B takes min(0, 100) = 0. Division: (200, 0).
Ordering 2 (B first): B takes min(200, 100) = 100. A takes min(100, 200) = 100. Division: (100, 100).
Average: A gets (200 + 100)/2 = 150, B gets (0 + 100)/2 = 50. Awards: (150, 50).[^58]

This matches Concede and Divide exactly. For two claimants, run-on-the-bank and CnD always agree. The averaging process over all orderings, it turns out, is doing the same work as "concede what isn't in dispute, split the rest."

**Three-claimant run-on-the-bank.** Claims (100, 200, 300), E = 200. There are 3! = 6 orderings.

| Ordering | Takes... | Takes... | Takes... | Division |
|:---|:---:|:---:|:---:|:---:|
| (1, 2, 3) | 1 takes 100 | 2 takes 100 | 3 takes 0 | (100, 100, 0) |
| (1, 3, 2) | 1 takes 100 | 3 takes 100 | 2 takes 0 | (100, 0, 100) |
| (2, 1, 3) | 2 takes 200 | 1 takes 0 | 3 takes 0 | (0, 200, 0) |
| (2, 3, 1) | 2 takes 200 | 3 takes 0 | 1 takes 0 | (0, 200, 0) |
| (3, 1, 2) | 3 takes 200 | 1 takes 0 | 2 takes 0 | (0, 0, 200) |
| (3, 2, 1) | 3 takes 200 | 2 takes 0 | 1 takes 0 | (0, 0, 200) |

Averages: Creditor 1 = (100 + 100 + 0 + 0 + 0 + 0)/6 = 200/6 = 33⅓.
Creditor 2 = (100 + 0 + 200 + 200 + 0 + 0)/6 = 500/6 = 83⅓.
Creditor 3 = (0 + 100 + 0 + 0 + 200 + 200)/6 = 500/6 = 83⅓.

Run-on-the-bank gives (33⅓, 83⅓, 83⅓). The Mishnah says (50, 75, 75). Different.

The run-on-the-bank result is too extreme — it gives too little to the small creditor and too much to the larger creditors, because the orderings where a large creditor goes first are devastating to the others (the large creditor takes everything). The averaging smooths this out but not enough. The Talmud Rule's approach — using half-claims as caps — provides a more moderate result that better reflects the shared nature of the shortfall.

For three or more claimants, run-on-the-bank does *not* generally produce the same results as the Talmud Rule. It is equivalent to the Shapley Value restricted to the bankruptcy game, and it inherits the Shapley Value's consistency problems.

## V.C. The Shapley Value and Its Flaw

Lloyd Shapley introduced his value concept for cooperative games in 1953, and it has become one of the most celebrated ideas in game theory.[^59] Applied to claims problems, the Shapley Value is essentially run-on-the-bank computed through the cooperative game structure.

For two claimants, the Shapley Value coincides with CnD. For three or more, it generalizes naturally — but it has a critical flaw.

**The duplication problem.** Consider claims (200, 300) with E = 300. CnD gives (100, 200). The computation: Concession of 1 to 2 = max(300 − 200, 0) = 100. Concession of 2 to 1 = max(300 − 300, 0) = 0. Contested = 200. Split 100 each. Awards: (0 + 100, 100 + 100) = (100, 200).

Now imagine claimant 1 splits into two identical entities, each claiming 200, while claimant 2 splits into two identical entities, each claiming 300. The problem becomes claims (200, 200, 300, 300) with E = 600.

If the rule is well-behaved, the two copies of claimant 1 should receive a combined 200 total (100 each), and the two copies of claimant 2 should receive a combined 400 total (200 each). The original answer, duplicated.

The Shapley Value does not do this. With the duplicated problem, it produces approximately (116⅔, 116⅔, 183⅓, 183⅓) — so the two copies of claimant 1 receive a *combined* 233⅓, far more than the original 200. The two copies of claimant 2 receive a combined 366⅔, less than their expected 400.[^60]

**Why does this happen?** The Shapley Value averages over all 4! = 24 orderings of the four players. In many of these orderings, a copy of claimant 1 arrives early (before either copy of claimant 2) and grabs a large share of the estate. In the original two-person problem, there are only 2 orderings, and claimant 1 arrives first half the time. In the duplicated problem, there are far more orderings in which *at least one* copy of claimant 1 arrives early. The averaging over these extra orderings inflates the combined payment to claimant 1's copies.

The practical consequence: a creditor who discovers she can split her claim among multiple subsidiary entities (family members, shell companies) can extract more from the estate under the Shapley Value. This creates an incentive to fragment, which is incompatible with any reasonable notion of fairness.

The problem is that duplicating a claimant introduces new orderings and new coalitional interactions. The average over orderings shifts because there are now more permutations in which a copy of claimant 1 arrives early. Duplication is advantageous, which means the rule incentivizes a creditor to split her claim across multiple entities.

This inconsistency under cloning is a fundamental objection. A rule that can be gamed by fragmenting one's identity into multiple claims doesn't just fail a technical axiom — it fails a basic test of fairness. The Talmud Rule does not have this problem.[^61]

## V.D. Ibn Ezra's Layered Cost-Sharing

Abraham ibn Ezra (1089–1167), in his commentary on the Torah, describes a layered division principle that has structural parallels to Ravad's approach.[^62]

Consider a group of travelers who hire a ship. The ship has capacity for a journey of 300 miles, but the travelers are going different distances: one travels 100 miles, another 200, the third 300. How should they share the cost?

Ibn Ezra's answer: the first 100 miles are shared by all three travelers equally. The next 100 miles (from 100 to 200) are shared by only the two who travel that far. The final 100 miles (from 200 to 300) are borne by the last traveler alone.

**Worked example.** Ship fare is 600 for the full journey. Three travelers going 100, 200, 300 miles.

Layer 1 (miles 0–100): cost = 200, shared by 3. Each pays 66⅔.
Layer 2 (miles 100–200): cost = 200, shared by 2. Each pays 100.
Layer 3 (miles 200–300): cost = 200, borne by 1. Pays 200.

Total payments: Traveler 1 pays 66⅔. Traveler 2 pays 166⅔. Traveler 3 pays 366⅔.

If instead the total fare were 300 (half the full cost): Layer 1 capacity is 300, and the fare fills just Layer 1. Each traveler pays 100 equally. This matches CEA behavior for small estates.

The structural parallel to claims problems is exact. The travelers' distances are the claims; the ship's fare is the estate. The layered construction mirrors Ravad's layered equal division and, for estates below D/2, mirrors the Talmud Rule's behavior.

Where Ibn Ezra's principle is most illuminating is in its *intuition*. It provides a physical narrative for why equal division makes sense at each layer: the first 100 miles of shared travel are genuinely joint costs. No one has a stronger claim to that portion of the fare than anyone else. The differentiation begins only when some travelers leave the ship while others continue.

This "joint cost" framing makes CEA's behavior for small estates feel almost inevitable. When the estate is small — when everyone is still "on the ship" — equal shares are natural because the estate falls below every creditor's claim.

The layered model also illuminates *why* CEA produces kinks in the awards graph. The first traveler's departure from the ship at mile 100 corresponds to the first creditor's claim being fully absorbed in the first layer. After that departure, the cost-sharing changes discontinuously — the same dollar of fare is now shared by fewer travelers. These kinks are not artifacts of the algorithm; they reflect genuine changes in the *structure of the shared obligation* as some participants' claims are exhausted.

Modern cost-sharing theory formalizes this through "serial cost-sharing" rules, where users of a shared facility (a bridge, a utility, a communication network) pay based on the ordered structure of their demands. The connection to bankruptcy problems is direct and well-studied: the bankruptcy problem is formally equivalent to a cost-sharing problem where the "cost" is the shortfall and the "demands" are the claims.

The challenge, which Ibn Ezra's model does not address, is what happens when the estate grows large enough that some creditors are nearly satisfied. That transition requires the machinery of the Talmud Rule.

### A Talmudic Example of Coalitional CnD: Yevamot 38a

A remarkable application of pairwise CnD appears in a completely different halakhic context: the laws of levirate marriage (<span dir="rtl">יבום</span>) in Yevamot 38a, as highlighted by Schechter in his exposition of the Aumann-Maschler solution.

The scenario: Mr. B dies childless. His widow marries his brother, Mr. C, as required by levirate marriage law (Deuteronomy 25:5–6). C already has two sons, c₁ and c₂, from his first wife. Eight months later, B's widow gives birth to a son, b — whose father is uncertain (could be B or C). Then C dies. How is the grandfather A's estate divided among the three grandchildren: b, c₁, and c₂?

Young b's claim: half of A's estate goes to B's line and half to C's line. I am B's only son, so I get the full B-half. That's half the estate.

c₁ and c₂'s claim: B had no children (b is really C's son, born too soon to be B's). All of A's estate goes to C, and C had three sons (b, c₁, c₂), so we each get a third. Together we claim two-thirds.

The Talmud's resolution treats b as one claimant and (c₁, c₂) as a coalition — then applies CnD. b claims ½ of the estate. The coalition (c₁, c₂) claims ⅔. With an estate of 1 (normalized):

- b concedes that ⅓ of the estate is not his (the portion going to c₁ and c₂ even under b's own theory). So b's concession to the coalition: ⅓.
- The coalition concedes that ½ is not theirs (the portion going to b even under their theory). Concession to b: ½.
- Wait — concessions total ⅓ + ½ = ⅚, but the estate is only 1. The concessions overlap, which means some portion is conceded by *both* sides. Contested portion: 1 − ⅓ − ½ = ⅙.
- Split the contested ⅙ equally: 1/12 each.
- b gets ½ + 1/12 = 7/12. Coalition gets ⅓ + 1/12 = 5/12.
- c₁ and c₂ split the coalition's share equally: 5/24 each.

Final division: b = 7/12 ≈ 58.3%, c₁ = c₂ = 5/24 ≈ 20.8% each.

This is CnD applied to a family law question, not a bankruptcy. The algorithm travels across tractates, across subject matter, across centuries of commentary. Its principle — concede what isn't in dispute, split the rest — is portable enough to handle contested garments, bankrupt estates, and uncertain paternity.

The Yevamot case also illustrates something about how the Talmud thinks about algorithms. No one in the Gemara says "apply the contested-garment rule to this family dispute." The connection is implicit — the reader is expected to recognize that the same logical structure underlies both problems. The Talmud teaches algorithms not by naming them and cataloging their applications, but by placing structurally similar problems in proximity and trusting the student to see the pattern. The algorithm is never separated from its context — it is always embedded in a specific legal question — and yet the same pattern recurs across vastly different domains. That recurrence is itself the Talmud's way of saying: this is a general principle, not a special rule.

## V.E. Ketzos HaChoshen

Rabbi Aryeh Leib Heller (1745–1812), in his monumental commentary Ketzos HaChoshen on Shulchan Aruch Choshen Mishpat Siman 138, brings a different analytical framework to the contested garment: the distinction between *bari* (certain) and *shema* (uncertain) claims.[^63]

The distinction matters because it affects the underlying logic of division. In the Mishnah's garment case, neither claimant can prove ownership — each claim is contested. But the claims differ in their epistemic status. The claim of "all mine" is a claim of certainty (<span dir="rtl">ברי</span>): the claimant asserts, with full confidence, that the entire garment is his. The claim of "half mine" is also a claim of certainty — but about a smaller portion.

The Ketzos analyzes how the division changes when one claim is *bari* (certain) and the other is *shema* (perhaps) — when one claimant says "it is definitely mine" and the other says "it might be mine." In such cases, the Talmud has different presumption rules. A *bari* claim carries more weight against a *shema* claim, not because of any division algorithm, but because of evidentiary presumptions about who is more likely to be telling the truth.[^64]

The algorithmic consequence: if the claimant asserting "all mine" has a *bari* claim while the claimant asserting "half" has only a *shema* claim, the division shifts further toward the certain claimant. The Ketzos explores how *migo* — the principle that a claimant who could have made a stronger claim but chose a weaker one is presumed to be honest — interacts with the Concede and Divide algorithm.[^65]

**Netivot HaMishpat**, the commentary of Rabbi Yaakov of Lissa (1760–1832), disagrees with the Ketzos on key points. The Netivot holds that the *bari*/*shema* distinction should not modify the division algorithm but should operate at a prior stage — determining *whether* to apply the algorithm at all, rather than changing *how* it works.[^66] The dispute between Ketzos and Netivot on Siman 138 became one of the most celebrated analytical disagreements in Acharonic literature, studied in yeshivot to this day as a masterclass in legal reasoning.

**A concrete scenario.** Two people hold a garment worth 200. A says: "It is definitely all mine" (*bari*). B says: "I think half of it might be mine" (*shema*). Under standard CnD, if we take the claims at face value (A claims 200, B claims 100): A gets 150, B gets 50.

The Ketzos argues that the *shema* quality of B's claim weakens it. B isn't asserting ownership with certainty — she's hedging. Should a hedging claim receive the same algorithmic treatment as a certain one?

**Worked example under the Ketzos.** Standard CnD: B concedes 100 (since she claims only 100). A concedes 0. Contested portion = 100. Split equally: 50 each. Awards: A = 100 + 50 = 150, B = 0 + 50 = 50.

Under the Ketzos's modification: B's claim is *shema*, so the contested portion is not split equally. The certain claimant (A) has a stronger position in the split of the contested remainder. If, for instance, the *bari* claim receives two-thirds of the contested portion (reflecting its epistemic advantage), then: A = 100 + 66⅔ = 166⅔, B = 0 + 33⅓ = 33⅓. The exact weighting depends on the strength of the *shema* and the applicability of *migo*, but the direction is clear: epistemic certainty shifts the contested portion toward the certain claimant.

The Ketzos does not specify a precise numerical weight — the analysis is qualitative rather than quantitative. The point is structural: the "split the contested portion equally" step of CnD assumes symmetric claims, and when the claims are epistemically asymmetric, equal splitting is no longer justified.

The Netivot counters: the *bari*/*shema* distinction operates at the stage where the court *admits* the claim, not where it *divides* the estate. If B's *shema* claim passes the evidentiary threshold — if the court decides it's sufficient to warrant a hearing — then it enters the division algorithm as a full claim. The algorithm itself should be epistemic-neutral. In the Netivot's framework, the worked example above would never arise: if B's *shema* claim is admitted, the standard CnD applies and yields (150, 50). If it's not admitted, B receives nothing. There is no middle ground where the claim enters the algorithm at reduced weight.

This is a deep jurisprudential question. Should the division algorithm internalize the quality of the evidence, or should evidence quality be resolved upstream, with only validated claims entering the algorithm? The Ketzos takes the first view (evidence-sensitive algorithms); the Netivot takes the second (evidence-neutral algorithms with evidence-sensitive admission).

For our purposes, the debate illuminates the boundary conditions of algorithmic division. The pure claims problem assumes that all claims are valid and the only question is allocation. The Ketzos shows that in practice, the Talmud operates in a richer space where the *epistemic quality* of a claim — how certain it is — affects the division.

The debate has a precise modern analog. In mechanism design theory, the distinction between "direct mechanisms" (where agents report their types truthfully and the mechanism computes the allocation) and "indirect mechanisms" (where the mechanism uses observed behavior rather than reports) mirrors the Netivot-Ketzos distinction. The Netivot's view — resolve evidence upstream, feed only validated claims to the algorithm — is a direct mechanism. The Ketzos's view — embed evidence quality into the algorithm itself — is closer to an indirect mechanism where the algorithm processes all available information simultaneously.

Algorithms are embedded in a larger framework of evidence, presumption, and judicial reasoning. The mathematical theory of mechanism design, which studies how to design allocation systems when participants may have private information about their claims, engages with exactly the same questions. The fact that two eighteenth-century commentators anticipated the central question of twentieth-century mechanism design — should information be processed before or within the allocation rule? — is a testament to the depth of the halakhic analysis.

## V.F. Shulchan Aruch: Codified Division Rules

The Shulchan Aruch of Rabbi Yosef Karo (1488–1575), with the glosses of Rabbi Moshe Isserles (the Rema), codifies practical division rules across several sections of Choshen Mishpat.[^67]

**Siman 138** addresses the contested garment directly, and it is the most algorithmically precise section of Choshen Mishpat's treatment of division. The Shulchan Aruch rules according to the Mishnah: CnD applies, with each claimant swearing to the validity of their claim.

The ruling covers several variant scenarios:

- *Both hold the garment and both claim all*: divide equally (CnD with equal claims).
- *Both hold it, one claims all and one claims half*: three-fourths to the all-claimant, one-fourth to the half-claimant (CnD with unequal claims).
- *One holds it and the other claims it*: the holder retains possession, and the claimant must bring proof. No CnD — the algorithm doesn't apply when only one party has physical possession.
- *Neither holds it, both claim it*: depends on the circumstances — sometimes CnD, sometimes *shuda d'dayanei*, depending on whether there's any basis for distinguishing the claims.

The condition that both claimants must physically hold the garment is not merely procedural; it is a substantive prerequisite for the CnD algorithm. Physical holding (<span dir="rtl">תפיסה</span>) establishes that both claims have at least minimal credibility. A claim made by someone who doesn't hold the object is, in the Mishnah's framework, categorically weaker — it requires proof rather than an algorithm. The Sma (Sefer Me'irat Einayim) and Shach (Siftei Kohen) elaborate on the conditions under which the rule applies — requiring, for instance, that both claimants physically hold the garment.[^68]

**Simanim 104–105** address creditor priority when the debtor's assets are insufficient. Here the Shulchan Aruch distinguishes between different types of debts (secured vs. unsecured, earlier vs. later) and establishes priority orderings that interact with the division algorithms. A creditor with a lien on specific property has priority over general creditors; among general creditors, the division follows established rules.[^69]

**Worked example: secured vs. unsecured creditors.** A debtor owes three creditors: Creditor A holds a lien on a specific field worth 80 (secured claim of 120). Creditor B has an unsecured claim of 200. Creditor C has an unsecured claim of 100. The debtor's total assets are 300.

Step 1: Creditor A's secured claim. The field is worth 80, and A's claim is 120. A takes the field (80) and enters the unsecured pool with a residual claim of 40.

Step 2: Remaining assets = 300 − 80 = 220. Unsecured claims: A has 40, B has 200, C has 100. Total claims = 340 > 220.

Step 3: Within the unsecured pool, division follows the applicable rule. Under proportional division: A receives (40/340) × 220 = 25.88. B receives (200/340) × 220 = 129.41. C receives (100/340) × 220 = 64.71.

Final awards: A receives 80 (from the field) + 25.88 = 105.88, B receives 129.41, C receives 64.71. Total: 300.

The priority structure creates a two-tier system: resolve secured claims against their collateral first, then divide the remainder among unsecured claims. The choice of division rule within the unsecured tier (proportional, CEA, or otherwise) is a separate decision — and it is here that the Rishonim's debates apply.

**Simanim 171–176** deal with partnership and joint ventures. Division of partnership assets follows its own logic — profits are shared based on capital contributions and labor agreements, and dissolution requires evaluation of both tangible assets and ongoing obligations.[^70]

**Simanim 175–176** address specific partnership dissolution scenarios, including cases where partners contributed unequal capital and cases involving *iska* (investment-and-loan hybrid) arrangements where the division depends on whether profits or losses have been incurred.[^71]

The codification represents a practical decision: which algorithm applies to which circumstance.

The Sma (Sefer Me'irat Einayim) adds important qualifications to the contested-garment rule. He notes that CnD applies only when both claimants physically hold the garment (<span dir="rtl">תרוייהו נקטי</span>). If one claimant holds it and the other merely claims it, different rules apply — the holder has a presumptive advantage (<span dir="rtl">מוחזק</span>) that shifts the burden of proof. The algorithm changes based on the physical circumstances, not just the claims.

The Shach (Siftei Kohen) further distinguishes between cases where the garment was found by both simultaneously, where one found it first and the other took it from him, and where the ownership history is entirely unknown. Each scenario invokes different evidentiary presumptions that feed into or bypass the CnD algorithm.

The Rema's glosses introduce Ashkenazic custom variations. In some communities, the practice for creditor disputes followed proportional division rather than any of the Talmudic rules, because proportional division is simpler to administer and less dependent on the disputed interpretation of the Ketuboth passage. Custom (<span dir="rtl">מנהג</span>), in the Rema's framework, can determine which algorithm the courts apply — a meta-level choice about algorithms.

Rather than seeking a single universal rule, the Shulchan Aruch maps different contexts to different algorithms — CnD for contested property, priority-based rules for creditors, proportional rules for partnerships. The unification attempted by the Talmud Rule is retrospective; the codified law remains pluralistic.

## V.G. Hai Gaon's Methodology

Rabbi Hai Gaon (939–1038), the last of the great Geonim and head of the Pumbedita academy in what is now Iraq, made a crucial suggestion that went largely unappreciated for nine centuries. In his opinion, as recorded by the Rif, the Mishnah in Ketuboth about estate division should be explained on the basis of the Mishnah in Bava Metzia about the contested garment.[^72]

This is the very connection that Aumann and Maschler would prove is correct: the Ketuboth numbers are CnD-consistent. Hai Gaon saw the link but did not make it explicit — he suggested the direction without working out the details.

Tsvi Groner's monograph on Hai Gaon's legal methodology documents the Gaon's broader approach to claims adjudication.[^73] Hai Gaon was distinctive among the Geonim for his willingness to engage with the logical structure of halakhic arguments, not merely their textual pedigree. His suggestion that Ketuboth should be explained through Bava Metzia reflects this structural thinking: rather than treating each Talmudic passage as an isolated ruling, he sought unifying principles.

Hai Gaon's position was not arbitrary. He was responding to a real structural observation: the Ketuboth table's numbers exhibit the same pairwise CnD-consistency that the Bava Metzia garment cases do. The Gemara in Ketuboth explicitly invokes the garment principle to verify the pairwise divisions. Hai Gaon took this invocation seriously — not as a passing analogy but as a statement of underlying unity. The same principle, he argued, should govern both cases.

The irony is that Hai Gaon's suggestion was not pursued. Subsequent generations treated the Bava Metzia and Ketuboth passages as addressing different circumstances (contested ownership vs. insufficient assets), and the connection languished. Tosafot's objection — that the two situations differ in kind — carried the day. For eight centuries, the majority view was that the garment rule and the estate rule were different algorithms applied in different contexts, not manifestations of a single underlying principle.

When Aumann and Maschler rediscovered the connection, they acknowledged the precedent: "The early medieval authority Rabbi Hai Gaon... did express the opinion that the Mishna in Kethubot should be explained on the basis of that in Bava Metzia. He did not, however, make an explicit connection, and in subsequent years, this line of attack was abandoned."[^74]

Hai Gaon was right. The Ketuboth table *is* explained by the Bava Metzia principle. CnD-consistency — the property the Gemara verified and Hai Gaon elevated to a structural principle — is the key that unlocks the entire theory. It takes a certain intellectual courage to insist on a connection that the mainstream has abandoned. Hai Gaon had that courage. He also had the disadvantage of working nine centuries before the mathematical tools existed to prove himself right.

---

# Part VI: THE AUMANN-MASCHLER BREAKTHROUGH

## VI.A. Two Economists Read the Talmud

By the mid-twentieth century, the state of the Ketuboth problem was essentially unchanged from the Rishonim's era. Multiple partial explanations existed. No unified algorithm was known. The passage remained, as it had been for centuries, the most famous unsolved puzzle in Talmudic mathematics.

The landscape of potential solutions was well-mapped: CEA matched one row, proportional matched another, and Piniles' half-claims approach matched all three rows but failed the Bava Metzia cases. The missing piece was a rule that could handle both tractates — one that was CnD-consistent for the garment and produced the correct numbers for the widows.

In 1980 or 1981, a young man named Shlomo Aumann was studying at a yeshiva in Jerusalem. He came across the puzzling Mishnah in Ketuboth and brought it home to his father, Robert Aumann, a professor of mathematics at the Hebrew University.[^75]

Robert Aumann — who would later receive the Nobel Prize in Economics (2005) for his work on game theory — and his colleague Michael Maschler set to work on the problem. The two were an extraordinary pair: Aumann, the theoretical visionary with deep connections to both mathematics and Jewish scholarship; Maschler, the rigorous game theorist who provided the analytical machinery. Both were at the Hebrew University of Jerusalem, and both had extensive experience with cooperative game theory.

Aumann later recounted that in the research process, the order of discovery was reversed from the order of presentation. They first realized that the Mishnah's numbers coincide with the nucleolus of a naturally defined cooperative game. Only after that game-theoretic discovery did they find the non-game-theoretic justifications — CnD-consistency, self-duality, the coalitional procedure — which are independent of game theory and more in the spirit of the Talmudic analysis. The paper presents the non-game-theoretic results first, saving the nucleolus connection for the final section, because the independent justifications are more elementary and more directly rooted in Talmudic principles.[^76]

The paper was published in 1985 in the *Journal of Economic Theory*. Its dedication reads: "To the memory of Shlomo Aumann, Talmudic scholar and man of the world, killed in action near Khush-e-Dneiba, Lebanon, on the eve of the nineteenth of Sivan, 5742 (June 9, 1982)."

Shlomo Aumann did not live to see the solution to the puzzle he had brought his father. The paper that solved a two-thousand-year-old mathematical mystery is, at its heart, a memorial.

Aumann and Maschler are careful to note the boundaries of their contribution: "In particular, this article should on no account be used as a source for Talmudic law." The paper is a mathematical analysis of a mathematical structure embedded in a legal text. The legal conclusions — how courts should actually divide estates — remain the province of the halakhic authorities. What Aumann and Maschler provide is a proof that the Mishnah's specific numbers arise from a unique rule with extraordinary mathematical properties.

## VI.B. The Talmud Rule

Aumann and Maschler's central discovery is a single algorithm that produces all three rows of the Ketuboth table. The algorithm stitches together CEA and CEL through the half-claims, with the transition point at E = D/2 (where D is the sum of all claims).[^77]

The intuition: when the estate is small (E ≤ D/2), think in terms of what each creditor *gains*. Apply CEA, but use half-claims as the caps. No creditor gets more than half her claim in this regime. When the estate is large (E > D/2), switch to thinking about what each creditor *loses*. Apply CEL, using half-claims as the floor — no creditor loses more than half her claim.

> **Algorithm: The Talmud Rule**
>
> INPUT: An estate E, claims c₁ ≤ c₂ ≤ ... ≤ cₙ
>
> 1. Compute half-claims: hᵢ = cᵢ / 2 for each i.
> 2. Let D = c₁ + c₂ + ... + cₙ (sum of claims).
> 3. If E ≤ D/2 (small estate):
>    - Apply CEA to the problem (E; h₁, h₂, ..., hₙ).
>    - OUTPUT: the CEA awards.
> 4. If E > D/2 (large estate):
>    - Compute total losses: L = D − E.
>    - Apply CEA to the problem (L; h₁, h₂, ..., hₙ).
>    - For each claimant i: Award = cᵢ − CEA loss.
>    - OUTPUT: the awards.
>
> end.

The key insight in Step 4: for large estates, we compute the *losses* using CEA on half-claims and then subtract from full claims. This ensures that each creditor's loss is capped at half her claim — no one loses more than half of what she's owed. The symmetry with Step 3 (where each creditor's *gain* is capped at half her claim) is what makes the rule self-dual.

**Verification against the Ketuboth table.** Claims (100, 200, 300). D = 600. D/2 = 300. Half-claims: (50, 100, 150).

**E = 100 (≤ 300, small estate):** Apply CEA to (100; [50, 100, 150]). Equal share: 100/3 = 33⅓. All half-claims ≥ 33⅓. Awards: **(33⅓, 33⅓, 33⅓)** ✓

**E = 200 (≤ 300, small estate):** Apply CEA to (200; [50, 100, 150]). Equal share: 200/3 = 66⅔. Creditor 1's half-claim is 50 < 66⅔, so she gets 50. Remaining: 150 between two claimants. Equal share: 75. Both remaining half-claims (100, 150) ≥ 75. Awards: **(50, 75, 75)** ✓

**E = 300 (= 300, boundary):** Apply CEA to (300; [50, 100, 150]). Sum of half-claims = 300 = E. Each creditor gets her full half-claim: (50, 100, 150). Awards: **(50, 100, 150)** ✓

All three rows. One algorithm. And the algorithm is not a special-purpose construction designed to fit these three examples. It's a general rule — applicable to any number of creditors with any claims and any estate size — that happens to produce these specific numbers for these specific inputs.

To feel the weight of that, try a different set of claims and verify the algorithm works mechanically.

**New example: claims (50, 100, 150), E = 120.** D = 300. D/2 = 150. Half-claims: (25, 50, 75). E = 120 ≤ 150, so small-estate regime. Apply CEA to (120; [25, 50, 75]). Equal share = 40. Creditor 1's half-claim (25) < 40: she's satisfied at 25. Remaining: 95 between two claimants. Equal share: 47.5. Creditor 2's half-claim (50) ≥ 47.5, Creditor 3's (75) ≥ 47.5. Awards: (25, 47.5, 47.5).

Verify CnD-consistency: Creditors 2 and 3 received 95 combined. Claims: 100 and 150. CnD(95, [100, 150]): Concession of 2 to 3 = max(95 − 100, 0) = 0. Concession of 3 to 2 = max(95 − 150, 0) = 0. Contested = 95. Split: 47.5 each. ✓

**New example: claims (50, 100, 150), E = 200.** D = 300. D/2 = 150. E = 200 > 150, so large-estate regime. L = D − E = 100. Apply CEA to losses: CEA(100; [25, 50, 75]). Equal loss = 33⅓. All half-claims ≥ 33⅓. Loss vector: (33⅓, 33⅓, 33⅓). Awards: (50 − 33⅓, 100 − 33⅓, 150 − 33⅓) = (16⅔, 66⅔, 116⅔).

Verify CnD-consistency: Creditors 1 and 2 received 83⅓ combined. Claims: 50 and 100. CnD(83⅓, [50, 100]): Concession of 1 to 2 = max(83⅓ − 50, 0) = 33⅓. Concession of 2 to 1 = max(83⅓ − 100, 0) = 0. Contested = 50. Split: 25 each. Awards: (25, 58⅓). But we said (16⅔, 66⅔). These don't match!

Wait — let's recheck. CnD(83⅓, [50, 100]): Concession of 1 to 2 = max(83⅓ − 50, 0) = 33⅓. Concession of 2 to 1 = max(83⅓ − 100, 0) = 0. Contested = 83⅓ − 33⅓ − 0 = 50. Split: 25 each. Award₁ = 0 + 25 = 25. Award₂ = 33⅓ + 25 = 58⅓.

But the Talmud Rule gave (16⅔, 66⅔). That's different. So is the Talmud Rule not CnD-consistent?

Let's recompute the Talmud Rule more carefully. E = 200, claims (50, 100, 150). D = 300, D/2 = 150. E > D/2. Total loss L = 100. Half-claims: (25, 50, 75). Apply CEA to losses: CEA(100; [25, 50, 75]). Equal share = 100/3 = 33⅓. h₁ = 25 < 33⅓, so Creditor 1's loss is capped at 25. Remaining loss: 75. Two claimants. Equal loss: 37.5. h₂ = 50 ≥ 37.5, h₃ = 75 ≥ 37.5. Loss vector: (25, 37.5, 37.5). Awards: (50 − 25, 100 − 37.5, 150 − 37.5) = (25, 62.5, 112.5).

Now recheck CnD-consistency. Creditors 1 and 2: combined award = 87.5. Claims: (50, 100). CnD(87.5, [50, 100]): Concession of 1 to 2 = max(87.5 − 50, 0) = 37.5. Concession of 2 to 1 = max(87.5 − 100, 0) = 0. Contested = 50. Split: 25 each. Awards: (25, 62.5). ✓

Creditors 1 and 3: combined = 137.5. Claims: (50, 150). CnD(137.5, [50, 150]): Concession of 1 to 3 = max(137.5 − 50, 0) = 87.5. Concession of 3 to 1 = max(137.5 − 150, 0) = 0. Contested = 50. Split: 25 each. Awards: (25, 112.5). ✓

Creditors 2 and 3: combined = 175. Claims: (100, 150). CnD(175, [100, 150]): Concession of 2 to 3 = max(175 − 100, 0) = 75. Concession of 3 to 2 = max(175 − 150, 0) = 25. Contested = 75. Split: 37.5 each. Awards: (25 + 37.5, 75 + 37.5) = (62.5, 112.5). ✓

Every pair checks out. The initial computation error came from applying CEA incorrectly (forgetting that CEA caps at the half-claim, not at equal division). The careful recomputation confirms: the Talmud Rule is CnD-consistent. Working through the arithmetic by hand — catching the error, recomputing, rechecking — is precisely the kind of exercise that builds the intuition. The algorithm is mechanical, but trusting it requires seeing it work.

**Extended table.** The Talmud Rule generates a complete awards schedule for claims (100, 200, 300) at every estate value from 0 to 600:

| Estate | Creditor 1 | Creditor 2 | Creditor 3 | Regime |
|:---:|:---:|:---:|:---:|:---|
| 0 | 0 | 0 | 0 | Small |
| 100 | 33⅓ | 33⅓ | 33⅓ | Small |
| 150 | 50 | 50 | 50 | Small |
| 200 | 50 | 75 | 75 | Small |
| 250 | 50 | 100 | 100 | Small |
| 300 | 50 | 100 | 150 | Boundary |
| 350 | 50 | 100 | 200 | Large |
| 400 | 50 | 125 | 225 | Large |
| 450 | 50 | 150 | 250 | Large |
| 500 | 66⅔ | 166⅔ | 266⅔ | Large |
| 600 | 100 | 200 | 300 | Large |

**Detailed computation for E = 350 (large estate).** D = 600. L = D − E = 250. Half-claims: (50, 100, 150). Apply CEA to losses: CEA(250; [50, 100, 150]). Equal loss = 250/3 = 83⅓. Creditor 1's half-claim is 50 < 83⅓: her loss is capped at 50. Remaining loss: 200 between two claimants. Equal loss: 100. Creditor 2's half-claim (100) = 100: she loses exactly her half-claim. Creditor 3's half-claim (150) ≥ 100: she loses 100. Loss vector: (50, 100, 100). Awards: (100 − 50, 200 − 100, 300 − 100) = (50, 100, 200). ✓

**Detailed computation for E = 450 (large estate).** L = 150. CEA(150; [50, 100, 150]). Equal loss = 50. All half-claims ≥ 50. Loss vector: (50, 50, 50). Awards: (50, 150, 250). Each creditor has lost exactly half her claim — the maximum loss before the Talmud Rule switches perspective. This is the mirror of E = 150 in the small-estate regime, where each creditor had gained exactly 50 (less than half her claim for Creditors 2 and 3).

**Detailed computation for E = 500 (large estate).** L = 100. CEA(100; [50, 100, 150]). Equal loss = 33⅓. Creditor 1's half-claim (50) ≥ 33⅓: she loses 33⅓. All do. Loss vector: (33⅓, 33⅓, 33⅓). Awards: (66⅔, 166⅔, 266⅔).

Examine the structure. In the small-estate regime (E ≤ 300), awards grow from zero. The three creditors receive equal shares until E = 150, when Creditor 1 hits her half-claim ceiling of 50. After that, only Creditors 2 and 3 continue to receive additional funds, equally, until E = 250, when Creditor 2 hits her half-claim ceiling of 100. Above 250, only Creditor 3 receives additional funds, reaching her half-claim of 150 at E = 300.

At the boundary (E = 300 = D/2), everyone has received exactly half her claim: (50, 100, 150).

In the large-estate regime (E > 300), the logic mirrors: losses shrink from full claims. At E = 350, total losses = 250. CEA on (250; [50, 100, 150]): equal loss = 250/3 = 83⅓, Creditor 1's half-claim is 50 < 83⅓, so her loss is 50; remaining loss 200 between two, equal loss 100 each. Awards: (100 − 50, 200 − 100, 300 − 100) = (50, 100, 200). This tracks the table.

The table exhibits perfect symmetry around the center. Compare E = 100 and E = 500: at E = 100 the awards are (33⅓, 33⅓, 33⅓); at E = 500 the *losses* are (100 − 66⅔, 200 − 166⅔, 300 − 266⅔) = (33⅓, 33⅓, 33⅓). The awards at E and the losses at D − E are identical. This is self-duality made visible — the rule divides gains at E in exactly the same way it divides losses at D − E.

The symmetry extends further. Compare E = 200 and E = 400: at E = 200, awards are (50, 75, 75); at E = 400, losses are (100 − 50, 200 − 125, 300 − 225) = (50, 75, 75). Identical. The entire lower half of the table mirrors the upper half through the center line at E = 300.

### Kaminski's Glassware Proof

A beautiful physical realization of the Talmud Rule was discovered by Marek Kaminski, a political scientist at the University of California, Irvine. Kaminski was a student of H. Peyton Young and was struggling to visualize the Talmud Rule when, as he writes, "the hydraulic idea came to my mind in one of those unexplainable flashes."

The construction: for each creditor i with claim cᵢ, build a glass vessel divided into a top half and a bottom half, each with capacity cᵢ/2. Connect all the bottom halves with a tube at the base, and connect all the top halves with a tube at the top. The total capacity of the system is c₁ + c₂ + ... + cₙ = D.

Now pour liquid — representing the estate E — into this system.

When E is small, the liquid fills only the bottom halves. Because they're connected, it rises to the same level in each glass. Each creditor's award equals the amount of liquid in their glass, which is the same for all (equal division) until the smallest glass's bottom half fills up at cᵢ/2. After that, the liquid continues rising equally in the remaining glasses. This is CEA applied to half-claims.

When E is large and you've already filled all the bottom halves (E > D/2), the liquid begins filling the top halves. These are also connected, so the liquid rises equally — but now the *remaining space* is what matters. The smallest glass fills first (least remaining capacity), and the others continue. The division of the *remaining space* is CEA of half-claims applied to the losses.

The physical system automatically computes the Talmud Rule. Pour in any amount of liquid, read off the levels — those are the awards. The connected tubes enforce CnD-consistency (any pair of glasses distributes the liquid between them according to CnD). The symmetry of the vessel (each glass split into equal top and bottom halves) enforces self-duality. And because water seeks a common level in connected vessels, the allocation is unique.

Kaminski's construction provides an independent proof of the Aumann-Maschler theorem: the connected-glassware system produces a unique allocation, that allocation is CnD-consistent, and therefore it must equal the Talmud Rule. No linear algebra required — just fluid dynamics.

## VI.C. The Recursive Formulation

Aumann and Maschler provide a second way to compute the same answer: the *coalitional procedure*.[^78]

The idea: treat the smallest claimant as one player and all remaining claimants pooled together as the other player. Apply CnD to this two-person problem. Then take the coalition's award and recursively divide it among its members using the same procedure.

**Worked example.** Claims (100, 200, 300), E = 200.

Step 1: Player 1 has claim 100. The coalition {2, 3} has combined claim 500. Apply CnD to (E = 200, claims = [100, 500]). Concession of Player 1 to coalition: max(200 − 100, 0) = 100. Concession of coalition to Player 1: max(200 − 500, 0) = 0. Contested: 200 − 100 − 0 = 100. Half each: 50. Player 1 gets 0 + 50 = 50. Coalition gets 100 + 50 = 150.

Step 2: The coalition {2, 3} must divide 150 between claims 200 and 300. Apply CnD to (E = 150, claims = [200, 300]). Concession of 2 to 3: max(150 − 200, 0) = 0. Concession of 3 to 2: max(150 − 300, 0) = 0. Contested: 150. Half each: 75. Awards: (75, 75).

Final: (50, 75, 75). Matches the Talmud Rule and the Mishnah. ✓

This coalitional approach has a deep connection to the Jerusalem Talmud's language. Samuel's statement that the creditors "empower each other" — that the third empowers the second to deal with the first — describes exactly this recursive coalition formation. The third creditor allies with the second; together they negotiate with the first using CnD; then they divide their share between themselves.[^79]

**Second worked example.** Claims (100, 200, 300), E = 300.

Step 1: Player 1 (claim 100) vs. coalition {2,3} (claim 500). CnD(300, [100, 500]): Concession of 1: max(300 − 100, 0) = 200. Concession of coalition: max(300 − 500, 0) = 0. Contested: 100. Split: 50 each. Player 1 gets 0 + 50 = 50. Coalition gets 200 + 50 = 250.

Step 2: Coalition {2,3} divides 250 between claims 200 and 300. CnD(250, [200, 300]): Concession of 2: max(250 − 200, 0) = 50. Concession of 3: max(250 − 300, 0) = 0. Contested: 200. Split: 100 each. Creditor 2 gets 0 + 100 = 100. Creditor 3 gets 50 + 100 = 150.

Final: (50, 100, 150). Matches. ✓

**Third worked example: five claimants.** Aumann and Maschler illustrate the coalitional procedure with n = 5, claims (100, 100, 100, 100, 100) — five equal claims — and E = 510.

Step 1: Player 1 (claim 100) vs. coalition {2,3,4,5} (claim 400). CnD(510, [100, 400]): Concession of 1: max(510 − 100, 0) = 410. Concession of coalition: max(510 − 400, 0) = 110. Contested: 510 − 410 − 110 = −10. Wait — that's negative.

When concessions exceed the estate, the contested portion is zero, and the algorithm reduces to: each side gets exactly their concession from the other. Player 1 gets 110. Coalition gets 400. But 110 + 400 = 510? No — 110 > 100, which violates claim-boundedness. The issue is that with E > sum of claims, everyone can be fully paid. The coalitional procedure handles this: if E ≥ D, all claims are paid in full. For E = 510 > 500 = D, this means everyone gets 100 and 10 is left over. (The problem isn't well-formed if E > D in the standard model.)

Let's fix the example: E = 350, five equal claims of 100.

Step 1: Player 1 (claim 100) vs. coalition {2,3,4,5} (claim 400). CnD(350, [100, 400]): Concession of 1: max(350 − 100, 0) = 250. Concession of coalition: max(350 − 400, 0) = 0. Contested: 100. Split: 50 each. Player 1 gets 50. Coalition gets 300.

Step 2: Divide 300 among four equal claims of 100. By symmetry (or by recursion), each gets 75.

Final: (50, 75, 75, 75, 75). Verify: 50 + 4(75) = 350. ✓

This makes intuitive sense: the first player, peeled off against the coalition, receives less than the others because the coalition's joint claim (400) vastly exceeds hers (100), so the concessions flow overwhelmingly in one direction. The coalition then divides its share equally among its members.

Aumann and Maschler's Theorem C states that the coalitional procedure yields the CG-consistent solution for all bankruptcy problems.[^80] The procedure always terminates, always produces order-preserving results (a higher claim yields a higher award), and always agrees with the direct computation via CEA/CEL on half-claims.

## VI.D. Three Regimes

The Talmud Rule's behavior partitions the estate values into three distinct regimes, each with its own character.

**Small estates (E < smallest claim).** All claimants are far from their half-claim ceilings. CEA on half-claims reduces to pure equal division. Everyone gets E/n. The claims don't matter — the estate is so small that differentiating by claim size feels unjust. The first row of the Ketuboth table lives here.

In our running example (claims 100, 200, 300), the small-estate regime covers E = 0 to E = 100 (the smallest half-claim times 2). In this range, Creditors 1, 2, and 3 all receive E/3. The awards graph shows three overlapping lines rising at the same slope from the origin. There is no visible difference between the creditors — the algorithm treats them as interchangeable.

This behavior has a halakhic resonance. When everyone is losing badly, the differences between claims are morally irrelevant. A creditor owed 100 and a creditor owed 300 are both in the same situation: they're getting a fraction of what they're owed, and that fraction is small. In such circumstances, equality of *outcome* (same dollar amount) trumps equality of *rate* (same percentage of claim). The Mishnah's equal division at E = 100 encodes this moral intuition.

**Large estates (E > sum of claims − smallest claim).** All claimants are close to full satisfaction. CEL on half-claims reduces to approximate equal-loss division. The smallest claimant's loss hits her half-claim ceiling first, and losses equalize among the rest. The third row of the Ketuboth table lives here (E = 300, where losses are 300 total, distributed as 50, 100, 150 — each creditor loses exactly half her claim).

In the large-estate regime (E = 500 to E = 600 in our example), the losses are small and equally shared. At E = 500, everyone loses 33⅓. At E = 550, everyone loses 16⅔. At E = 600, no one loses anything. The awards graph shows three lines converging toward their full claims, all rising at the same slope. The regime is the mirror image of the small-estate regime — just as small estates equalize gains, large estates equalize losses.

The halakhic intuition here is also clear. When the estate is nearly sufficient, the relevant question shifts from "what does each person get?" to "what does each person sacrifice?" And when the sacrifice is small relative to the claims, the moral impulse is to spread it equally. A creditor owed 300 who loses 33⅓ is in essentially the same situation as a creditor owed 100 who loses 33⅓ — both are experiencing a minor shortfall. Equal sacrifice, not proportional sacrifice, feels appropriate.

**The transition zone.** Between these extremes, the interesting structure lives. Claimants hit their half-claim ceilings at different points, creating kinks in the awards graph.

To trace the transitions precisely for claims (100, 200, 300):

- E = 0 to 100: All three receive E/3. Slope: 1/3 each.
- E = 100: Creditor 1 hits half-claim ceiling (50). She freezes.
- E = 100 to 250: Creditors 2 and 3 each receive additional estate equally. Slope for 2 and 3: 1/2 each. Slope for 1: 0.
- E = 250: Creditor 2 hits half-claim ceiling (100). She freezes.
- E = 250 to 300: Only Creditor 3 receives additional estate. Slope for 3: 1. Slopes for 1 and 2: 0.
- E = 300: Boundary. Everyone has exactly their half-claim: (50, 100, 150).

From 300 to 600, the mirror image:

- E = 300 to 350: Only Creditor 3 absorbs loss reductions. Her loss shrinks while others' are still at their half-claim ceilings.
- E = 350: Creditor 2's loss drops below her half-claim. She begins gaining.
- E = 350 to 500: Creditors 2 and 3 gain equally.
- E = 500: Creditor 1's loss drops below her half-claim. She begins gaining.
- E = 500 to 600: All three gain equally.

The graph is piecewise linear, with kinks at E = 100, 250, 300, 350, and 500. These kinks correspond to the points where creditors enter or leave their "frozen" state (at their half-claim ceiling). The overall shape is a series of connected line segments that starts as equal division, gradually differentiates as smaller creditors freeze, reaches maximum differentiation at E = D/2, then gradually re-equalizes as the large-estate regime takes over.

The middle row of the Ketuboth table — E = 200, with its puzzling (50, 75, 75) — sits squarely in this transition zone, between the first and second kinks. Creditor 1 is frozen at her half-claim of 50. Creditors 2 and 3 are sharing the remainder equally. The "puzzle" is simply the behavior of CEA on half-claims at an intermediate estate value.

The three regimes correspond to different moral intuitions about fairness. When there's almost nothing, share equally — the absolute sizes of the claims are irrelevant. When there's almost enough, share the shortfall equally — the claims are the baseline and fairness means equal sacrifice. In between, the transition honors both intuitions simultaneously, with the half-claim serving as the watershed between "thinking about gains" and "thinking about losses."

Aumann and Maschler connect this to the Talmudic principle <span dir="rtl">רובו ככולו</span> — "more than half is like the whole" (Hullin 27a). When you've received more than half your claim, you've crossed a psychological threshold: your mental framing shifts from "I gained x" to "I lost d − x." The Talmud Rule respects this threshold by treating it as the exact point where the algorithm's logic changes.[^81]

---

# Part VII: THE GAME-THEORETIC FOUNDATION

Aumann and Maschler present three independent justifications for the Talmud Rule in Sections 3, 4, and 5 of their paper — CnD-consistency, self-duality with CEA of half-claims, and the coalitional procedure. None of these require game theory. Their fourth justification does: the Talmud Rule is the *nucleolus* of a naturally defined cooperative game. This connection to game theory is not necessary for computing the rule, but it explains *why* the rule has the properties it does.

## VII.A. Cooperative Games

Game theory studies strategic interactions — situations where the outcome depends on the choices of multiple agents. In *non-cooperative* game theory, each agent acts independently, and the focus is on predicting behavior. In *cooperative* game theory, agents can form binding agreements, and the focus shifts to *fairness*: given that the agents will cooperate, how should the fruits of cooperation be divided?

A cooperative game consists of a set of players, a total value to be divided among them, and a *value function* that assigns to every coalition (subset of players) the amount that coalition can guarantee itself, no matter what the other players do.[^82]

The leap from claims problems to cooperative games requires one conceptual step: translating "claims against an estate" into "guaranteed values for coalitions." The translation is natural. A coalition's guaranteed value is the estate minus what all non-coalition members could claim at most — the amount that would remain even if every outsider were paid in full.

The claims problem defines a cooperative game as follows. The players are the creditors. The value to be divided is the estate E. The value function for a coalition S is:

> v(S) = max(E − sum of claims of players NOT in S, 0)

In words: a coalition's guaranteed value is whatever remains of the estate after all *non*-coalition members are paid their full claims. If the non-members' claims eat up the entire estate, the coalition gets nothing.[^83]

**Worked example.** Claims (100, 200, 300), E = 200.

- v({1}) = max(200 − 500, 0) = 0. Creditor 1 alone is guaranteed nothing.
- v({2}) = max(200 − 400, 0) = 0. Neither is Creditor 2.
- v({3}) = max(200 − 300, 0) = 0. Nor Creditor 3.
- v({1,2}) = max(200 − 300, 0) = 0. Even Creditors 1 and 2 together get nothing.
- v({1,3}) = max(200 − 200, 0) = 0. Creditors 1 and 3 together get nothing.
- v({2,3}) = max(200 − 100, 0) = 100. But Creditors 2 and 3 together are guaranteed 100.
- v({1,2,3}) = 200. The grand coalition gets the full estate.

The value function captures how much leverage each coalition has. A coalition of the two larger creditors can guarantee 100 because even after the smallest creditor is paid in full (100), there's still 100 left. No smaller coalition can guarantee anything.

The bankruptcy game has a distinctive shape. Most coalitions have value 0 — they can guarantee nothing because the other creditors' claims eat up the entire estate. Only large coalitions (those whose complement has small enough claims) have positive value. This makes the game "almost zero" from most perspectives, which is why the nucleolus — designed to handle the tensions between coalitions with different guaranteed values — produces such clean results.

**Second value function example: E = 300.**

- v({1}) = max(300 − 500, 0) = 0.
- v({2}) = max(300 − 400, 0) = 0.
- v({3}) = max(300 − 300, 0) = 0.
- v({1,2}) = max(300 − 300, 0) = 0.
- v({1,3}) = max(300 − 200, 0) = 100.
- v({2,3}) = max(300 − 100, 0) = 200.

Now there are two coalitions with positive value: {1,3} and {2,3}. Creditor 3 is in both of them — she's the "key player" whose presence unlocks value for any coalition. This is reflected in her award (150, the highest), but the nucleolus ensures that even the smallest creditor receives a meaningful share (50) despite having no guaranteed value alone.

**Third value function example: E = 100.**

- v({1}) = v({2}) = v({3}) = 0.
- v({1,2}) = max(100 − 300, 0) = 0.
- v({1,3}) = max(100 − 200, 0) = 0.
- v({2,3}) = max(100 − 100, 0) = 0.

Every coalition has value 0. No subset of creditors can guarantee anything, because the remaining creditors' claims always exceed the estate. In this "all zeros" game, the nucleolus assigns equal shares (33⅓ each) — the only allocation that minimizes maximum unhappiness when all coalitions have the same guaranteed value (zero). This is why the Mishnah prescribes equal division for E = 100: the cooperative game is symmetric in a precise sense.

## VII.B. The Nucleolus

Given a cooperative game, the *nucleolus* is the allocation that minimizes the maximum unhappiness of any coalition. The concept was introduced by David Schmeidler in 1969.[^84]

The *excess* of a coalition S under allocation x is e(x, S) = sum of awards to S members − v(S). It measures how much more the coalition is receiving under allocation x than what it could guarantee itself. A low excess means the coalition is close to what it could force — it has reason to complain. A high excess means it's getting more than its guarantee — it's content.

The nucleolus finds the allocation where the smallest excess across all coalitions is as large as possible. It maximizes the minimum satisfaction. If there's a coalition getting barely more than its guarantee, the nucleolus adjusts the allocation to give that coalition more — even at the expense of coalitions that have plenty of excess.[^85]

Think of it as a judge who asks: under this proposed division, which group of creditors would file the loudest complaint? A group that's receiving barely more than its guaranteed value has strong grounds for objecting. The nucleolus finds the division where the loudest complaint is as quiet as possible. Then, among all divisions that minimize the loudest complaint, it finds the one where the second-loudest complaint is as quiet as possible. And so on, working down the hierarchy of grievances until the allocation is fully determined.

This lexicographic minimization of complaints is a powerful fairness concept. It doesn't try to make everyone happy — that's impossible when there isn't enough. It tries to ensure that no group's unhappiness is unnecessarily extreme.

**Worked example.** Claims (100, 200, 300), E = 200. Consider the Mishnah's allocation (50, 75, 75).

| Coalition | v(S) | Award to S | Excess |
|:---:|:---:|:---:|:---:|
| {1} | 0 | 50 | 50 |
| {2} | 0 | 75 | 75 |
| {3} | 0 | 75 | 75 |
| {1,2} | 0 | 125 | 125 |
| {1,3} | 0 | 125 | 125 |
| {2,3} | 100 | 150 | 50 |

The minimum excess is 50, achieved by both {1} and {2,3}. Can we do better — can we find an allocation where the minimum excess exceeds 50?

If we increase Creditor 1's share by some amount δ, {1}'s excess rises to 50 + δ. But Creditors 2 and 3 must lose that δ between them, so {2,3}'s excess falls to 50 − δ. The minimum of the two drops to 50 − δ. Worse. If we decrease Creditor 1's share by δ, {1}'s excess becomes 50 − δ while {2,3}'s rises to 50 + δ. The minimum again drops to 50 − δ. Any perturbation from (50, 75, 75) makes the smallest excess smaller.[^86]

Checking the other coalitions: {2} and {3} have excess 75, and {1,2} and {1,3} have excess 125. The sorted excess vector is (50, 50, 75, 75, 125, 125). This is the lexicographically last such vector — no other allocation produces a sorted excess vector that comes later in lexicographic order. The Mishnah's allocation is the nucleolus.

**A second verification: E = 300.** The Mishnah says (50, 100, 150).

Value function: v({1}) = max(300 − 500, 0) = 0. v({2}) = max(300 − 400, 0) = 0. v({3}) = max(300 − 300, 0) = 0. v({1,2}) = max(300 − 300, 0) = 0. v({1,3}) = max(300 − 200, 0) = 100. v({2,3}) = max(300 − 100, 0) = 200.

| Coalition | v(S) | Award to S | Excess |
|:---:|:---:|:---:|:---:|
| {1} | 0 | 50 | 50 |
| {2} | 0 | 100 | 100 |
| {3} | 0 | 150 | 150 |
| {1,2} | 0 | 150 | 150 |
| {1,3} | 100 | 200 | 100 |
| {2,3} | 200 | 250 | 50 |

Sorted excess vector: (50, 50, 100, 100, 150, 150). The minimum excess is again 50, achieved by {1} and {2,3}. The same balancing act as before: {1}'s excess and {2,3}'s excess are tied at 50, and any perturbation lowers the minimum. The Mishnah's allocation is the nucleolus for this case too.

Notice the pattern: in both cases, the minimum excess equals the smallest claimant's award. This is not coincidence — it follows from the structure of the bankruptcy game. The smallest claimant's coalition {1} has v({1}) = 0 (she can guarantee nothing alone), so her excess equals her award. The complementary coalition {2,3} has v = E − c₁, and its excess equals its award minus (E − c₁). When the allocation is CnD-consistent, these two excesses are equal.

## VII.C. The Talmud Rule Is the Nucleolus

Aumann and Maschler's Theorem D states: for any bankruptcy problem, the CG-consistent solution — the Talmud Rule — equals the nucleolus of the associated cooperative game.[^87]

This is Theorem D of the paper, the culmination of the analysis. The paper presents four theorems:
- Theorem A: each bankruptcy problem has a unique CG-consistent solution (Section 3).
- Theorem B: the CG-consistent solution is the unique self-dual rule applying CEA to half-claims for E ≤ D/2 (Section 4).
- Theorem C: the coalitional procedure yields the CG-consistent solution (Section 5).
- Theorem D: the CG-consistent solution equals the nucleolus (Section 6).

Each theorem provides an independent characterization. Together, they establish that five different approaches — CnD-consistency, self-duality with half-claims, the coalitional procedure, the nucleolus, and the direct CEA/CEL algorithm — all lead to the same unique answer. The Mishnah's numbers sit at the intersection of all five.

This is a deep result. The Talmud Rule was derived from entirely non-game-theoretic reasoning: CnD-consistency, self-duality, CEA of half-claims. The nucleolus was derived from entirely different considerations: minimizing maximum coalition complaints in cooperative games. That they coincide means the Mishnah's numbers are not just consistent with CnD, not just self-dual, not just computable by the coalitional procedure — they are also the unique allocation that minimizes the worst-case grievance of any coalition of creditors.

The coincidence is provable, not coincidental. The CnD-consistency property and the nucleolus's lexicographic minimization are structurally related: both require that no pair of players can improve their joint position by redistributing between themselves. CnD-consistency checks this pairwise; the nucleolus ensures it globally through its optimization criterion.

The proof of Theorem D is the most technically demanding part of the paper. It requires showing that the excess vector of the CG-consistent solution is lexicographically maximal — that no other allocation can reduce the maximum excess further. The key step is showing that the excess of any coalition S is determined by the CnD-consistent awards of its members, and that perturbing any award increases some coalition's excess more than it decreases another's. The details are algebraic, but the intuition is geometric: the CG-consistent solution sits at a "saddle point" where all coalitions' excesses are in equilibrium.

For the reader who wants to see the full proof, Aumann and Maschler's original is concise and self-contained (Section 6, pp. 207–213). Schechter's expository paper provides a gentler approach using Kaminski's glassware construction, where the equilibrium condition becomes literally visible: the liquid level is the same height in every connected pair of vessels.

For the skeptic who found the pairwise CnD argument too simple — too dependent on a particular reading of the Gemara — the nucleolus provides independent confirmation. The Mishnah's numbers are optimal in a precise mathematical sense that the Mishnah's authors could not have articulated but whose consequences they grasped intuitively.

## VII.D. What the Mishnah Could Not Have Known

Aumann and Maschler are explicit: "Of course, it is unlikely that the sages of the Mishna were familiar with the general notion of a coalitional game, to say nothing of the nucleolus."[^88]

The Mishnah does not contain game theory. What it contains is a solution that, two thousand years later, turns out to be the solution that game theory would prescribe. The question is what to make of this.

One reading: the Mishnah's authors had extraordinary intuitions about fairness, and the nucleolus merely formalizes what they already understood informally. They knew that no pair of creditors should be able to improve their position by trading between themselves (CnD-consistency). They knew that gains and losses should be treated symmetrically (self-duality). They knew that the transition between "thinking about what you got" and "thinking about what you lost" occurs at the halfway point. These are moral intuitions, not mathematical ones, and they happen to determine a unique rule.

Another reading: the numbers in the Ketuboth table were not derived from first principles but were received as a tradition, and the Gemara's pairwise CnD analysis was a post-hoc rationalization. This doesn't diminish the result — a tradition that encodes the nucleolus is no less remarkable than one that derives it.

A third reading, perhaps the most honest: we don't know how the Mishnah's authors arrived at these numbers. We know the numbers are correct. We know the Gemara's analysis (CnD-consistency) is sound. We know the result connects to deep structures in mathematics. Whether the Tannaim had a complete algorithm or merely a set of worked examples that they could not generalize — the passage itself supports either interpretation — is a question the text does not settle.

What the text does settle is that the instinct for fairness, developed in the study halls of second-century Palestine, converges with the instinct for fairness developed in the mathematics departments of twentieth-century Jerusalem. The algorithms are different ways of articulating the same moral structure.

There is a parallel to other famous convergences between ancient intuition and modern formalization. Euclid's parallel postulate was an intuition about geometry that turned out to be equivalent to a deep statement about the curvature of space. The Talmud's estate-division intuition turns out to be equivalent to a deep statement about the structure of cooperative games. In both cases, the ancient formulation was not "wrong" or "primitive" — it was a compact encoding of a truth that required entirely different tools to unpack.

Aumann, in his Nobel Prize lecture (2005), returned to the Talmud problem as an example of the power of game-theoretic thinking. The example shows that game theory is not merely a modern invention — its core ideas, about cooperation, fairness, and the resolution of competing claims, are as old as human civilization. The mathematics provides the language; the moral intuitions provide the content. Neither is complete without the other.

---

# Part VIII: OTHER DIVISION PROBLEMS IN RABBINIC LAW

The claims problems of Bava Metzia and Ketuboth are the most algorithmically rich, but they are not the only division problems in rabbinic literature. Across the Talmud and the codes, situations arise where something must be divided and the division is not obvious. Each involves its own constraints, its own moral considerations, and its own algorithmic logic.

What distinguishes these problems from the creditor cases is that each introduces a structural feature the standard claims model lacks. Inheritance introduces asymmetric entitlements (the firstborn's double portion). Land division introduces heterogeneous goods — parcels that differ in quality and cannot be interchanged like coins. Partnership dissolution introduces mixed instruments (part loan, part investment) where the division rule depends on the instrument type. Damage allocation introduces priority classes. And *shuda d'dayanei* introduces the limit case: what happens when the problem's structure is too thin to support any algorithm at all.

Together, these cases map the boundary of algorithmic division in halakha — showing where the formal machinery applies, where it must be adapted, and where it gives way to human judgment.

## VIII.A. Inheritance: The Firstborn's Double Portion

The Torah prescribes that a firstborn son receives a double portion of his father's estate — <span dir="rtl">פי שנים</span>, literally "a mouth of two."[^89] If a man leaves three sons, the firstborn receives 2/4 of the estate and the other two receive 1/4 each. With four sons, the firstborn receives 2/5 and the others 1/5 each. The general rule: with n sons, the firstborn receives 2/(n+1) and each other son receives 1/(n+1).

> **Algorithm: Firstborn Double Portion**
>
> INPUT: Estate E, n sons (first is the firstborn)
>
> 1. Total shares = n + 1 (one extra share for the firstborn)
> 2. Share size = E / (n + 1)
> 3. Firstborn receives 2 × share size
> 4. Each other son receives 1 × share size
>
> OUTPUT: Awards vector
>
> end.

The algorithm is simple, but its interaction with debts creates complexity. The Talmud (Bava Batra 122b–124a) discusses whether the double portion applies to the gross estate or the net estate after debts.[^90] The majority opinion: the firstborn receives a double portion of what the father possessed at the time of death, but debts reduce the estate before the double portion is calculated.

**Worked example.** A father dies with an estate of 600 and three sons. He owes a debt of 300. The distributable estate is 300. The firstborn receives 2/(3+1) × 300 = 150. The other two sons receive 1/4 × 300 = 75 each. Total: 150 + 75 + 75 = 300. ✓

**A more complex example.** The father's estate includes both property he owned at death (<span dir="rtl">מוחזק</span>) and expected future income (<span dir="rtl">ראוי</span>). He owned a house worth 400 and had a debt owed to him worth 200 (not yet collected). He owed debts of 100. Three sons, the eldest being the firstborn.

The Talmud rules that the double portion applies only to <span dir="rtl">מוחזק</span>, not to <span dir="rtl">ראוי</span>. So: distribute the <span dir="rtl">מוחזק</span> estate (400) minus debts (100) = 300 using the double-portion rule. Firstborn gets 150, others get 75 each. Then when the 200 debt is eventually collected, it is divided equally among all three sons (66⅔ each), without a double portion, since it was only <span dir="rtl">ראוי</span> at the time of death.

Final totals: firstborn = 216⅔, others = 141⅔ each. The double portion applies selectively, creating a two-stage division with different rules at each stage.

Maimonides codifies this in Hilkhot Nahalot (Laws of Inheritance), and the Shulchan Aruch addresses it in Choshen Mishpat 277–278.[^91]

The algorithmic interest lies in edge cases.

**Contested firstborn status.** What if two sons each claim to be the firstborn? This is itself a claims problem: two claimants, one double portion. If neither can prove his claim, a version of CnD might apply — the contested double portion (one extra share) is split between them, while the uncontested shares are distributed normally.

**Posthumous assets.** If the father was owed a debt that is collected after his death, does the firstborn get a double portion of it? The Talmud (Bava Batra 124a) rules no: the double portion applies only to assets the father possessed at death (<span dir="rtl">מוחזק</span>), not to future acquisitions (<span dir="rtl">ראוי</span>). This creates a two-tier division: the <span dir="rtl">מוחזק</span> assets are divided with the double portion, while the <span dir="rtl">ראוי</span> assets are divided equally among all sons.

**Debts against the estate.** If the father died owing debts, the debts are paid first, and the double portion applies to the remainder. This ordering matters: paying debts first reduces the estate, which reduces the firstborn's advantage (since his double share is of a smaller base). Some Rishonim debate whether the firstborn should bear a double share of the debts (matching his double inheritance) or an equal share. The majority view, codified by Maimonides: the firstborn bears an equal share of debts, receives a double share of net assets.

The inheritance algorithm, despite its apparent simplicity (just multiply by 2/(n+1) for the firstborn), opens onto a landscape of complexity when combined with debts, contested status, and mixed asset types. Each complication requires a decision about when and how the double-portion rule interacts with other division rules — and each decision reflects a moral judgment about the relationship between privilege and responsibility.

## VIII.B. Land Division and Heterogeneous Goods

The opening chapter of Bava Batra addresses dividing jointly owned property — a courtyard, a garden, a field. Here the problem is not insufficient funds but *heterogeneous goods*: different parts of the property have different values, and the division must be fair despite the asymmetry.[^92]

The Mishnah establishes minimum viable portions — a courtyard, for instance, cannot be divided if each share would be too small to function as a courtyard. Below the minimum, the property must be sold and the proceeds divided.[^93]

When division is possible, the Talmud prescribes two main approaches:

**Expert appraisal** (<span dir="rtl">שומא</span>): appraisers assess the value of different parcels, and the division ensures each party receives equal value, even if the physical areas differ. A party receiving a more desirable parcel compensates the other with a smaller area.[^94]

**Drawing lots** (<span dir="rtl">גורל</span>): when parcels are of equal value, lots determine who gets which piece. This is not an algorithm for *computing* the division but for *implementing* it fairly — ensuring that no party can claim the process was biased. The distinction between computation and implementation is important: the algorithm determines *what* each party receives (equal value); the lots determine *which* specific parcel. The two stages are independent.[^95]

**Cut-and-choose.** The oldest fair-division protocol in human history — "I divide, you choose" — has a natural rabbinic analog. When two partners divide a field, one marks the boundary; the other selects her preferred side. The divider, knowing the chooser will take the better piece, has an incentive to make the division as equal as possible. This protocol guarantees *envy-freeness*: neither party prefers the other's share, because the chooser picked her preferred piece and the divider made the pieces (in her judgment) equal.

**Worked example.** Reuven and Shimon co-own a field. The western half has a well and is worth 600; the eastern half is dry and worth 200. Total value: 800. Fair share: 400 each.

Reuven divides. He marks a boundary so that one parcel includes the well and some surrounding land (worth 400 by his estimate) and the other includes the remaining land (also worth 400 by his estimate). If the western soil is better, Reuven might draw the boundary so the western parcel is physically smaller but includes the well, while the eastern parcel is larger but dry — making both parcels worth 400.

Shimon chooses. If Shimon agrees with Reuven's valuation, either parcel is fine. If Shimon values the well at 700 (because she plans to irrigate), she takes the western parcel, getting what she perceives as 700 in value — more than her fair share. Reuven gets the eastern parcel, worth 400 by his own assessment. Neither envies the other: Reuven divided equally by his lights; Shimon chose her preferred piece.

The protocol works even when the parties disagree about the values of different parcels. Disagreement about values is not a problem — it is the mechanism's engine. The greater the disagreement, the more both parties feel they received more than half.

The Talmud does not use the term "cut-and-choose," but the underlying logic appears in discussions of property division where one party is given the power to divide and the other the power to select. The protocol's game-theoretic properties — that it incentivizes honest division through the strategic structure of the two-stage process — are precisely the properties that modern fair-division theory analyzes.

The Shulchan Aruch (Choshen Mishpat 171–176) codifies detailed rules for partnership dissolution, including scenarios where one partner wants to divide and the other does not, where the property has been improved by one partner's labor, and where the property cannot be physically divided without diminishing its value.[^96]

The Mishnah's minimum-portion rule embodies a principle that recurs across the halakhic treatment of division: division should not be allowed to destroy the utility of the thing being divided. A courtyard too small to be useful is worse than a courtyard held jointly. A Torah scroll cannot be cut in half and distributed. The law recognizes that some goods have minimum viable sizes below which division is harmful, and in those cases it mandates sale (conversion to a homogeneous good — money) followed by monetary division.

This insight — that the type of good constrains the available division algorithms — is remarkably modern. The economic literature distinguishes between *divisible* goods (money, grain) and *indivisible* goods (a house, a car), and between *homogeneous* goods (identical units) and *heterogeneous* goods (parcels of land with different soil quality). Each combination demands different algorithmic tools. The Talmud's treatment of courtyard partition anticipates this taxonomy by asking, before any division: *can this object be meaningfully divided?* Only if the answer is yes does the algorithmic machinery engage.

These problems are structurally different from claims problems. In a claims problem, the estate is homogeneous (money) and the challenge is the claims exceeding the estate. In land division, the estate is heterogeneous and the challenge is ensuring equal value from unequal objects. The algorithmic literature on "fair division" — from Steinhaus's moving-knife procedures to modern envy-free algorithms — addresses precisely this class of problems, and its roots trace directly to the Talmudic discussions of courtyard partition.

## VIII.C. Partnership Dissolution

When partners dissolve a joint venture, the division depends on the terms of the partnership. The Talmud (Bava Metzia 104b–105a) and the Shulchan Aruch (Choshen Mishpat 176–177) distinguish several cases.[^97]

If both partners contributed capital and labor equally, profits and losses are split equally. If capital contributions were unequal, profits are shared in proportion to capital — unless the partners agreed otherwise. If one contributed capital and the other labor (the *iska* arrangement), the default division of profits is 50/50, but the laboring partner is treated as half-borrower and half-custodian of the capital partner's share, creating a hybrid of loan and investment.[^98]

The *iska* arrangement is particularly interesting algorithmically because it nests two division rules: the profits are divided as a partnership, but the capital is treated partly as a loan (with fixed repayment obligation) and partly as an investment (with shared risk). The algorithm for unwinding an *iska* requires determining which portion of the capital was at the laboring partner's risk and which was guaranteed.[^99]

> **Algorithm: Basic Iska Dissolution**
>
> INPUT: Capital C (from investor), Final value V (of the venture)
>
> 1. Half the capital (C/2) is a loan: the laborer owes C/2 regardless of outcome.
> 2. Half the capital (C/2) is an investment: the investor bears the risk.
> 3. Profit on the investment half = max(V/2 − C/2, 0).
> 4. Investor receives: C/2 (loan repayment) + C/2 (investment principal) + Profit/2.
>    Simplified: C + max(V − C, 0)/4 if V ≥ C.
> 5. Laborer receives: V − Investor's share.
>
> OUTPUT: Division of V between investor and laborer.
>
> end.

**Worked example.** An investor provides 1,000 zuz. The laborer runs a business. After one year, the business is worth 1,400.

Under the default *iska* terms:
- Loan half: C/2 = 500. The laborer repays 500 regardless.
- Investment half: C/2 = 500, now worth V/2 = 700. Profit = 200. Split equally: 100 each.
- Investor receives: 500 (loan) + 500 (investment principal) + 100 (half the profit) = 1,100.
- Laborer receives: 1,400 − 1,100 = 300. But wait — the laborer's "half" of the profit is 100, and he repaid the 500 loan, so he netted 300 from the full enterprise, which represents his return on labor.

Now suppose the business lost value: it's worth only 800.
- Loan half: 500 repaid.
- Investment half: C/2 = 500, now worth V/2 = 400. Loss = 100. Borne entirely by the investor (it's his investment risk).
- Investor receives: 500 (loan) + 400 (remaining investment) = 900.
- Laborer receives: 800 − 900 = −100? That can't be right. The laborer can't owe more than the venture is worth.

Here the halakhic structure intervenes: the laborer's obligation on the loan half is a genuine debt, but it cannot exceed what's available. If the venture's total value (800) is less than the loan repayment (500) plus the investment return, the investor absorbs the full shortfall on the investment half and the laborer still owes the full 500 as a loan. But if the venture is worth less than 500, the laborer may not be able to repay even the loan half — and then the *iska* starts to resemble a claims problem, with the investor's claim (1,000 of capital) exceeding the available assets.

The actual halakhic *iska* involves additional complications — the laborer receives a nominal wage for managing the investment half (<span dir="rtl">שכר טרחה</span>), and certain conditions (such as witnesses to the loss) apply to claims of capital loss — but the underlying structure is a layered division: guaranteed repayment first, then shared profit/loss on the remainder. The layering echoes the Ravad's incremental approach and the Talmud Rule's separation of regimes.

## VIII.D. Damages with Insufficient Assets

When a tortfeasor causes damage to multiple parties and lacks sufficient assets to compensate all of them, the Talmud (Bava Kamma 9a) prescribes a division among the injured parties.[^100]

The Shulchan Aruch (Choshen Mishpat 389–390) codifies priority rules: a fine owed to the court takes precedence over compensation owed to individuals. Among individuals, the order of the incidents may matter — earlier victims may have priority over later ones, on the theory that their claim attached to the tortfeasor's assets first.[^101]

Within each priority class, however, the division is proportional to the damages. If two victims are owed 100 and 200 respectively, and only 150 is available (after higher-priority claims), they receive 50 and 100 — in proportion to their damages.

This priority-then-proportional approach differs from the Ketuboth model (which treats all creditors as equal in priority) and from the Bava Metzia model (which is about contested ownership rather than admitted liability). The algorithmic structure is:

> 1. Order claims by priority class.
> 2. Satisfy higher-priority classes fully before proceeding to lower.
> 3. Within each class, divide proportionally.

**Worked example.** A tortfeasor has 200 in assets. She owes:
- 100 to the court (fine for a violation)
- 150 to Victim A (property damage)
- 250 to Victim B (larger property damage)

Priority class 1 (court fine): 100. Fully satisfied from the 200. Remaining: 100.

Priority class 2 (damage to individuals): 150 + 250 = 400 total claims against 100 remaining. Proportional division: Victim A receives (150/400) × 100 = 37.5. Victim B receives (250/400) × 100 = 62.5.

Final awards: Court = 100, Victim A = 37.5, Victim B = 62.5.

If the Talmud Rule were applied to the victims instead: Claims (150, 250), E = 100. D = 400, D/2 = 200. E = 100 ≤ 200, small estate. Half-claims: (75, 125). CEA(100; [75, 125]): equal share = 50. Both half-claims exceed 50. Awards: (50, 50). Equal division — quite different from the proportional (37.5, 62.5).

This comparison illustrates a policy choice embedded in the algorithm selection. The proportional rule says: your share of the shortfall tracks your share of the total damage. The Talmud Rule says: when there's very little to go around, share it equally. The halakhic tradition, by applying proportional division within priority classes for damages, implicitly chooses the proportional-fairness framework over the Talmud Rule in this context.

This is the approach used in modern bankruptcy law as well — secured creditors first, then unsecured, then equity holders — with proportional division within each tier. The rabbinic innovation is in the specifics of priority ordering and in the edge cases where priority is itself disputed.

## VIII.E. Shuda D'Dayanei: When No Algorithm Applies

Sometimes the Talmud reaches the boundary of algorithmic thinking and acknowledges it explicitly. <span dir="rtl">שודא דדייני</span> — "the judge's assessment" — is the halakhic mechanism for cases where no rule can determine the correct division.[^102]

The classic case is Ketuboth 94a: a man sells or gives the same field to two different people on the same day, and the deeds bear the same date with no indication of which transaction came first. There is no algorithm that can determine priority because the relevant information (which transaction occurred first) does not exist in the record.

The Talmud's solution: <span dir="rtl">שודא דדייני</span>. The judge uses his discretion — his assessment of the circumstances, the parties' characters, the surrounding evidence — to award the field to one party or the other. There is no formula. The judge decides.[^103]

A similar principle applies in Bava Batra 35a, where two people claim the same field and neither can prove ownership. The Talmud considers various allocation methods but ultimately invokes *shuda d'dayanei* as a fallback.

There are two interpretations of *shuda d'dayanei* in the Rishonim. Rashi understands it as pure judicial discretion — the judge decides based on his overall assessment, without being bound by any formula. Tosafot understand it differently: the judge assesses which party is more likely to be the true owner, based on circumstantial evidence that doesn't rise to the level of legal proof. On Rashi's view, *shuda* is subjective; on Tosafot's view, it is a form of probabilistic reasoning that falls short of certainty.

The difference matters for our analysis. If *shuda* is pure discretion (Rashi), then it represents a genuine exit from algorithmic thinking — the judge is doing something that no algorithm can replicate because it depends on factors that cannot be formalized. If *shuda* is probabilistic assessment (Tosafot), then it represents a different *kind* of algorithm — one that processes soft evidence rather than hard claims — and it might in principle be formalized, even if the formalization is complex.

The Shulchan Aruch (Choshen Mishpat 138) preserves this escape valve alongside the algorithmic rules. The codification recognizes a boundary: algorithms handle cases where the relevant information is known and the structure of the problem fits a recognized pattern. Outside that boundary — when the information is missing, when the competing claims don't map onto a standard claims problem, when the circumstances are genuinely unique — human judgment takes over.[^104]

This is not a failure of the algorithmic framework. It is its honest acknowledgment of scope. Every computational system has inputs it cannot process and edge cases it cannot resolve. The halakha's willingness to say "here, the judge decides" is the ancient equivalent of a well-designed system's exception handler: it catches what the algorithms cannot and routes it to a human intelligence that can weigh factors no formula captures.

---

# Part IX: THE MODERN CONVERSATION

The Aumann-Maschler paper opened a channel between Talmudic scholarship and mathematical economics that has remained productive for four decades. Published in 1985, the paper was cited in Aumann's Nobel Prize citation twenty years later. It inspired a generation of researchers to explore the axiomatic foundations of division rules, and it established the Talmudic claims problems as canonical examples in the economics literature — alongside Arrow's impossibility theorem and Nash's bargaining solution — of ancient fairness problems that admit precise mathematical analysis.

The modern literature on claims problems — sometimes called "bankruptcy problems" or "rationing problems" — is now vast, with characterization theorems, alternative axiomatizations, and connections to practical allocation problems. Thomson's 2019 monograph alone contains over 500 references, and the literature continues to grow.

## IX.A. Thomson's Axiomatics

William Thomson's comprehensive monograph *How to Divide When There Isn't Enough* (2019) provides the definitive axiomatic treatment of claims problems.[^105] Thomson catalogs dozens of division rules and characterizes each by the combinations of properties it satisfies.

A *characterization theorem* says: if a rule satisfies properties A, B, and C, then it must be rule X — and no other rule satisfies all three. This is powerful because it reduces the choice of rule to the choice of axioms. You don't need to evaluate every possible algorithm; you only need to decide which properties fairness requires.

Thomson's key characterizations include:

**CEA** is the unique rule satisfying equal treatment of equals, consistency, and composition from minimal rights — the property that first giving each claimant the minimum they could guarantee and then reapplying the rule to the remainder produces the same answer as applying the rule once.[^106]

**CEL** is the unique rule satisfying equal treatment of equals, consistency, and composition — the property that dividing part of the estate, distributing it, reducing claims by the amounts received, and then dividing the remainder produces the same total as dividing the full estate at once.[^107]

**The Proportional Rule** is the unique rule satisfying equal treatment of equals, consistency, and no advantageous transfer — the property that no group of claimants can benefit by redistributing their claims among themselves.[^108]

**The Talmud Rule** is characterized by Aumann and Maschler's Theorem B: it is the unique self-dual rule that assigns CEA of half-claims when E ≤ D/2. Thomson provides additional characterizations involving the half-claim property and CnD-consistency.[^109]

Each characterization theorem reveals what you're committing to when you choose a rule. Choosing CEA means committing to composition from minimal rights — a specific view about what happens when a small amount is distributed first. Choosing the Proportional Rule means committing to no advantageous transfer — no gaming through claim restructuring. The axioms make the moral commitments explicit.

The power of this approach is that it replaces "which rule feels fair?" with "which properties does fairness require?" The first question is subjective and context-dependent. The second is precise and debatable. If you can agree on the properties, the mathematics determines the rule — there's no room for further disagreement.

Thomson catalogs these properties with extraordinary thoroughness. His monograph identifies more than fifty distinct properties and maps which combinations characterize which rules. Some properties are logically independent; others are implied by combinations of others. The landscape is intricate, but the main roads are clear:

- CEA and CEL are duals of each other under every characterization. Every property that characterizes CEA has a dual property that characterizes CEL.
- The Proportional Rule is the only rule that is self-consistent (consistent with itself), self-dual, and satisfies no advantageous transfer simultaneously.
- The Talmud Rule is the only rule that is self-dual, CnD-consistent, and resource-monotonic.

These characterizations don't settle which rule a court should use — that remains a moral judgment. But they make the consequences of each moral choice mathematically precise.

## IX.B. Dagan's Alternative Characterizations

Nir Dagan developed alternative characterizations of the classical rules by focusing on independence properties — the conditions under which a rule's recommendations don't change when certain parameters shift.[^110]

Dagan shows that the Talmud Rule can be characterized by a property he calls *independence of irrelevant claims*: if a claimant's claim exceeds the estate, reducing that claim to the estate level doesn't change anyone's award. The intuition is natural — a creditor claiming more than the entire estate might as well claim exactly the estate; the excess is meaningless.

**Worked example.** Claims (100, 200, 5000), E = 300. Creditor 3 claims 5,000, but the entire estate is only 300. Under independence of irrelevant claims, replacing Creditor 3's claim with 300 (the estate) shouldn't change any awards.

Talmud Rule with claims (100, 200, 5000), E = 300: D = 5300, D/2 = 2650. E < D/2. Half-claims: (50, 100, 2500). CEA(300; [50, 100, 2500]): equal share = 100. Creditor 1 capped at 50. Remaining: 250 between 2 claimants. Equal share: 125. Creditor 2 capped at 100. Remaining: 150 to Creditor 3. Awards: (50, 100, 150).

Now with claims (100, 200, 300), E = 300: D = 600, D/2 = 300. E = D/2. Half-claims: (50, 100, 150). CEA(300; [50, 100, 150]): everyone gets their full half-claim: (50, 100, 150). Same awards!

The property holds: Creditor 3's claim could be 5,000 or 300 or any number ≥ 300, and the awards are the same. The excess claim is irrelevant. Combined with CnD-consistency, this property pins down the Talmud Rule uniquely.[^111]

Dagan also provides characterizations of CEA and CEL using different independence conditions:

- CEA satisfies *independence of claims above the equal share*: if a claimant's claim exceeds the equal share of the estate, increasing it further doesn't change any awards.
- CEL satisfies the dual: *independence of claims below the equal loss*.

These characterizations map the landscape of rules more finely than Thomson's property-combination approach. His work shows that the rabbinic algorithms are not just historically interesting but occupy distinguished positions in the space of all possible division rules — they are the natural solutions under different, clearly articulable fairness criteria.

## IX.C. Balinski's "What Is Just?"

Michel Balinski's 2005 paper "What Is Just?" in the *American Mathematical Monthly* approaches the problem from an explicitly philosophical angle.[^112] The title itself is significant — it's the question Aristotle asked in the *Nicomachean Ethics*, the question the Mishnah answers through worked examples, and the question that the axiomatic literature sometimes obscures through formalism.

Balinski's contribution is to shift the focus from axiomatic characterization to *justification*: given that multiple rules satisfy reasonable-sounding axioms, on what grounds should a society choose one over another? Characterization theorems tell you that if you want properties A, B, and C, you must use rule X. But they don't tell you *why* you should want properties A, B, and C. His answer involves a meta-level analysis of what the axioms themselves presuppose about the nature of claims and the meaning of fairness.

For instance: the proportional rule treats claims as *measures of entitlement*. A claim of 200 is twice as strong as a claim of 100 in the sense that it should receive twice as much. CEA treats claims as *ceilings on need*: once your need is met, additional funds flow elsewhere. CEL treats claims as *measures of sacrifice*: fairness means equal loss relative to entitlement.

The Talmud Rule, in Balinski's framing, combines these perspectives by using the half-claim as the switchover point. Below the half-claim, a creditor's situation is described by what she has gained. Above it, by what she has lost. The rule respects both framings without privileging either, and the transition is smooth because it occurs at the midpoint of each creditor's claim — the point of maximum symmetry.

Balinski also discusses the *practical plausibility* of different rules. The Proportional Rule is easy to explain and implement — anyone with a calculator can compute proportional shares. CEA requires an iterative procedure (cap at claim, redistribute, repeat) that is slightly more complex. The Talmud Rule requires computing half-claims and knowing which regime (small or large estate) applies, which adds another layer. In a world where legal rules must be applied by real judges in real time, computational simplicity matters. The Proportional Rule's dominance in secular law may owe as much to its computational transparency as to its moral appeal.

The Talmud Rule's computational cost is modest — O(n log n) for sorting claims, then a single pass — but its *conceptual* cost is higher. Explaining to a litigant that she receives CEA of half-claims because the estate is below the halfway point requires more scaffolding than explaining that she receives a proportional share. Whether this conceptual complexity is a barrier or a feature depends on your view of legal education.

Balinski's philosophical grounding connects the rabbinic discussion to contemporary debates about distributive justice: how should a society allocate scarce healthcare resources, educational opportunities, or disaster relief? The rules developed for dividing Talmudic estates turn out to be the same rules economists and political scientists propose for these modern problems.

## IX.D. Connections Forward

The claims problem is not a historical curiosity. It is a living mathematical structure that appears wherever demand exceeds supply and the excess must be rationed fairly.

**Healthcare allocation.** When a hospital has limited ICU beds or organ transplants, the question of who receives what is a claims problem with the additional constraint that claims may not be purely monetary — severity of illness, likelihood of benefit, and time on the waiting list all function as "claims" of different types.

During the COVID-19 pandemic, hospitals around the world faced exactly this problem: limited ventilators, many patients, not enough for everyone. The triage protocols that were developed — and the ethical frameworks that justified them — recapitulate the same debates the Rishonim had about the Ketuboth table. Should ventilators go to the sickest patients (a severity-based claim, analogous to a large monetary claim)? To those with the best prognosis (a likelihood-of-benefit claim, which has no direct Talmudic analog but corresponds to the epistemic quality the Ketzos analyzes)? Equally to all (the CEA/small-estate approach)? To those who waited longest (a temporal priority system, like the Shulchan Aruch's creditor ordering)?

**A concrete allocation.** A hospital has 10 ventilators. Three wards have requested them: Ward A needs 5, Ward B needs 8, Ward C needs 12. Total demand: 25.

Under CEA: equal share = 3⅓, all needs exceed this. Awards: (3⅓, 3⅓, 3⅓). Every ward gets the same — roughly 3 ventilators each. Ward C, with the most critically ill patients, gets the same as Ward A with fewer.

Under proportional: A gets (5/25) × 10 = 2, B gets (8/25) × 10 = 3.2, C gets (12/25) × 10 = 4.8. The ward with the most patients receives the most ventilators, but not proportionally to its need — it still falls far short.

Under the Talmud Rule: D = 25, D/2 = 12.5, E = 10 < 12.5. Half-claims: (2.5, 4, 6). CEA(10; [2.5, 4, 6]): equal share = 3⅓. Ward A capped at 2.5. Remaining 7.5 between B and C. Equal share = 3.75. Both exceed 3.75. Awards: (2.5, 3.75, 3.75). Ward A, whose need is smallest, gets slightly less; the other two wards share the remainder equally.

Each rule encodes a different moral logic. The choice between them is not mathematical — it is ethical. The axiomatic framework developed for bankruptcy problems directly informs the design of such allocation protocols.[^113]

**Network bandwidth.** When multiple users share a limited communication channel, the division of bandwidth among them is a claims problem. Each user has a maximum capacity (their claim) and the total available bandwidth (the estate) is insufficient.

This is not an analogy — it is literally the same mathematical problem. Network engineers use the term "max-min fairness" for a bandwidth allocation that equalizes each user's allocation, subject to the constraint that no user gets more than their capacity. Max-min fairness *is* CEA. The term "proportional fairness" refers to allocating bandwidth in proportion to some weight (typically the claim). The debate between max-min fairness and proportional fairness in network engineering is, structurally, the debate between CEA and the Proportional Rule in claims theory — which is, in turn, the debate between Maimonides and Aristotle on how to divide an insufficient estate.

The proportional rule is commonly used for its mathematical properties (it maximizes the product of utilities), but CEA-like rules have better properties in some network architectures, particularly when the goal is to guarantee minimum service to all users.[^114]

**Environmental resource allocation.** Dividing fishing quotas, carbon emission permits, or water rights among competing users with different historical usage levels is structurally identical to dividing an estate among creditors with different claims. The axiomatic analysis of which properties a fair division should satisfy carries over directly.[^115]

**Algorithmic fairness.** The contemporary field of algorithmic fairness — designing systems that allocate resources (loans, housing, jobs) without bias — draws on the same axiomatic toolkit. Properties like consistency, population monotonicity, and equal treatment of equals are directly relevant to ensuring that automated allocation systems behave justly.[^116]

**Disaster relief.** When an earthquake strikes and multiple cities need aid, the total available aid (the estate) rarely covers the total need (the claims). How should it be distributed? The intuition behind the Talmud Rule — equal shares when everyone is far from satisfaction, proportional-like division as satisfaction approaches — mirrors the standard practice of distributing emergency supplies: equal distribution in the acute phase, needs-proportional distribution as recovery proceeds.

**International climate agreements.** Carbon emission reduction targets face the same structure: a total reduction target (the "estate" of permitted emissions) must be divided among nations with different economic needs (their "claims"). Developing nations argue for equal per-capita shares (a CEA-like logic: everyone gets the same, capped at their need). Developed nations sometimes argue for proportional reduction from current levels (a CEL-like logic: everyone takes an equal percentage cut). The Talmud Rule's synthesis — equalizing gains for small allocations, equalizing losses for large ones — offers a structural compromise that neither side has yet considered.

**A sketch of the problem.** Suppose three countries must share 100 units of permitted carbon emissions. Country A's economy requires 30, Country B requires 80, Country C requires 150. Total demand: 260. The "estate" of 100 permitted units must be divided.

Under CEA: equal allocation = 33⅓. Country A is capped at 30 (its need). Remaining 70 split between B and C: 35 each. Awards: (30, 35, 35). Every country gets a livable allocation, but Country C — the largest economy, needing the most — receives only 35 out of 150.

Under CEL: total cut = 160. Equal cut = 53⅓. Country A's claim (30) < 53⅓, so A gets 0. Remaining 100 between B and C with equal loss from 230: each loses 65. Awards: (0, 15, 85). Country A is shut down entirely. Country C, as the largest emitter, keeps most of its allocation.

Under the Talmud Rule: D = 260, D/2 = 130, E = 100 < 130. Half-claims: (15, 40, 75). CEA(100; [15, 40, 75]): equal share = 33⅓. A capped at 15. Remaining 85 between B and C: 42.5 each. B capped at 40. Remaining 45 to C. Awards: (15, 40, 45). Every country receives a meaningful allocation. The distribution is moderate — more egalitarian than CEL but less than CEA.

The moral content of each rule is visible in the numbers. CEL says: large emitters have earned their emissions through economic development and should keep most of them. CEA says: every country has an equal right to a livable portion. The Talmud Rule says: start from equal entitlement, but respect the structure of the claims as they diverge. The framework developed for Talmudic estates provides not the answer to climate negotiations, but a precise vocabulary for articulating what is at stake in the choice.

The thread that connects Mishnah Bava Metzia to contemporary resource allocation runs through two thousand years of legal reasoning and a century of mathematical economics. The problems change — garments become bandwidth, estates become organ transplant lists — but the underlying question remains: when there isn't enough, what does fairness require?

---

# Part X: SYNTHESIS AND REFLECTION

## X.A. A Map of the Algorithms

Twenty algorithms have appeared in this manuscript, spanning from the biblical period to the late twentieth century. Here they are, mapped together:

| # | Algorithm | Primary Source | Period | Ketuboth Match |
|:---|:---|:---|:---|:---:|
| 1 | Equal Division | Mishnah BM 1:1 (case 1) | Tannaitic | Row 1 only |
| 2 | Concede and Divide | Rashi on BT BM 2a | Rishonic | 2-person only |
| 3 | Rabbi Natan's Pairwise Decomposition | BT Ketuboth 93a | Amoraic | Verification, not generation |
| 4 | Constrained Equal Awards (CEA) | Maimonides, Hilkhot MLvL 20:4 | Rishonic | Row 1 only |
| 5 | Constrained Equal Losses (CEL) | Maimonides, Hilkhot Erkhei HaKdesh 8:4 | Rishonic | None |
| 6 | Proportional Rule | Aristotle; various Talmudic contexts | Classical | Row 3 only |
| 7 | Ravad's Layered Equal Division | Ravad on Rif, Ketuboth 51a | Rishonic | = CEA |
| 8 | Ravad's Bidding Rule | Ravad on Maimonides MLvL 20:4 | Rishonic | Dual of CEA |
| 9 | Piniles' Rule | *Darkah Shel Torah* (1863) | Acharonic | All 3 rows |
| 10 | Run on the Bank | O'Neill; Young | Modern | 2-person only |
| 11 | Shapley Value | Shapley (1953) | Modern | Fails consistency |
| 12 | Ibn Ezra's Layered Cost-Sharing | Ibn Ezra on Torah | Rishonic | ≈ CEA |
| 13 | Ketzos HaChoshen framework | Ketzos, Siman 138 | Acharonic | Modifies CnD |
| 14 | Netivot HaMishpat alternative | Netivot, Siman 138 | Acharonic | Pre-algorithmic |
| 15 | Talmud Rule (Aumann-Maschler) | Aumann & Maschler (1985) | Modern | All 3 rows ✓ |
| 16 | Nucleolus | Schmeidler (1969) | Modern | = Talmud Rule |
| 17 | Firstborn Double Portion | Deut 21:17; BT BB 122b | Biblical/Tannaitic | Different problem |
| 18 | SA Creditor Priority | SA CM 104–105 | Acharonic | Different problem |
| 19 | Partnership Dissolution | SA CM 176–177 | Acharonic | Different problem |
| 20 | Shuda D'Dayanei | BT Ketuboth 94a; BT BB 35a | Amoraic | Non-algorithmic |

Several patterns emerge from this table.

The first: the Tannaim and Amoraim had the right instincts but not the right tools. The numbers in the Ketuboth table are correct — they are the nucleolus, they are CnD-consistent, they are self-dual — but the general algorithm for producing them from arbitrary inputs was not articulated. The Rishonim struggled to extract the general rule from the specific examples and could not do so.

The second: Piniles came remarkably close in 1863, matching all three Ketuboth rows. His failure was at the boundaries — the Bava Metzia garment cases and large estates — where his rule's lack of self-duality manifests. Piniles was a Lithuanian maskil (Jewish enlightenment scholar) who combined Talmudic erudition with mathematical curiosity — a profile similar to the authors of this manuscript's sources. That he got so close using purely literary-mathematical analysis, without the tools of cooperative game theory, is a testament to the power of careful observation.

The third: the modern algorithms (Talmud Rule, Nucleolus) are not new rules imposed from outside the tradition. They are formalizations of principles the tradition already contained — CnD-consistency, the <span dir="rtl">רובו ככולו</span> threshold, the coalitional reasoning of the Jerusalem Talmud. The mathematics did not change the tradition's answer; it explained it.

The fourth: the algorithms cluster by period in revealing ways. The Tannaitic period produced specific cases (Bava Metzia, Ketuboth) — worked examples without general rules. The Amoraic period produced the key insight (CnD-consistency) and the coalitional intuition (Samuel in the Jerusalem Talmud) — the verification framework without the generalization. The Rishonic period produced the component algorithms (CEA, CEL, Ravad's layered rules) — building blocks without the assembly. The Acharonic period produced the closest predecessor (Piniles) and the deepest analysis of boundary cases (Ketzos/Netivot). And the modern period finally assembled the pieces.

Each period contributed something essential. No single period could have solved the problem alone. The Tannaim gave the numbers. The Amoraim gave the consistency principle. The Rishonim gave the building blocks. The Acharonim refined the edge cases. The economists gave the unifying framework. The problem required all of it.

## X.B. What the Tradition Teaches About Fairness

The multiplicity of algorithms in the rabbinic tradition encodes a deep insight: "fairness" is not a single concept. Different circumstances call for different rules, and the choice between them is a moral decision, not a technical one.

Consider a small community with three families and a limited tzedakah fund. The fund has 100. Family A needs 100, Family B needs 200, Family C needs 300. How should the fund be distributed?

If you think the priority is to help as many families as possible get closer to stability, you lean toward CEA — equal shares capped at need. Everyone gets 33⅓. No family is fully helped, but no family is abandoned.

If you think the priority is to minimize the worst outcome — to ensure no family falls below a survivable floor — you might lean toward a different calculation entirely, one that factors in the current resources each family already has. The claims problem assumes need is fully captured by the claim; real life is messier.

If you think the priority is to honor the fact that some families face larger shortfalls and should receive proportionally more help, you lean toward proportional division. Family C, which needs three times as much as Family A, would receive three times as much from the fund.

The Talmud Rule offers a fourth perspective: when the fund is small relative to total need, treat everyone equally — the differences in need are swamped by the shared desperation. When the fund is large relative to total need, let the differences in need drive the allocation — equality of sacrifice rather than equality of benefit. The transition between these regimes happens smoothly, with the half-need as the watershed.

Each of these is a defensible moral position. The rabbinic tradition's contribution is not to declare one of them correct but to make the options explicit and to develop the algorithmic machinery for implementing each one precisely.

The tradition's pluralism is visible in the codes. The Shulchan Aruch doesn't prescribe the Talmud Rule for all situations. It prescribes CnD for the contested garment (CM 138), proportional division for certain creditor disputes, priority-based division for others, and judicial discretion for the unresolvable cases. The Rema, Sma, and Shach add further nuances — conditions under which one rule applies rather than another, edge cases where the rules interact, situations where custom (<span dir="rtl">מנהג</span>) overrides the default.

This pluralism is sometimes read as inconsistency — as if the tradition should have settled on one rule. But the modern axiomatic analysis vindicates the pluralism. Each rule is the *unique* solution satisfying a specific set of fairness properties. Different situations invoke different fairness properties. The contested garment, where both claimants hold the garment and the dispute is about ownership, naturally invokes CnD-consistency — the principle that what you don't claim, you concede. Creditor bankruptcy, where all debts are valid but the estate is insufficient, might reasonably invoke proportional fairness — each dollar of debt treated equally. Partnership dissolution, where the partners' contributions and expectations are known, naturally invokes the terms of the partnership agreement.

The tradition's map of "which rule for which situation" is not arbitrary. It reflects an implicit understanding that different contexts activate different moral intuitions, and the algorithmic framework should respect those differences rather than flatten them into a single formula.

Equal division makes sense when everyone is suffering equally — when the estate is so small that the differences between claims are swamped by the shared inadequacy of the resource. This is the intuition of the first row of the Ketuboth table. It is also the intuition behind many emergency allocation protocols: when disaster strikes, distribute relief equally, regardless of prior entitlements.

Proportional division makes sense when the claims are seen as measures of prior entitlement — when the question is "what fraction of what you're owed can we honor?" This is the default in secular bankruptcy law and reflects a commitment to treating each dollar of debt identically.

The Talmud Rule makes sense when you believe that fairness requires a psychological realism: that the same division should look fair whether you frame it as "what did I get?" or "what did I lose?", and that the natural dividing line between these frames is the midpoint of each person's claim.

The tradition does not insist on one answer. It provides a family of algorithms, each with its own moral logic, and reserves the choice of rule for the decision-maker who understands the specific circumstances. The Shulchan Aruch's pluralistic codification — different rules for different situations — is a feature, not a bug. It reflects the understanding that fairness is contextual and that no single algorithm captures every dimension of justice.

The convergence of the Talmud Rule with the nucleolus is, in this light, a remarkable fact but not a prescriptive one. It tells us that the Mishnah's specific numbers for the Ketuboth problem are mathematically optimal in a precise sense. It does not tell us that all division problems should be solved the same way. The tradition's wisdom is in recognizing both the power and the limits of algorithmic thinking — in developing algorithms where they apply and in reserving *shuda d'dayanei* for where they don't.

## X.C. Open Questions

Several questions remain open or under-explored.

**Computational complexity.** The Talmud Rule can be computed in O(n log n) time for n claimants (sort the claims, then iterate through the CEA/CEL computation). The nucleolus, in general cooperative games, requires solving a sequence of linear programs and has much higher complexity. That the two coincide for bankruptcy games means the nucleolus can be computed efficiently in this special case — but are there other classes of cooperative games where Talmudic-style reasoning yields efficient nucleolus computation?[^117]

**Incomplete information.** The standard claims problem assumes all claims are known and verified. The Ketzos-Netivot debate suggests that the tradition takes epistemic quality seriously — *bari* versus *shema* claims receive different treatment. A formal model that incorporates claim uncertainty into the axiomatic framework could bridge the halakhic literature on evidence with the mathematical literature on mechanism design.[^118]

**Dynamic estates.** The standard model is static: the estate has a fixed value. But many real-world situations involve estates that change over time — businesses whose value fluctuates, natural resources that renew. How should a division rule adapt when the estate is growing or shrinking between the time claims are filed and the time division occurs? The halakhic literature on *kinyan* (acquisition) and the changing value of property may offer insights.[^119]

**Multi-dimensional claims.** In the Talmudic model, claims and the estate are measured in the same units (money). In many modern problems, claims are multi-dimensional: a patient needs both an organ and post-operative care; a student needs both admission and financial aid. Extending the axiomatic framework to multi-dimensional claims problems is an active area of research.[^120]

**Weighted claims.** The standard model treats all claims as having equal legal weight. But in halakhic practice, some claims carry more weight than others — a secured creditor has a lien on specific property; an earlier debt may take precedence over a later one; a debt incurred through *kinyan* (formal acquisition) is stronger than a verbal promise. How should weights be incorporated into the axiomatic framework? Thomson discusses weighted rules briefly, but the halakhic literature's rich taxonomy of claim types — <span dir="rtl">שטר</span> vs. <span dir="rtl">מלוה על פה</span>, <span dir="rtl">שעבוד קרקעות</span> vs. <span dir="rtl">מטלטלין</span> — suggests a much richer structure waiting to be formalized.

**The pedagogy of fairness.** The Talmud's method — presenting specific cases with specific numbers, inviting the student to find the pattern, only then revealing the general principle — is a pedagogical strategy, not just an expository one. The worked examples in Bava Metzia and Ketuboth are designed to develop moral intuition before formal rules. Whether this approach transfers to modern settings — teaching algorithmic fairness through cases rather than axioms — is an open question in both education and ethics.

**The missing middle row.** Across two millennia, the first and third rows of the Ketuboth table were always more or less understandable. Equal division for E = 100; something close to proportional for E = 300. The mystery was always E = 200. The persistence of this specific puzzle — that the middle case is the hard one — reflects a general principle: the behavior of any system is most interesting at intermediate values, where competing regimes interact and neither dominates. The Talmud Rule's beauty lies precisely in its treatment of the transition zone, where CEA's logic and CEL's logic overlap and must be reconciled. This is where the half-claim does its work, and this is where the algorithm's moral structure is most visible.

The Ketuboth table was hidden in plain sight for two thousand years. Three rows of numbers, six entries each, all correct, all consistent, all derivable from a single principle that no one could state. When Aumann and Maschler finally stated it — when they wrote down the rule that stitches CEA and CEL together through the half-claims — they didn't invent something new. They translated something old into a language that could finally hold it.

The manuscript you've just read traces a single thread from a garment in a courtroom to the nucleolus of a cooperative game, through medieval commentaries, Acharonic responsa, Lithuanian scholarship, and Israeli mathematics departments. The thread is the question: when there isn't enough, how should we divide what there is?

Twenty algorithms later, the answer is: it depends on what you value. If you value equal treatment of pain, use CEA. If you value equal treatment of sacrifice, use CEL. If you value proportionality, use the Proportional Rule. If you value consistency — the principle that any two people, looking at their combined share, should be able to justify it by the same rule that justified the whole — use the Talmud Rule.

The Mishnah chose consistency. And twenty centuries later, the mathematics proved it right.

There is a final reflection worth making. The problem we've traced — dividing disputed property — is, at its core, a problem about living together. It arises whenever people share a world with limited resources. The garment is a metaphor: two people, one thing, not enough. Every family, every community, every society faces versions of this problem daily.

The tradition's response was not to impose a single answer but to develop a family of answers, each suited to its circumstances, and to subject each answer to rigorous scrutiny — testing it against worked examples, checking it for consistency, comparing it with alternatives, debating its foundations. The mathematical formalization that came two millennia later is a continuation of this tradition, not a departure from it. Aumann and Maschler did what the Rishonim did — they tested, checked, compared, and debated — only with different tools.

The twenty algorithms cataloged in this manuscript are twenty attempts to answer the same question: what does fairness demand? They disagree on specifics. They agree that the question matters, that the answer should be precise, and that a good answer should withstand scrutiny from every angle. That convergence — between ancient law and modern mathematics, between moral intuition and formal proof, between the study hall and the seminar room — is the deepest lesson of the disputed property.

---

# Glossary

**Awards vector.** The list of amounts allocated to each claimant in a division. Must be non-negative, bounded by claims, and sum to the estate.

**Bari** (<span dir="rtl">ברי</span>). A claim of certainty — the claimant asserts definite knowledge. Contrasted with *shema*.

**CEA (Constrained Equal Awards).** A division rule that gives each claimant the same amount, capped at their claim. Proposed by Maimonides for creditor division.

**CEL (Constrained Equal Losses).** A division rule that imposes equal losses on each claimant, floored at zero. The dual of CEA.

**Claims problem.** A triple consisting of an estate E, a vector of claims (c₁, ..., cₙ), and the condition that total claims exceed E.

**CnD (Concede and Divide).** A two-person division rule: give each side what the other concedes, split the contested remainder equally. Attributed to Rashi on BM 2a.

**CnD-consistency (CG-consistency).** A property of n-person division rules: any two claimants, dividing their combined award using CnD, recover their individual awards.

**Coalition.** A subset of players in a cooperative game. The coalition's value is what it can guarantee itself regardless of the other players' actions.

**Consistency.** A property of a division rule: paying off a claimant and reapplying the rule to the rest leaves everyone else's award unchanged.

**Duality.** The relationship between dividing what's there and dividing what's missing. The dual of rule f divides losses the way f divides gains.

**Estate (E).** The total resource available for division. In the Talmudic context, the deceased's assets; more generally, any scarce resource.

**Excess.** In cooperative game theory, the difference between a coalition's allocation and its guaranteed value. High excess means the coalition is content; low excess means it has a grievance.

**Geonim.** The heads of the Babylonian academies in the post-Talmudic period (roughly 589–1038 CE). Singular: Gaon.

**Iska** (<span dir="rtl">עסקא</span>). A hybrid investment-and-loan arrangement in which profits are shared but capital is partially guaranteed. Codified in SA CM 177.

**Migo** (<span dir="rtl">מיגו</span>). An evidentiary principle: a claimant who could have made a stronger claim but made a weaker one is presumed honest.

**Nucleolus.** The allocation in a cooperative game that minimizes the maximum unhappiness of any coalition. Introduced by Schmeidler (1969). Equals the Talmud Rule for bankruptcy games.

**Resource monotonicity.** A property: increasing the estate (with claims fixed) never decreases any claimant's award.

**Rishonim** (<span dir="rtl">ראשונים</span>). The leading rabbinic authorities of the medieval period (roughly 1000–1500 CE). Singular: Rishon.

**Self-duality.** A property of a division rule: it produces the same awards whether one thinks of dividing gains or dividing losses.

**Shema** (<span dir="rtl">שמא</span>). A claim of uncertainty — the claimant says "perhaps." Contrasted with *bari*.

**Shuda d'dayanei** (<span dir="rtl">שודא דדייני</span>). Judicial discretion applied when no algorithmic rule can determine the outcome. The halakhic boundary of algorithmic thinking.

**Shuma** (<span dir="rtl">שומא</span>). Expert appraisal of property value, used in land division cases.

**Acharonim** (<span dir="rtl">אחרונים</span>). The later rabbinic authorities, from the publication of the Shulchan Aruch (1563) onward. Singular: Acharon.

**Bankruptcy game.** A cooperative game derived from a claims problem, where each coalition's value is the estate minus the total claims of non-members (floored at zero). The nucleolus of this game equals the Talmud Rule.

**Claims monotonicity.** A property: increasing one claimant's claim (all else equal) never decreases that claimant's award.

**Envy-freeness.** A fairness property in which no party prefers another party's allocation to their own. Central to land division and heterogeneous goods problems.

**Half-claim.** Half of a claimant's stated claim (cᵢ/2). The Talmud Rule uses half-claims as inputs to CEA or CEL, depending on estate size.

**Population monotonicity.** A property: adding a new claimant (estate fixed) never increases any existing claimant's award.

**Proportional Rule.** A division rule that awards each claimant a share proportional to their claim: xᵢ = (cᵢ/D) × E. Attributed to Aristotle.

**Talmud Rule.** The division rule that applies CEA to half-claims when E ≤ D/2 and CEL to half-claims when E > D/2. Discovered by Aumann and Maschler (1985). Equals the nucleolus of the associated bankruptcy game.

---

# Bibliography

## Primary Rabbinic Sources

**Mishnah Bava Metzia** 1:1. The contested garment: two holders, equal and unequal claims.

**Tosefta Bava Metzia** 1:1–2. Extension of the garment case to one-third claims.

**Babylonian Talmud, Bava Metzia** 2a. Gemara discussion of the contested garment; Rashi's commentary introducing Concede and Divide.

**Babylonian Talmud, Ketuboth** 93a. The three-widow problem; Rabbi Natan's pairwise decomposition; CnD-consistency verification.

**Jerusalem Talmud, Ketuboth.** Samuel's statement that creditors "empower each other" — coalitional reasoning.

**Babylonian Talmud, Bava Batra** 35a, 122b–124a. Disputed property and firstborn inheritance.

**Babylonian Talmud, Bava Kamma** 9a. Damage allocation with insufficient assets.

**Babylonian Talmud, Ketuboth** 94a. *Shuda d'dayanei* — judicial discretion.

**Babylonian Talmud, Erakhin** 27b. Auction renege scenario; basis for CEL.

**Babylonian Talmud, Hullin** 27a. <span dir="rtl">רובו ככולו</span> — "more than half is like the whole."

**Maimonides (Rambam).** *Mishneh Torah*:
- Hilkhot Malveh v'Loveh 20:4 — Constrained Equal Awards for creditor division.
- Hilkhot Erkhei HaKdesh 8:4 — Equal loss division for reneging bidders.
- Hilkhot Nahalot — Inheritance laws including the firstborn's double portion.

**Rashi (Rabbi Shlomo Yitzchaki, 1040–1105).** Commentary on Bava Metzia 2a and Ketuboth 93a.

**Tosafot.** Commentary on Ketuboth 93a.

**Rif (Rabbi Isaac Alfasi, 1013–1103).** Halakhic compendium on Ketuboth; admission of difficulty with the three-widow problem.

**Ravad (Rabbi Abraham ben David, 1125–1198).** Glosses on the Rif (Ketuboth 51a) — Layered Equal Division. Glosses on Maimonides (MLvL 20:4) — the Bidding Rule.

**Ramban (Nachmanides, 1194–1270).** Treatment of creditor claims in Ketuboth.

**Ran (Rabbenu Nissim of Gerona, 1320–1376).** Alternative explanation of Ketuboth 93a.

**Rosh (Rabbenu Asher ben Yechiel, 1250–1327).** Practical rulings on creditor division.

**Shulchan Aruch** (Rabbi Yosef Karo, 1488–1575), Choshen Mishpat:
- Siman 138 — Contested garment.
- Simanim 104–105 — Creditor priority.
- Simanim 171–176 — Partnership and land division.
- Simanim 176–177 — Partnership dissolution and *iska*.
- Simanim 277–278 — Inheritance.
- Simanim 389–390 — Damage allocation.

**Ketzos HaChoshen** (Rabbi Aryeh Leib Heller, 1745–1812). Commentary on SA CM 138; *bari*/*shema* analysis.

**Netivot HaMishpat** (Rabbi Yaakov of Lissa, 1760–1832). Commentary on SA CM 138; alternative to Ketzos on *bari*/*shema*.

**Rabbi Hai Gaon** (939–1038). Suggestion that Ketuboth should be explained through Bava Metzia.

**Abraham ibn Ezra** (1089–1167). Layered cost-sharing principle in Torah commentary.

## Academic Sources

**Aumann, Robert J. and Michael Maschler.** "Game Theoretic Analysis of a Bankruptcy Problem from the Talmud." *Journal of Economic Theory* 36 (1985): 195–213. The foundational paper connecting the Ketuboth table to game theory, proving that the CG-consistent solution equals the nucleolus.

**Balinski, Michel.** "What Is Just?" *American Mathematical Monthly* 112, no. 6 (2005): 502–511. Philosophical analysis of division rules and their justifications.

**Dagan, Nir.** "New Characterizations of Old Bankruptcy Rules." *Social Choice and Welfare* 13, no. 1 (1996): 51–59. Alternative axiomatic characterizations of CEA, CEL, and the Talmud Rule.

**Groner, Tsvi.** *The Legal Methodology of Hai Gaon.* Brown Judaic Studies, no. 66. Chico, CA: Scholars Press, 1985. Monograph on Hai Gaon's approach to legal reasoning, including his treatment of claims adjudication.

**O'Neill, Barry.** "A Problem of Rights Arbitration from the Talmud." *Mathematical Social Sciences* 2, no. 4 (1982): 345–371. Early mathematical treatment of the Talmudic bankruptcy problem.

**Piniles, Zvi Menahem.** *Darkah Shel Torah.* Vienna, 1863. First published attempt to explain the Ketuboth table through half-claims CEA.

**Schechter, Stephen.** "How the Talmud Divides an Estate Among Creditors." Working paper, 2012. Accessible exposition of the Aumann-Maschler solution, including Kaminski's glassware proof.

**Schmeidler, David.** "The Nucleolus of a Characteristic Function Game." *SIAM Journal on Applied Mathematics* 17, no. 6 (1969): 1163–1170. Introduction of the nucleolus concept.

**Shapley, Lloyd S.** "A Value for n-Person Games." In *Contributions to the Theory of Games*, vol. 2, edited by H. W. Kuhn and A. W. Tucker, 307–317. Princeton University Press, 1953.

**Thomson, William.** *How to Divide When There Isn't Enough: From Aristotle, the Talmud, and Maimonides to the Axiomatics of Resource Allocation.* Cambridge University Press, 2019. Definitive axiomatic treatment of claims problems.

**Young, H. Peyton.** *Equity: In Theory and Practice.* Princeton University Press, 1994. Broad treatment of fair division, including claims problems and the proportional rule.

## General References

**Aristotle.** *Nicomachean Ethics*, Book V, Chapters 3–4. The proportional rule as a principle of distributive justice.

---

[^1]: Mishnah Bava Metzia 1:1. The oath requirement (<span dir="rtl">שבועה</span>) is a procedural safeguard: each claimant must swear they own no less than half before the division proceeds. The division itself follows from the claims being equal.

[^2]: Mishnah Bava Metzia 1:1. <span dir="rtl">זה אומר כולה שלי וזה אומר חציה שלי... הנוטל יותר ישבע שאין לו בה פחות משלשה חלקים</span>.

[^3]: Tosefta Bava Metzia 1:2. The extension to one-third claims follows the same concede-and-divide logic: the party claiming one-third concedes two-thirds, leaving one-third in dispute.

[^4]: Rashi on BT Bava Metzia 2a, s.v. <span dir="rtl">שלשה חלקים</span>. The algorithm is implicit in Rashi's explanation: "Half is conceded to the one claiming all; the remaining half is contested; they split it."

[^5]: The Tosefta's numbers round to whole fractions because the Tannaitic text works in thirds and sixths of a garment. The exact CnD computation gives 166⅔ and 33⅓ for a 200-zuz garment.

[^6]: Thomson, *How to Divide When There Isn't Enough*, Chapter 2. The formal definition requires E ≥ 0, each cᵢ ≥ 0, and c₁ + c₂ + ... + cₙ ≥ E.

[^7]: Non-negativity (xᵢ ≥ 0), claim-boundedness (xᵢ ≤ cᵢ), and balance (Σxᵢ = E) are the standard feasibility conditions for a claims solution. See Thomson, Chapter 2.

[^8]: The Mishnah in Ketuboth speaks of three wives with ketubot (marriage contracts) of different amounts, but the mathematical structure is identical to three creditors with different claims. Aumann and Maschler frame it as a bankruptcy problem; we follow their convention.

[^9]: Mishnah Ketuboth 10:4; BT Ketuboth 93a.

[^10]: Equal division assigns E/3 to each claimant regardless of claims. For E = 200, this gives (66⅔, 66⅔, 66⅔) ≠ (50, 75, 75).

[^11]: Proportional division with claims (100, 200, 300) and E = 100 gives awards in ratio 1:2:3, i.e., (16⅔, 33⅓, 50) ≠ (33⅓, 33⅓, 33⅓).

[^12]: CEA for claims (100, 200, 300) at E = 200: equal share = 66⅔, all claims exceed this, so awards = (66⅔, 66⅔, 66⅔) ≠ (50, 75, 75).

[^13]: CEL for claims (100, 200, 300) at E = 200: total loss = 400, equal loss = 133⅓, Creditor 1's claim (100) < 133⅓ so she gets 0. Remaining 200 between Creditors 2 and 3 with equal loss 150 each: awards (50, 150) ≠ (75, 75).

[^14]: Aumann and Maschler, "Game Theoretic Analysis of a Bankruptcy Problem from the Talmud," 196.

[^15]: Aumann and Maschler, 196, citing Lewy [7, p. 106].

[^16]: Rif on Ketuboth, cited in Aumann and Maschler, 199. The original reads <span dir="rtl">דקדקנו ביה ולא אסתייעא מילתא</span> — "we examined it closely and the matter did not work out."

[^17]: BT Ketuboth 93a attributes the underlying reasoning to Rabbi Natan. The Gemara's pairwise analysis is the earliest known verification of CnD-consistency.

[^18]: BT Ketuboth 93a. The Gemara explicitly invokes <span dir="rtl">שנים אוחזין</span> (the two-holders principle from Bava Metzia) to justify the pairwise divisions.

[^19]: CnD verification for Creditors 1 and 2, E = 200: combined award = 50 + 75 = 125. CnD(125, [100, 200]): concession of 1 to 2 = max(125 − 100, 0) = 25, concession of 2 to 1 = max(125 − 200, 0) = 0, contested = 100, split 50 each. Awards: (50, 75). ✓

[^20]: Jerusalem Talmud, Ketuboth. Samuel's formulation: <span dir="rtl">מתניתין דמקנן חד לחבריה</span> — "the Mishnah [works because] they empower one another." See Aumann and Maschler, 206.

[^21]: Rashi on BT Ketuboth 93a, s.v. <span dir="rtl">כיצד</span>.

[^22]: Tosafot on BT Ketuboth 93a, s.v. <span dir="rtl">ומאי שנא</span>.

[^23]: Rif on Ketuboth. The Ravad's glosses offer alternative constructions; see Part III.D.

[^24]: Ran on Ketuboth 93a. His priority-based reading attempts to reconcile the numbers through a sequential satisfaction model.

[^25]: Rosh on Ketuboth 93a. His practical ruling influenced the Shulchan Aruch's treatment in CM 104–105.

[^26]: Ramban on Ketuboth. His treatment connects the three-widow problem to broader principles of creditor law.

[^27]: Maimonides, Mishneh Torah, Hilkhot Malveh v'Loveh 20:4. This ruling adopts CEA as the default for creditor division. See Aumann and Maschler, 203, footnote 12.

[^28]: This example follows the standard CEA computation. See Thomson, *How to Divide*, Chapter 3.

[^29]: Maimonides, Mishneh Torah, Hilkhot Erkhei HaKdesh 8:4, based on BT Erakhin 27b.

[^30]: Ravad on Maimonides, Hilkhot Malveh v'Loveh 20:4. See Aumann and Maschler, 203–204.

[^31]: CEL computation: total loss = 30, distributed equally at 10 each, all within claim bounds.

[^32]: Aristotle, *Nicomachean Ethics* V.3: <span dir="rtl">τὸ δίκαιον τὸ ἀνάλογον</span> — "the just is the proportional."

[^33]: Awards: (60/130)×100 = 46.15, (40/130)×100 = 30.77, (30/130)×100 = 23.08.

[^34]: Ravad on Rif, Ketuboth 51a. See Aumann and Maschler, 203, footnote 14.

[^35]: Aumann and Maschler, 203: "This rule is implicit already in the Babylonian Talmud's discussion of our Mishna." Their footnote 14 identifies it with CEA.

[^36]: Ravad on Maimonides, Hilkhot Malveh v'Loveh 20:4. See Aumann and Maschler, 203, footnote 17.

[^37]: The bidding-rule computation: increments are 40, 10, 10. Layer 1: 40/3 each. Layer 2: 10/2 for bidders 2–3. Layer 3: 10/1 for bidder 3. Losses: (13⅓, 18⅓, 28⅓).

[^38]: Thomson, *How to Divide When There Isn't Enough*, Chapters 4–6. The axiomatic method for claims problems was developed systematically from the 1980s onward.

[^39]: Thomson, Chapter 2, defines non-negativity as part of the standard feasibility conditions.

[^40]: Claim-boundedness (xᵢ ≤ cᵢ) is standard. See Thomson, Chapter 2.

[^41]: Balance (Σxᵢ = E) requires full distribution. Some authors use "efficiency" for this property.

[^42]: Equal treatment of equals: Thomson, Chapter 4.

[^43]: Resource monotonicity: if E′ > E, then fᵢ(E′; d) ≥ fᵢ(E; d) for all i. Thomson, Chapter 5.

[^44]: Consistency: Thomson, Chapter 6. The term is used differently in different contexts; here it refers specifically to "bilateral consistency" — the property checked pairwise.

[^45]: Aumann and Maschler, Theorem A, Section 3 (pp. 199–201).

[^46]: CEA is self-consistent (consistent with itself), as is CEL and the Proportional Rule. But only the Talmud Rule is consistent with CnD specifically.

[^47]: Duality: Aumann and Maschler, Section 4 (pp. 202–205). Thomson, Chapter 4.

[^48]: The dual of CEA is CEL: Thomson, Chapter 4. This follows from the definition f*(E; d) = d − f(D − E; d).

[^49]: Aumann and Maschler, Theorem B, Section 4 (p. 205).

[^50]: Aumann and Maschler, 204–205, on <span dir="rtl">רובו ככולו</span> and the psychological watershed at the half-claim.

[^51]: Claims monotonicity: if c′ᵢ > cᵢ (all else equal), then fᵢ(E; c′) ≥ fᵢ(E; c). Thomson, Chapter 5.

[^52]: Population monotonicity: adding a claimant (E fixed) never increases any existing claimant's award. Thomson, Chapter 5.

[^53]: Piniles, *Darkah Shel Torah*, p. 64, Vienna 1863. See Aumann and Maschler, 196 (footnote), 203.

[^54]: For E ≤ D/2, Piniles' rule applies CEA to half-claims, which is exactly what the Talmud Rule prescribes. The two rules diverge only for E > D/2.

[^55]: Aumann and Maschler, 203: "The earliest reference we have been able to find is Piniles (1861)."

[^56]: Piniles' rule for claims (200, 100), E = 200: half-claims (100, 50), H = 150, E > H. Awards = (100 + 25, 50 + 25) = (125, 75) ≠ (150, 50).

[^57]: The run-on-the-bank model: O'Neill, "A Problem of Rights Arbitration from the Talmud" (1982). See also Young, *Equity*, Chapter 4.

[^58]: Two orderings of two claimants: (A, B) gives (200, 0); (B, A) gives (100, 100). Average: (150, 50) = CnD(200, [200, 100]).

[^59]: Shapley, "A Value for n-Person Games" (1953).

[^60]: Shapley Value for claims (200, 200, 300, 300) at E = 600: the expected marginal contributions do not scale linearly with claim duplication, producing approximately (116⅔, 116⅔, 183⅓, 183⅓) instead of (100, 100, 200, 200).

[^61]: The Talmud Rule satisfies a "dummy" property that prevents gaming through claim fragmentation. See Thomson, Chapter 5.

[^62]: Ibn Ezra's layered cost-sharing principle appears in several of his Torah commentaries. See Aumann and Maschler, 203, footnote 14, which notes the connection.

[^63]: Ketzos HaChoshen, Siman 138. The *bari*/*shema* framework analyzes how epistemic certainty affects the allocation.

[^64]: The *bari*/*shema* distinction is a principle of Talmudic jurisprudence (BT Bava Kamma 118a): a certain claim prevails over an uncertain one in some (but not all) circumstances.

[^65]: Ketzos HaChoshen, Siman 138, on *migo* and its interaction with CnD. The analysis asks: if a claimant who says "half is mine" could have said "all is mine" (and been believed via migo), does this strengthen her claim?

[^66]: Netivot HaMishpat, Siman 138. The Netivot holds that *bari*/*shema* operates at the evidentiary level, determining whether a claim is admitted at all, rather than modifying the division algorithm.

[^67]: Shulchan Aruch, Choshen Mishpat, compiled by R. Yosef Karo (1563); Rema glosses by R. Moshe Isserles.

[^68]: SA CM 138; Sma and Shach ad loc. The requirement of physical holding (<span dir="rtl">תפיסה</span>) is a prerequisite for applying CnD.

[^69]: SA CM 104–105 on creditor priority; see also Rosh on Ketuboth for the Rishonic precedents.

[^70]: SA CM 171–176 on partnership law.

[^71]: SA CM 176–177 on *iska* arrangements and partnership dissolution.

[^72]: Hai Gaon's opinion is preserved in the Rif's compilation on Ketuboth. See Aumann and Maschler, 199: "Rabbi Hai Gaon (10th century) did express the opinion that the Mishna in Kethubot should be explained on the basis of that in Bava Metzia."

[^73]: Groner, *The Legal Methodology of Hai Gaon* (1985). The monograph documents Hai Gaon's analytical approach to legal reasoning.

[^74]: Aumann and Maschler, 199.

[^75]: Schechter, "How the Talmud Divides an Estate Among Creditors," p. 1: "Aumann learned of the Talmud's estate-division problem in 1980 or 1981 from his son Shlomo, who was studying at a Talmudic academy in Jerusalem."

[^76]: Aumann and Maschler, 195. Shlomo Aumann was killed on June 9, 1982, during the First Lebanon War.

[^77]: Aumann and Maschler, Theorem B (Section 4) and the explicit construction in Section 3. The algorithm is stated as: when E ≤ D/2, assign CEA of (E; d/2); when E > D/2, assign d − CEA of (D − E; d/2).

[^78]: Aumann and Maschler, Section 5 (pp. 206–207): the coalitional procedure.

[^79]: Jerusalem Talmud, Ketuboth. Samuel's language about creditors "empowering each other" parallels the coalitional procedure's recursive structure.

[^80]: Aumann and Maschler, Theorem C, Section 5 (p. 207).

[^81]: Aumann and Maschler, 204–205, discussing the principle <span dir="rtl">רובו ככולו</span> and the half-way transition.

[^82]: Schechter, "How the Talmud Divides," Section 6; Aumann and Maschler, Section 6 (pp. 207–213).

[^83]: The bankruptcy game's value function: v(S) = max(E − Σ_{j∉S} cⱼ, 0). This guarantees each coalition the estate minus what non-members could claim. See Aumann and Maschler, Section 6.

[^84]: Schmeidler, "The Nucleolus of a Characteristic Function Game," *SIAM Journal on Applied Mathematics* 17 (1969): 1163–1170.

[^85]: The nucleolus is the allocation whose sorted excess vector is lexicographically maximal. See Schechter, Section 6, Definition 6.1.

[^86]: Verification follows Schechter, Section 6, where the excess table for (50, 75, 75) is computed and shown to be lexicographically maximal.

[^87]: Aumann and Maschler, Theorem D, Section 6. The proof connects the consistent solution's properties (CnD-consistency, self-duality) to the nucleolus's lexicographic optimization.

[^88]: Aumann and Maschler, 197.

[^89]: Deuteronomy 21:17: <span dir="rtl">כי את הבכר בן השנואה יכיר לתת לו פי שנים</span>.

[^90]: BT Bava Batra 122b–124a discusses the firstborn's double portion, including the question of whether it applies to <span dir="rtl">ראוי</span> (prospective assets) or only to <span dir="rtl">מוחזק</span> (assets in hand at death).

[^91]: Maimonides, Hilkhot Nahalot 2:1–3; SA CM 277–278.

[^92]: Mishnah Bava Batra 1:1–6; BT Bava Batra 2a–12b.

[^93]: Mishnah Bava Batra 1:6: a courtyard must provide each partner with at least four *amot* by four *amot* to be divisible.

[^94]: BT Bava Batra 7b on expert appraisal for unequal parcels.

[^95]: BT Bava Batra 106b on the use of lots for division of equal-value parcels.

[^96]: SA CM 171–176. The codification covers forced division, voluntary division, improvements by one partner, and property that cannot be divided without diminishing value (<span dir="rtl">אין בו דין חלוקה</span>).

[^97]: BT Bava Metzia 104b–105a; SA CM 176–177.

[^98]: SA CM 177 on *iska*. The default arrangement: half the capital is a loan (guaranteed repayment), half is a deposit for investment (shared risk). Profits on the investment half are split equally.

[^99]: The algorithmic details of *iska* dissolution are codified in SA CM 177 and elaborated by the Sma, Shach, and later commentators.

[^100]: BT Bava Kamma 9a: <span dir="rtl">כל המקדים לגבות זכה</span> — "whoever collects first, acquires" — establishes temporal priority in damage collection.

[^101]: SA CM 389–390 on damage allocation with insufficient assets. Priority ordering: earlier victims may take precedence over later ones.

[^102]: *Shuda d'dayanei*: literally "the throw of the judges" or "the estimation of the judges." BT Ketuboth 94a; BT Bava Batra 35a.

[^103]: BT Ketuboth 94a. The Gemara debates the meaning of *shuda d'dayanei* — Rashi interprets it as judicial discretion; Tosafot interpret it as the judge assessing who is more likely to be the true owner.

[^104]: SA CM 138. The Shulchan Aruch codifies both the algorithmic rules (CnD for contested garment) and the non-algorithmic escape valve (*shuda d'dayanei* for unresolvable cases).

[^105]: Thomson, *How to Divide When There Isn't Enough* (Cambridge University Press, 2019).

[^106]: Thomson, Chapter 6, Theorem on CEA characterization.

[^107]: Thomson, Chapter 6, Theorem on CEL characterization.

[^108]: Thomson, Chapter 6, Theorem on Proportional Rule characterization.

[^109]: Aumann and Maschler, Theorem B; Thomson, Chapter 6.

[^110]: Dagan, "New Characterizations of Old Bankruptcy Rules," *Social Choice and Welfare* 13 (1996): 51–59.

[^111]: Dagan, 55–57, on independence of irrelevant claims and its role in characterizing the Talmud Rule.

[^112]: Balinski, "What Is Just?" *American Mathematical Monthly* 112, no. 6 (2005): 502–511.

[^113]: The application of claims-problem axiomatics to healthcare allocation is discussed in Thomson, Chapter 10, and in subsequent literature on rationing and triage.

[^114]: Network bandwidth allocation as a claims problem: see the literature on max-min fairness and proportional fairness in communication networks, which parallels the CEA/Proportional distinction.

[^115]: Environmental resource allocation as claims problems: Young, *Equity*, Chapter 8.

[^116]: Connections between classical claims-problem axioms and modern algorithmic fairness: a growing literature connects consistency, equal treatment, and monotonicity to the fairness desiderata in automated decision-making.

[^117]: Computational complexity of the Talmud Rule: the CEA/CEL computation requires sorting claims (O(n log n)) and a single pass through the sorted list. The nucleolus in general requires solving a sequence of linear programs with exponentially many constraints, but for bankruptcy games, the Aumann-Maschler result provides the polynomial shortcut.

[^118]: Incomplete information in claims problems: the mechanism design literature addresses settings where claims are private information and claimants may have incentives to misreport. The Ketzos-Netivot debate anticipates some of these considerations.

[^119]: Dynamic claims problems: Thomson, Chapter 9, discusses time-dependent generalizations.

[^120]: Multi-dimensional claims: an active area; see recent work on multi-issue allocation and its axiomatic foundations.

