# OptiLink design notes

**Status:** Proposed design; requires implementation and user testing.

## Screen flow

1. Home: choose Read Text, Find Object, or Describe Scene through accessible touch controls or speech.
2. Capture: provide spoken framing guidance and capture/cancel controls.
3. Processing: announce progress, allow cancellation, and handle timeouts.
4. Result: speak a concise response; allow repeat, stop, recapture, and return to task selection.

The [interface concept](../assets/optilink-interface-concept.svg) illustrates home, text capture, and text result screens. Camera guidance and recognized text are examples, not implemented behavior.

## Accessibility requirements

- Give every interactive control a meaningful TalkBack label and appropriate role.
- Preserve logical focus order and announce status changes without moving focus unexpectedly.
- Avoid gestures, color, icons, or camera previews as the only means of understanding a task.
- Support text scaling and large touch targets; verify the final layout on actual devices.
- Keep speech brief, allow immediate interruption, and provide accessible touch alternatives to voice commands.
- Test with consenting blind and low-vision users where recruitment permits.

## Recovery and user control

| Situation | Intended behavior |
| --- | --- |
| Blurred image or tiny text | Explain the issue and request another capture |
| Requested object not detected | State that it was not detected in this image; do not claim it is absent from the room |
| Ambiguous description | Communicate uncertainty and offer recapture |
| Cloud consent declined | Explain which selected features remain available locally |
| Network unavailable | Announce the issue and use local modes where supported |
| Speech command unclear | Ask the user to repeat or use an accessible button |

## Privacy design

Request camera and microphone permissions when needed. Explain cloud processing before transmitting an image. Keep API credentials on the backend. Avoid retaining captured images by default; any evaluation recording requires separate informed consent.

## Open decisions

OCR provider, detector classes, cloud model, device requirements, language availability, and final visual styling will be determined during development. The proposed screens do not establish accessibility compliance.
