# Detailed source-specific workflow


1. Establish the contracting authority, reference, lot, official profile and document versions. For discovery, start with the official PLACSP Atom feed using `licita_search`. Report pages and entries scanned, retrieval time, cancellation notices, truncation and the continuation cursor. A recent feed update is not a new or still-open tender. Do not label this bounded national feed window as all tenders in Spain.
2. For a named tender, retrieve the current announcement, PCAP, PPT, annexes, corrections and clarification notices from the official profile or user attachments. Use the host's file reader for supplied documents. A summary or scraped title is not the tender terms. Preserve lot-specific differences, deadline date/time and the source timezone; never invent a timezone or infer a deadline from publication date.
3. Extract exact passages into a qualification matrix: requirement; document/page/section; applicant evidence; met / not met / unknown; required action. Distinguish professional capacity, company certifications, financial solvency, insurance, turnover, references, guarantees, award criteria and post-award requirements. Do not turn a desirable award criterion into an exclusion or an unverified user fact into a compliance claim.
4. Give a concise pursue / conditional / do-not-pursue recommendation only when supported. Preserve the user's actual capacity and scope; ask only for missing facts that change the decision. Identify lawful options explicitly allowed by the tender, such as reliance on third-party capacity, lots or a joint bid, without assuming those routes are permitted.
5. End with the concrete official documents and next preparation action. Drafting, signing, upload, submission receipt, admission and award are different states. This plugin does not log in, sign or submit bids.

## Output

Decision; official reference and lot; scope searched; budget with tax treatment; exact deadline; eligibility matrix with clause citations; missing evidence; official next step.

