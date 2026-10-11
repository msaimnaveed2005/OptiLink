# OptiLink: An AI Visual Assistant for Blind and Low-Vision People

**Competition:** International AI Competition  
**Project Category:** Intelligent App Creation  
**Proposed by:** Muhammad Saim Naveed  
**Project Status:** Proposed prototype  
**Keywords:** Assistive Technology, Computer Vision, Accessibility, Optical Character Recognition, Voice Interaction

## 1. Project Overview & Problem Statement

OptiLink is a proposed mobile application that converts selected visual information into spoken assistance for blind and low-vision people. Using a smartphone camera and voice interaction, it will help users read printed text, identify everyday objects, and ask simple questions about a captured scene.

Everyday activities such as reading a notice, finding a household item, or checking a product label can require assistance when information is available only visually. Switching between separate tools and navigating camera interfaces can also create barriers. OptiLink aims to bring these tasks into one accessible, voice-first application, with English support in the initial prototype and Urdu support evaluated as a localized extension.

The project focuses on practical information access and greater independence. It is not intended to replace a white cane, guide dog, or orientation and mobility training.

## 2. Proposed Solution

The user selects a task through an accessible button or voice command, points the camera, and captures an image. The application processes the image using the appropriate AI component and speaks a concise response. Users can repeat, stop, or request additional detail.

Three core modes will form the minimum viable product:

1. **Read Text:** Extract printed text from a captured image and read it aloud.
2. **Find an Object:** Identify a requested supported object and describe its approximate position within the camera image, such as left, center, or right.
3. **Describe a Scene:** Provide a short description of visible objects and activities, with optional follow-up questions about the same image.

For example, a user may say “Read this notice,” capture a photograph, and hear the recognized text. If the photograph is blurred or the text is too small, the application should ask for another capture instead of guessing.

Object locations refer only to the captured image. The prototype will not infer safe walking routes, reliable distances, or whether a road is safe to cross.

## 3. Objectives & Expected Outcomes

### Objectives

- Build an accessible Android prototype that supports text reading, common-object identification, and scene descriptions.
- Enable core tasks through speech and screen-reader-compatible controls.
- Communicate uncertain results and offer useful recovery steps.
- Evaluate whether users can complete selected everyday information tasks with less assistance.
- Explore Urdu text and speech support without delaying the core prototype.

### Expected Outcomes

- A working prototype and a documented demonstration of all three core modes.
- A usability report based on feedback from consenting blind or low-vision participants, subject to recruitment availability.
- A performance report covering recognition quality, response time, task completion, and failure cases.
- A documented development roadmap for broader language support and improved offline operation.

### Proposed Evaluation Targets

These are prototype targets, not achieved results.

| Measure | Proposed target and method |
| --- | --- |
| Accessibility | All core flows usable with Android TalkBack, without requiring visual-only controls |
| Task completion | At least 80% completion across predefined reading and object-finding tasks in a small supervised pilot |
| English OCR | Character error rate of 10% or less on a held-out set of clearly printed, well-lit samples |
| Object detection | Report precision and recall for a fixed set of 10–15 everyday object classes on held-out images |
| Response time | Median spoken-response start within 5 seconds on the selected test phone and documented network conditions |
| User feedback | Collect ratings and qualitative feedback on clarity, control, and usefulness; report participant count and limitations |

Results will be reported separately for difficult conditions such as low light, clutter, and blurred images. A small pilot will not establish real-world navigation safety.

## 4. Target Users

- Blind and low-vision adults seeking assistance with everyday visual information.
- Students who need spoken access to printed notices and learning materials.
- Users who prefer audio interaction over visually complex interfaces.
- Accessibility organizations and educators supporting prototype testing and feedback.

Participants will help refine the interface and task priorities. The design will account for differing levels of vision, smartphone experience, and language preference.

## 5. Key Features / Deliverables

### Core Features

- **Printed-text reading:** Capture, recognize, and speak text with repeat and stop controls.
- **Common-object identification:** Recognize supported everyday objects and describe their approximate image position.
- **Scene descriptions:** Generate brief, image-grounded descriptions on demand.
- **Voice interaction:** Support a small set of clear commands, with accessible touch controls as a fallback.
- **Accessible interface:** Meaningful screen-reader labels, logical focus order, large controls, adjustable text, and high contrast for low-vision users.
- **Capture guidance:** Provide audio prompts when image quality or framing prevents useful recognition.
- **Uncertainty handling:** Say when content cannot be identified reliably; avoid presenting uncertain descriptions as facts.
- **Privacy controls:** Explain camera and microphone use, obtain consent for cloud processing, and avoid retaining images by default.

### Stretch Features

- Urdu printed-text reading and spoken output, subject to quality testing.
- Offline text reading and a limited on-device object detector.
- Follow-up questions about the most recently captured scene.
- Optional vibration feedback for capture completion and processing status.

