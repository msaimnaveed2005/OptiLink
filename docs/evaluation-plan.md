# OptiLink evaluation and demonstration plan

**Status:** Planned evaluation; no testing results have been collected.

## Proposed measures

| Measure | Target or reporting method |
| --- | --- |
| TalkBack accessibility | Complete all core flows without visual-only controls |
| Task completion | At least 80% across predefined reading and object-finding tasks in a small supervised pilot |
| English OCR | Character error rate at most 10% on held-out, clearly printed, well-lit samples |
| Object identification | Report precision and recall for 10–15 fixed everyday classes on held-out images |
| Response time | Median spoken-response start within 5 seconds on a documented test phone and network |
| User experience | Record participant count, ratings, and qualitative feedback |

Report blur, low light, and clutter separately. Document model versions, phone specifications, sample counts, network conditions, and limitations. Do not use evaluation images as development examples in a way that contaminates the held-out set.

## Demonstration scenarios

| Scenario | Expected demonstration |
| --- | --- |
| Printed notice | Capture and read text; repeat and stop speech |
| Supported household object | Request an object and report its image-relative position |
| Stationary indoor scene | Speak a brief description of visible content |
| Blurred capture | Ask for recapture rather than inventing text |
| Network unavailable | Explain unavailable cloud processing and demonstrate local fallback if supported |
| Cloud consent declined | Respect the choice and explain remaining capabilities |

Use demonstration images and participants with permission. The interface illustration contains fictional notice text.

## Participant testing

Recruit consenting blind or low-vision adults where possible. Explain that this is an experimental information-access prototype. Use stationary, supervised tasks, permit withdrawal, and collect only the minimum necessary data. Report honestly if recruitment is limited or only preliminary checks are possible.

## Results to publish after testing

Record per-task completion, OCR errors, object precision/recall, response-time distributions, unsupported scene claims, recovery behavior, and accessibility issues. Distinguish achieved results from targets. A small pilot does not establish navigation safety.
