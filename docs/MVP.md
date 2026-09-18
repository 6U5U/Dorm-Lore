# Dorm Lore — MVP plan

## Experience

A digital dorm bulletin board with warm paper tones, bold headlines, and story cards. Mobile first: someone should be able to add a story from the hallway in under a minute.

## Core flow

1. A member enters their floor's private space.
2. They add a title, story, and date to a new moment.
3. The moment appears in the timeline.
4. Other members vote; five unique member votes makes it Legendary.

## Build order

1. Local prototype with fictional sample stories, submission, timeline, and voting. Label it as a demo; do not collect real dorm information.
2. Accounts and floor membership with expiring, revocable invitations.
3. Shared storage with server-enforced membership and one vote per member per story.
4. Reporting, author deletion, and floor-admin moderation before a real dorm pilot.
5. Optional photos and witness comments after the core pilot works.

## Data model

- Floor: ID, display name, creation date.
- Membership: floor ID, user ID, role (member or admin).
- Moment: ID, floor ID, author ID, title, story, event date, creation date.
- Vote: moment ID and user ID, unique together.
- Invitation: floor ID, token hash, expiration, usage limit, revocation status.

## Acceptance criteria for a real pilot

- Nonmembers cannot read stories, attachments, or membership lists.
- Members can submit a story and see it in date order.
- Empty titles and stories are rejected with clear messages.
- A member can toggle their vote; duplicate requests cannot create extra votes.
- The Legendary badge follows the current vote count.
- Authors can delete their own posts; admins can handle reports.
- The timeline works on a phone and supports keyboard navigation.
- Demo content is clearly fictional and kept separate from real floor content.

## Open implementation choices

Choose the application framework and hosting when building begins. Keep the initial prototype small; accounts and server-side access controls are required before describing the running app as private or invite-only.