### Final Deliverables

1. Android prototype installation package.
2. Source code and setup documentation.
3. Architecture and data-flow documentation.
4. Accessibility and performance evaluation report.
5. Short demonstration video and presentation materials.

## 6. Implementation Plan & Timeline

The proposed schedule is eight weeks and can be adjusted to the competition deadline and team availability.

| Period | Activities | Milestone |
| --- | --- | --- |
| Week 1 | Gather user needs, define tasks, recruit potential testers, and assess privacy requirements | Requirements and evaluation plan |
| Week 2 | Build accessible screens, camera capture, speech output, and basic commands | Accessible application shell |
| Weeks 3–4 | Integrate OCR and common-object detection; add capture guidance | Reading and object modes |
| Week 5 | Integrate scene descriptions, constrained follow-up questions, and uncertainty responses | Complete core AI workflow |
| Week 6 | Improve error handling, connectivity fallback, and processing efficiency; assess Urdu feasibility | Stable prototype |
| Week 7 | Conduct supervised accessibility and task testing; fix priority issues | Evaluation findings and revisions |
| Week 8 | Final verification, documentation, demonstration recording, and submission preparation | Competition deliverables |

If time or resources are limited, reliable English text reading and accessible controls will take priority, followed by object identification and scene description.

## 7. Resources or Requirements

### Proposed Technical Approach

- **Mobile application:** Kotlin for an Android-first prototype.
- **Text recognition:** An OCR component selected after testing printed-text quality, language support, and offline availability.
- **Object identification:** A pretrained mobile-compatible detector, limited to supported classes and evaluated on representative images.
- **Scene understanding:** A vision-language model accessed through a backend for optional cloud processing.
- **Audio interface:** Speech recognition and text-to-speech, with language availability checked on target devices.
- **Backend:** A lightweight service to protect API credentials, limit requests, and avoid unnecessary image retention.
- **Development workflow:** Version control, documented test cases, and repeatable evaluation scripts.

The processing flow is: user command → camera capture → image-quality check → selected recognition component → result validation → spoken output. Basic local modes should remain usable when cloud scene description is unavailable, where the chosen components support it.

### Required Resources

- A development laptop and at least one Android smartphone with a camera and microphone.
- Access to suitable pretrained models, with licenses checked before use or redistribution.
- A modest cloud/API allowance if cloud scene descriptions are included; spending limits and request quotas will be configured.
- Test images covering selected object classes, printed text, and challenging capture conditions.
- Consenting accessibility testers and, where available, an accessibility advisor.

No custom hardware is required. Exact costs will be estimated after model selection and expected request volumes are known.

## 8. Potential Challenges or Risks

| Challenge or risk | Planned response |
| --- | --- |
| Incorrect or invented AI descriptions | Use image-grounded prompts, concise output, uncertainty language, and evaluation of unsupported claims; require recapture when needed |
| Missed objects or misleading position cues | Restrict supported classes, report image-relative positions only, and exclude autonomous navigation from scope |
| Poor lighting, blur, or clutter | Add capture-quality checks and spoken guidance; test difficult conditions separately |
| Network delays or outages | Provide clear processing status, timeout handling, and local fallback where supported |
| Sensitive documents or bystanders in images | Process locally where feasible, require cloud consent, minimize uploaded content, and avoid default image storage |
| Voice commands failing in noisy settings | Provide screen-reader-accessible touch alternatives and repeat/cancel controls |
| Limited Urdu recognition quality | Evaluate Urdu separately and label it experimental until validated |
| Limited access to user testers | Recruit early through accessibility contacts and report honestly if testing is limited to preliminary checks |
| Excessive audio output | Keep responses brief, make detail optional, and provide immediate stop control |

The prototype will not make medication decisions, authenticate currency, identify strangers, or advise users when to cross a road. These tasks require capabilities and validation beyond this project's scope.

## 9. Additional Details

### Project Contribution

OptiLink combines established AI capabilities into an accessible workflow designed around user tasks. Its proposed contribution is the integration of concise spoken assistance, capture guidance, uncertainty handling, and evaluation with intended users. Urdu support offers a potential local-accessibility extension; the proposal does not claim that the concept is the first of its kind.

### Demonstration Plan

The demonstration will show a user reading a printed notice, locating a supported household object, and requesting a description of a stationary indoor scene. It will also show how the app responds to a blurred image and unavailable internet access. Demonstration images and participants will be used with permission.

### Future Development

After the prototype is evaluated, future work may expand language coverage, improve offline processing, and allow users to personalize supported tasks. Any mobility-related feature would require a separate safety assessment and specialist testing before deployment.

### Five Keywords for the Application Form

Assistive Technology, Computer Vision, Accessibility, Optical Character Recognition, Voice Interaction
