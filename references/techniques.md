# Investigation Techniques

Use these techniques when the main workflow needs more detail. Keep the investigation proportional to the decision.

## Build a MECE Question Map

### Decompose by decision dependency

1. Write the decision the research must support.
2. List every fact or judgment that could change that decision.
3. Group the list into non-overlapping sub-questions.
4. Add boundary dimensions such as time, version, jurisdiction, environment, population, and excluded cases.
5. Add a contrary question for each high-impact conclusion.

### Apply three tests

- **Coverage test:** Ask, "Could the final answer be materially wrong even if every listed sub-question were answered correctly?" Add the missing branch if yes.
- **Overlap test:** Ask, "Would two branches collect and judge the same evidence for the same purpose?" Merge or redraw them if yes.
- **Decision test:** Ask, "Could an answer to this branch change the conclusion, certainty, or caveat?" Remove or defer it if no.

Prefer a small complete map over a large taxonomy. Reopen decomposition whenever new evidence reveals a missing dependency.

## Match Claims to Primary Sources

Choose the source closest to the event, rule, implementation, measurement, or decision being claimed.

| Claim type | Prefer first | Use secondary sources for |
|---|---|---|
| Product capability or API behavior | Official documentation, changelog, release note, source code, or direct reproduction | Discovery, comparison, and identifying disputed boundaries |
| Price, availability, or policy | Official pricing, terms, status, policy, or announcement page with a date | Historical context or regional interpretation |
| Law, regulation, or standard | Issuing authority, enacted text, official register, or standards body | Commentary about application or consequences |
| Academic result | Original paper, dataset, supplementary material, preregistration, or author code | Field context, replication history, and critique |
| Company performance or statement | Filing, earnings material, official statement, or direct transcript | Independent interpretation and contradiction checks |
| Current event | Direct statement, official record, original media, or firsthand data | Corroboration, context, and competing accounts |
| Software behavior | Current source, tests, versioned documentation, release history, or controlled execution | Finding likely causes and known workarounds |

Treat a primary source as authoritative only for claims within its competence. Challenge self-interested claims with independent evidence.

## Test Source Independence

1. Trace citations and links upstream.
2. Identify shared datasets, press releases, wire reports, documentation, or common witnesses.
3. Check whether one source merely paraphrases another.
4. Count sources with the same origin as one evidentiary line.
5. Seek a different method when truly independent sources do not exist.

Use independence across methods when possible: compare documentation with direct execution, a reported number with a calculation, or a policy statement with the governing text.

## Interrogate Every Decisive Fact

Ask:

- What exactly is being measured, defined, promised, or implemented?
- Why should this fact hold?
- What mechanism produces it?
- Which assumptions must remain true?
- Where does it stop being true?
- Which version, date, environment, jurisdiction, or population does it cover?
- What counterexample would overturn or narrow it?
- Does the source directly support the claim, or does the claim require an inference?
- What incentive or limitation could bias the source?

Write facts, interpretations, and inferences separately. Grade the inference, not the source's confidence.

## Run Active Disconfirmation

### State the alternative

- Write the strongest credible competing answer in terms its supporter would accept.
- Avoid a weak or absurd alternative.
- Predict observable evidence under both the working conclusion and the alternative.

### Search against yourself

- Reverse the claim in search terms.
- Add terms such as limitation, exception, failure, regression, correction, retraction, incompatible, disputed, or false positive when relevant.
- Inspect versions and dates immediately before and after the claimed boundary.
- Look for cases selected by critics, not only by proponents.
- Reproduce the smallest decisive case when direct testing is possible.

### Update honestly

- Keep the conclusion when the alternative fails a fair test.
- Narrow the conclusion when only part survives.
- Downgrade certainty when evidence remains ambiguous.
- Replace the conclusion when the alternative explains the evidence better.
- Mark Unknown when available evidence cannot distinguish the alternatives.

## Resolve Source Conflict

1. Confirm that the sources address the same question.
2. Normalize dates, versions, definitions, populations, and units.
3. Compare proximity to the underlying event or implementation.
4. Compare methods, sample selection, incentives, and correction history.
5. Trace shared ancestry before treating agreement as corroboration.
6. Prefer the explanation that accounts for both agreement and disagreement with fewer unsupported assumptions.
7. Preserve the conflict as an open gap when no defensible resolution exists.

Do not average incompatible claims into a false compromise.

## Apply Certainty Grades Consistently

### Confirmed

Assign Confirmed only after at least two genuinely independent primary sources agree, material conflicts are resolved, and the strongest credible alternative has been tested within the stated scope.

### Probable

Assign Probable when credible evidence supports the claim but full independent primary-source corroboration or one material boundary test remains incomplete. Name that limitation beside the grade.

### Speculative

Assign Speculative when only reasoning or weak, indirect evidence supports the claim and plausible alternatives remain open.

### Unknown

Assign Unknown when available evidence cannot determine the answer. Keep the gap open instead of guessing.

Never use certainty grades as decoration. Tie each grade to the weakest unresolved part of the claim.

## Decide When to Stop

### Check completeness

- Cover every decision-relevant branch or name it as an open gap.
- Trace every key fact to an appropriate primary source when one exists.
- Corroborate every key conclusion with at least two genuinely independent sources.
- Test the strongest credible alternative.
- Resolve meaningful conflicts or expose them.
- Grade every material conclusion.

### Check convergence

Compare the latest investigation pass with the previous pass:

- Did any conclusion change?
- Did any certainty grade change?
- Did any material caveat appear or disappear?
- Did any new source add an independent evidentiary line?
- Did any open gap become practically resolvable?

Stop when all completeness conditions hold and the latest pass changes none of these. Continue only when a specific next action could materially change the answer.

### Prevent overresearch

- Stop after one authoritative source for a trivial, stable, low-impact fact when no ambiguity or conflict appears.
- Stop when remaining gaps cannot affect the decision.
- Stop when the cost of another pass exceeds the value of the uncertainty it could reduce; state that tradeoff.
- Do not keep searching merely to increase citation count.
