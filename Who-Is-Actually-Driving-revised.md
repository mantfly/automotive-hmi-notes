# Who Is Actually Driving?

## SAE Levels 0–5, Explained Through Real Cars and Everyday Situations

Imagine you are driving home on a rainy evening.

The car is holding its speed, following the vehicle ahead and keeping itself in the lane. Your hands are relaxed. Your feet are away from the pedals.

Then the lane markings fade near a construction zone.

Who is supposed to notice first—you or the car?

That question is more useful than asking whether the vehicle is “self-driving.” The SAE levels are not a ranking of how intelligent or futuristic a car feels. They describe how the driving task—and the responsibility for it—is divided between a human and a system.

I am starting with Levels 0–5 because they give everyone working on automotive HMI—designers, engineers, product managers and others—a shared foundation. This article is also a reference for my own learning: a place to begin with the basics before moving into more complex questions about human–automation interaction.

So, let us take a closer look at what the SAE levels actually mean. The Society of Automotive Engineers (SAE) defines **six levels of driving automation, numbered from Level 0 to Level 5**. Together, they describe how control and responsibility gradually shift from the human driver to the automated system.

Before we get into the levels, a quick note on language. SAE uses **Automated Driving System (ADS)** for the hardware and software collectively capable of performing the complete **Dynamic Driving Task (DDT)** on a sustained basis. Terms such as “autonomous driving” and “self-driving car” are widely used, but SAE advises against them because they are unclear about what the system can do and what the human must still do. Following [SAE J3016](https://www.sae.org/standards/j3016_202104-taxonomy-definitions-terms-related-driving-automation-systems-road-motor-vehicles) and the convention used by [Yurtsever and colleagues](https://arxiv.org/abs/1906.05113), this article uses the more precise language of **driving automation**.

---

## Before the Six Levels, Ask Four Questions

We can understand the whole framework without beginning with acronyms. For any driving feature, ask:

1. **Who controls the vehicle?** Who steers, accelerates and brakes?
2. **Who watches the road?** Who detects vehicles, pedestrians and hazards, interprets the situation and decides how to respond? SAE calls this *Object and Event Detection and Response*, or **OEDR**.
3. **Who provides the plan B?** If the feature reaches its limit, must the human take over, or can the system bring the vehicle to a safer state by itself? This is the **fallback**.
4. **Where does the feature work?** Its ability may depend on road type, speed, weather, lighting, lane markings, map coverage and sensor condition. These boundaries form its **Operational Design Domain**, or **ODD**.

One detail matters: an automation level belongs to a particular feature under particular conditions, not necessarily to the whole car. The same vehicle could contain an L0 emergency-braking feature, an L2 highway-assistance feature and an L4 automated-parking feature.

*[Insert Figure 1 here]*

*Figure 1. Four questions reveal how control, monitoring and fallback are divided—and where the feature is designed to work.*

With this framework in place, let us return to the rainy journey and see how the human role changes at each level.

---

## Level 0: The Car Can React, but You Are Driving

You begin by reversing out of a parking space. The car detects another vehicle approaching and warns you. It might even brake briefly to prevent a collision.

That can feel intelligent, but it is still Level 0.

At L0, you perform the sustained driving task. Features such as blind-spot warnings, lane-departure warnings and automatic emergency braking may warn or intervene in a specific moment, but they do not continuously drive the vehicle.

The HMI has one job: make the event and the required response immediately clear. What was detected? Is the system warning or intervening? What should you do now?

> A system can act automatically without being an automated-driving system.

---

## Level 1: The Car Takes One Part of the Work

You join the motorway and activate adaptive cruise control. The car adjusts its speed and following distance, but you continue steering and watching the road.

This is the basic L1 pattern: the system continuously controls either lateral movement—steering and lane position—or longitudinal movement—speed and braking—but not both at the same time.

If you have driven a car with adaptive cruise control, you may already have used an L1 feature. Mercedes-Benz introduced its radar-based **DISTRONIC** adaptive cruise control on the W220 S-Class in 1998, an early production example of sustained longitudinal assistance. [Mercedes-Benz records the milestone in its technology history](https://www.mercedes-benz.com/en/innovation/milestones/technology/mercedes-benz-since-1945/).

For the interface, the central question is simple:

> What is the system controlling, and what remains my responsibility?

---

## Level 2: The Car Steers and Controls Speed—but You Still Watch

Now add lane centring to adaptive cruise control. The car steers, follows traffic and adjusts its speed. Both dimensions of motion are automated.

This is Level 2—and it is where the experience can become misleading.

The system performs most of the visible driving actions, but you still monitor the road and provide fallback. [**Cadillac Super Cruise**](https://www.cadillac.com/technology/super-cruise) is a useful example: it can enable hands-free driving on compatible roads, but a driver-attention system checks that the driver remains attentive. Cadillac still describes it as driver-assistance technology, not a replacement for the driver.

> Hands-free does not mean eyes-free—or mind-free.

L2 creates a supervision paradox: the better the system performs, the less necessary the human may feel, even though continuous human attention is still required. Lee and See’s research on trust in automation explains why the goal is not maximum trust but **appropriate reliance**—the user’s confidence should match the system’s actual capability.

The cost of getting that relationship wrong is not theoretical. In 2018, a Tesla Model X operating with partial driving automation struck a highway crash barrier in Mountain View, California, killing the driver. The [US National Transportation Safety Board](https://www.ntsb.gov/investigations/Pages/HWY18FH011.aspx) attributed the crash to a combination of the system’s limitations and the driver’s distraction and overreliance on the automation; it also identified ineffective monitoring of driver engagement as a contributing safety issue. The case illustrates the danger of a system performing the physical work while the human remains responsible for seeing what the system misses.

An L2 interface therefore needs to keep three things continuously understandable:

- what the feature is controlling;
- what conditions it can currently handle;
- what the driver must still do.

*[Insert Figure 2 here]*

*Figure 2. Smooth assistance can increase trust, reduce attention and make the eventual human response slower. Driver monitoring helps detect disengagement, but it does not transfer responsibility away from the driver.*

---

## Level 3: For the First Time, the System Watches the Road

Traffic slows to a crawl. At Level 3, the vehicle may tell you that automated driving is available and allow you to look away to read a message.

The important change is not smoother steering. It is that the system now monitors the road and performs the complete driving task within its ODD.

Honda provided an early historical anchor in 2021 with the [**Traffic Jam Pilot**](https://hondanews.com/en-US/releases/honda-launches-next-generation-honda-sensing-elite-safety-system-with-level-3-automated-driving-features-in-japan) function in the Honda Legend—the first production vehicle to receive Japanese government designation for Level 3 automated driving. Its limited lease programme showed that this transfer of monitoring responsibility was technically and legally possible, although only under tightly specified conditions.

The next few years showed both progress and fragility. In 2023, [California authorised Mercedes-Benz **DRIVE PILOT**](https://www.dmv.ca.gov/portal/news-and-media/california-dmv-approves-mercedes-benz-automated-driving-system-for-certain-highways-and-conditions/) as the first production-vehicle L3 system permitted on the state’s public freeways. The approval was highly conditional: operation was limited to daylight and speeds up to 40 mph, and excluded construction zones, heavy rain, heavy fog and flooded roads. In December 2024, Germany’s Federal Motor Transport Authority [approved an upgraded version for use at up to 95 km/h](https://group.mercedes-benz.com/technology/autonomous-driving/driving/drive-pilot-95-kmh.html) under certain conditions, making it the fastest certified L3 system in a standard-production vehicle at the time. In December 2025, China also [granted its first conditional product-access approvals](https://www.miit.gov.cn/xwfb/gxdt/sjdt/art/2025/art_f734c7074580470593d4018742997640.html) to two L3 models from Changan and BAIC’s Arcfox for trials on designated roads in Chongqing and Beijing.

Yet commercialisation is not a straight line. Mercedes [paused DRIVE PILOT on the revised S-Class in early 2026](https://www.theverge.com/transportation/860935/mercedes-drive-pilot-level-3-scrapped), pointing to its restricted usefulness and high cost while shifting near-term attention to a more broadly usable L2 system. L3 has moved beyond a laboratory concept, but it has not yet become an ordinary mass-market feature. The narrow ODD, redundant hardware, regulation and takeover problem all have to work as one product.

But the human has not disappeared. As the rainy journey approaches the construction zone and the feature reaches its limit, the system may issue a **request to intervene**. You must notice the request, leave the non-driving activity, rebuild an understanding of the traffic situation and regain control.

That is a cognitive transition, not a button press.

Gold and colleagues found that traffic complexity affected both how quickly people took over from highly automated vehicles and how safely they responded. Merat and colleagues describe the related **out-of-the-loop** problem: while disengaged from driving, a person may lose situation awareness, familiarity with control and understanding of the automation’s state.

More recent work is beginning to turn that broad problem into specific interface decisions. In a [2025 simulator study](https://journals.sagepub.com/doi/10.1177/00187208241278433), Wu and colleagues tested four takeover-request times and seven combinations of visual, auditory and vibrotactile warnings. Longer lead times increased trust, while collisions during takeover reduced it. Warning modality alone did not significantly change trust, and using three modalities showed no clear advantage over using two. The practical lesson is not simply to add more alerts: sufficient time and a successful transition may matter more than sensory intensity.

A useful L3 interface must therefore explain why intervention is needed, how much time is available, what the vehicle is doing and when control has actually transferred. A loud alarm can attract attention, but it cannot instantly rebuild awareness of nearby traffic or disappearing lane markings.

*[Insert Figure 3 here]*

*Figure 3. A safe takeover requires attention, situation awareness, a decision and physical control—not merely a hand touching the steering wheel.*

---

## Level 4: The System Must Have Its Own Plan B

Now imagine that instead of driving home, you order a robotaxi. There is no safety driver behind the wheel. You enter a destination and become a passenger.

At Level 4, the system performs the complete driving task and handles fallback within its ODD. It cannot assume that you know how—or are able—to take control. If normal operation becomes impossible, it must reach a minimal-risk condition, perhaps by slowing down, stopping safely or requesting remote assistance.

[**Waymo One**](https://waymo.com/waymo-one/) illustrates this L4 pattern. Passengers are not expected to monitor the road or take over, but the service operates within defined geographical and operational boundaries. A robotaxi working inside part of a city can therefore be L4 without being able to drive everywhere.

Robotaxis are no longer a single-city American experiment. By March 2026, Waymo was [reporting 500,000 paid rides a week](https://techcrunch.com/2026/03/27/waymo-skyrocketing-ridership-in-one-chart/); in September it [began public rides in Denver, San Diego and Tampa](https://waymo.com/blog/2026/09/ride-in-denver-san-diego-tampa/), bringing its fully autonomous service to 14 US cities and [a fleet of more than 4,000 vehicles](https://techcrunch.com/2026/09/01/waymo-accelerates-robotaxi-expansion-with-launches-in-denver-san-diego-and-tampa/). The picture is also increasingly global. [Baidu reported in August 2026](https://ir.baidu.com/news-releases/news-release-details/baidu-announces-second-quarter-2026-results) that **Apollo Go** had reached 28 cities and begun fully driverless commercial operations in Dubai, with rides available through both Apollo Go and Uber. L4 is becoming a transport service that product, software, operations and support teams may have to design at real scale.

Scale, however, does not remove the operating boundary. In May 2026, Waymo filed [a software recall covering 3,791 ADS-equipped vehicles](https://static.nhtsa.gov/odi/rcl/2026/RCLRPT-26E026-6527.pdf) after one vehicle detected a flooded, higher-speed roadway but proceeded into it at reduced speed. [A second recall in June](https://www.reuters.com/legal/litigation/waymo-recall-over-3800-robotaxis-over-risk-entering-closed-construction-zones-2026-06-18/) covered 3,871 systems after vehicles entered closed freeway construction zones. The remedies involved restricting operations and changing software, maps and weather-related controls—not asking a passenger to take over.

This returns us to the fading lane markings in the opening scene. At L2, the driver must recognise that the construction zone is becoming unsafe. At L4, the passenger is not the backup: detecting the boundary and reaching a safe outcome belong to the system and the service around it.

The interface also changes character. Journey progress, route changes, unexpected stops, support and reassurance become more useful than steering-assistance status. The HMI begins to resemble a mobility service rather than a traditional cockpit.

---

## Level 5: No Predefined Operating Domain

Finally, imagine the same journey across any road a competent human could reasonably manage—in city traffic, on an unmapped rural road, in rain or snow.

That is the idea behind Level 5. The system performs the complete driving task without a predefined ODD, and no human supervision or fallback response is required.

SAE defines capabilities and responsibilities, not cabin styling, so L5 does not automatically mean that every steering wheel must disappear. More importantly, L5 is not simply L4 with better sensors. Removing the operating-domain boundary means coping with the enormous variety of roads, weather, infrastructure, regulations and unusual human behaviour found in the real world.

At this level, HMI becomes entirely passenger-facing: destination management, accessibility, comfort, privacy, emergency assistance and communication about the journey.

---

## The Six Levels in One View

| Level | Who controls motion? | Who watches the road? | Who handles fallback? | Human role |
|---|---|---|---|---|
| **L0** | Human | Human | Human | Driver |
| **L1** | Human and system; system controls one dimension | Human | Human | Assisted driver |
| **L2** | System controls steering and speed | Human | Human | Supervising driver |
| **L3** | System within its ODD | System | Human responds when requested | Fallback-ready user |
| **L4** | System within its ODD | System | System | Passenger |
| **L5** | System across human-manageable on-road conditions | System | System | Passenger |

*[Insert Figure 4 here]*

*Figure 4. Automation advances through transfers of control, monitoring and fallback—not through a simple increase in “intelligence.”*

The most important boundary is between **L2 and L3**. At L2, the system controls the vehicle but the human watches the road. At L3, responsibility for watching the road moves to the system within its ODD.

The next boundary, from L3 to L4, transfers fallback responsibility. The move from L4 to L5 removes the predefined operating-domain limitation.

---

## How HMI Priorities Change

| | L0–L2 | L3 | L4–L5 |
|---|---|---|---|
| **Main question** | What must I do now? | What is the system doing, and must I respond? | What will happen during my journey? |
| **Design focus** | Clear feedback and low distraction | Mode awareness and safe transitions | Confidence, comfort and accessibility |
| **Safety goal** | Support correct human action | Rebuild awareness and transfer control | Communicate system-managed fallback |
| **Most useful information** | Vehicle state and required action | Mode, limits, reason and time to respond | Progress, intent, disruption and support |

Across all levels, four human-factors questions keep returning: Does the user know which mode is active? Does their trust match the system’s capability? Do they understand what is happening and what may happen next? Can they process the information without unnecessary cognitive load?

This is why transparency should not mean displaying everything the vehicle detects. A screen full of bounding boxes, sensor signals and confidence scores may show technical sophistication while making the situation harder to understand.

Useful transparency is selective:

> Show enough for the user to understand the current mode, their role, the system’s boundary, its next action and any required response.

---

## What This Means for a Product Team

When a driving feature approaches the edge of its operating domain, the experience depends on several teams sharing the same definition of the situation.

| Role | The question it must answer |
|---|---|
| **Product and function design** | When is the feature available, degraded or unavailable, and what should happen next? |
| **Vehicle platform and backend** | Are sensor, map, localisation and system-health signals reliable, timely and consistent? |
| **Frontend engineering** | Can changing states be presented without delay, contradiction or stale information? |
| **Interaction and visual design** | Can the user understand the mode, urgency and required action across visual, audio and haptic channels? |

A compact review sequence is:

> **Mode → Human role → Operating boundary → System intent → Required action → Fallback**

If any link is unclear, the interface may look polished while leaving the human and the system with different understandings of who is responsible.

---

## The Question to Remember

SAE Levels 0–5 are often drawn as a staircase toward a driverless future. A better way to read them is as a sequence of responsibility transfers: first control, then monitoring, then fallback, and finally the operating-domain boundary.

For anyone designing automotive systems, the HMI must make those transfers visible and understandable.

So when a feature is described as “intelligent,” “hands-free” or “self-driving,” ask:

> **Who is actually driving—and what happens when the system reaches its limit?**

---

## A Note on the Writing Process

The structure and central argument of this article are my own. I used AI as a supporting tool to search for relevant literature, locate and cross-check real-world cases, and refine the English wording and flow. I reviewed and selected the sources and remain responsible for the final content.

---

## References and Further Reading

- SAE International. [*SAE J3016: Taxonomy and Definitions for Terms Related to Driving Automation Systems for On-Road Motor Vehicles*](https://www.sae.org/standards/j3016_202104-taxonomy-definitions-terms-related-driving-automation-systems-road-motor-vehicles).
- Yurtsever, E., Lambert, J., Carballo, A., & Takeda, K. [*A Survey of Autonomous Driving: Common Practices and Emerging Technologies*](https://arxiv.org/abs/1906.05113). *IEEE Access*, 2020.
- Lee, J. D., & See, K. A. [*Trust in Automation: Designing for Appropriate Reliance*](https://journals.sagepub.com/doi/10.1518/hfes.46.1.50_30392). *Human Factors*, 2004.
- Gold, C., Körber, M., Lechner, D., & Bengler, K. [*Taking Over Control From Highly Automated Vehicles in Complex Traffic Situations*](https://pubmed.ncbi.nlm.nih.gov/26984515/). *Human Factors*, 2016.
- Merat, N., Seppelt, B., Louw, T., et al. [*The “Out-of-the-Loop” Concept in Automated Driving*](https://link.springer.com/article/10.1007/s10111-018-0525-8). *Cognition, Technology & Work*, 2019.
- Wu, Y., Yao, X., Deng, F., & Yuan, X. [*Effect of Takeover Request Time and Warning Modality on Trust in L3 Automated Driving*](https://journals.sagepub.com/doi/10.1177/00187208241278433). *Human Factors*, 2025.
- National Transportation Safety Board. [*Collision Between a Sport Utility Vehicle Operating With Partial Driving Automation and a Crash Attenuator, Mountain View, California*](https://www.ntsb.gov/investigations/Pages/HWY18FH011.aspx). Highway Accident Report HAR-20/01, 2020.
- California Department of Motor Vehicles. [*California DMV Approves Mercedes-Benz Automated Driving System for Certain Highways and Conditions*](https://www.dmv.ca.gov/portal/news-and-media/california-dmv-approves-mercedes-benz-automated-driving-system-for-certain-highways-and-conditions/), 2023.
- Mercedes-Benz Group. [*Mercedes-Benz Increases Top Speed of Its Level 3 Automated Driving System to 95 km/h*](https://group.mercedes-benz.com/technology/autonomous-driving/driving/drive-pilot-95-kmh.html), 2024.
- Ministry of Industry and Information Technology of China. [*MIIT Grants Conditional Product Approval to Two Level 3 Automated-Driving Vehicles*](https://www.miit.gov.cn/xwfb/gxdt/sjdt/art/2025/art_f734c7074580470593d4018742997640.html), 2025.
- Waymo. [*Welcoming Our First Riders in Denver, San Diego, and Tampa*](https://waymo.com/blog/2026/09/ride-in-denver-san-diego-tampa/), 2026.
- Korosec, K. [*Waymo’s Skyrocketing Ridership in One Chart*](https://techcrunch.com/2026/03/27/waymo-skyrocketing-ridership-in-one-chart/). *TechCrunch*, 2026.
- Baidu. [*Baidu Announces Second Quarter 2026 Results*](https://ir.baidu.com/news-releases/news-release-details/baidu-announces-second-quarter-2026-results), 2026.
- US National Highway Traffic Safety Administration. [*Part 573 Safety Recall Report 26E026*](https://static.nhtsa.gov/odi/rcl/2026/RCLRPT-26E026-6527.pdf), 2026.
- Reuters. [*Waymo Recalls Nearly 3,900 Robotaxis Over Risk of Entering Closed Construction Zones*](https://www.reuters.com/legal/litigation/waymo-recall-over-3800-robotaxis-over-risk-entering-closed-construction-zones-2026-06-18/), 2026.
- Chen, F., & Terken, J. *Automotive Interaction Design: From Theory to Practice*.
- Meixner, G., & Müller, C. *Automotive User Interfaces: Creating Interactive Experiences in the Car*.
