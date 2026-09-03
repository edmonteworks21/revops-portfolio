# Email deliverability, taking a program from 200 sends to 2,800

Freelance engagement, 2026. Platform was HubSpot.

---

## Where things stood

The client had an email program in name only. The largest send in its history had gone to 200 recipients. There was no plan for what happened when that number grew, which mattered because growing it was the point of the engagement.

Sending volume is the thing that exposes every weakness in an email setup at once. At 200 recipients you can get away with unauthenticated mail, a messy list, and no consent trail. At 2,800 you cannot. Mailbox providers start forming an opinion about you, and by the time you notice the opinion is bad it is expensive to change.

So the work was not a deliverability rescue. It was making sure one would never be needed.

---

## What I did

**Authentication.** Configured SPF, DKIM, and DMARC so receiving servers could verify that mail claiming to come from the client actually did. Without these, mail from a growing sender looks exactly like mail from someone spoofing that sender.

**Sending domain.** Verified that campaigns were going out from the authenticated domain rather than a generic or mismatched address. This is the part that is easy to get wrong quietly. Everything looks fine in the platform, the mail still sends, and the reputation being built accrues to the wrong place or to nowhere.

**Consent.** Implemented double opt in so every address on the list had a verifiable moment of agreement behind it, and put a one click unsubscribe in the footer of every send. The unsubscribe matters more than it looks. A person who cannot find the unsubscribe hits the spam button instead, and a spam complaint costs far more than a lost subscriber.

**List hygiene.** Removed contacts showing no engagement over time. Cleaned column mapping on list uploads so imported data landed in the right properties rather than creating malformed records that would later fail or misfire in segmentation.

**Engagement based sending.** Built suppression so contacts who stopped engaging stopped receiving campaigns until they re initiated on their own. This is the piece most programs skip. Continuing to mail people who ignore you is the fastest way to teach a mailbox provider that your mail belongs in spam, and it degrades delivery for the people who do want to hear from you.

---

## Result

Send volume grew from a prior maximum of 200 recipients to over 2,800. On a representative campaign at that volume, 2,716 of 2,818 messages were delivered, with 8 bounces, 6 unsubscribes, and no spam complaints recorded.


---

## Tools

HubSpot, Google Tag Manager, Google Analytics

