# ClassHub: turning a class parent's laptop-bound admin work into a one-touch phone app

**Case study by Elle Tsao** · Discover → Design → Build → Improve

> As a class parent for a 2nd-grade class, I designed and built ClassHub, a private web app for our parent community. It replaced scattered information and hand-written emails and reminders with one place for dates, volunteer sign-ups, the class directory and announcements, with most of the communication automated or sent with one touch from a phone. It went from idea to live with real families in days, and it's been improved every week since based on how parents and admins actually use it.

*The source code is private. This page describes the problem, the solution and the results. A printable version is in [ClassHub-Case-Study.pdf](ClassHub-Case-Study.pdf).*

---

## The problem

I'm the class parent, which is a small-operations job done in spare time. Before ClassHub, the work had two big problems:

- **Nothing was in one place.** The roster, important dates, volunteer needs and birthdays lived in different spreadsheets, forms and message threads.
- **Every email and reminder was written by hand.** That included the weekly update, volunteer reminders, birthday reminders and information for the teacher, and pulling it all together meant sitting down at a laptop.

On top of that, I spent time every week answering the same questions: "When is…?", "Where do I sign up?", "Are there spots left?"

The underlying problems were **scattered information**, **manual, repetitive communication** and **work tied to a desk**. Small businesses deal with the same problems every day.

## What I did

### 1. Discover
Because I was doing the job myself, I started from my own week: what I re-typed, what I chased, and which questions parents kept asking. I also talked with other parents and co-admins about what they needed and what they worried about, mainly privacy for families and children.

### 2. Design
I kept the scope small and practical:
- **One place for everything** parents need: upcoming dates, volunteer needs, directory, announcements
- **Phone-first.** Parents use it from the home-screen icon, not a laptop.
- **Admins enter information once.** The weekly email, reminders and calendar feed are generated from it automatically.
- **Private by default.** Only families on the class roster can sign in.
- **Free to run.** It's built entirely on free tiers, so a volunteer group has no monthly bill.

### 3. Build
A working web app with two sides:

**For parents**
- Upcoming dates, with a calendar link that syncs to their phone's calendar
- One-tap volunteer sign-up and cancel, with spots left and who's going
- A class directory visible only to class families, which they can edit or hide from
- Announcements with photos, birthday-treat sign-ups and a "contact us" form
- Sign-in with a 6-digit email code, with no passwords to remember

**For class admins**
- Post announcements with a photo, and email or WhatsApp a single announcement with one tap after previewing it
- Manage the roster, dates, volunteer requests (including named roles like "Field trip chaperone"), announcements and quick links
- Copy and repeat dates and volunteer requests weekly or monthly
- Export the roster to CSV, and add co-admins and extra people such as the teacher
- One-click or fully automatic **weekly email** to every family
- **Automatic volunteer reminders** the day before, with a copy to admins

**Built-in safeguards**
- Only rostered emails can create an account, and removing a family cuts off access immediately
- The database itself enforces who can see and change what
- Volunteer slots can't be over-filled, even if two parents grab the last spot at the same moment
- Automated checks run on every change, plus an hourly site monitor that emails an alert if something breaks

### 4. Improve
After launch I kept improving it based on real use. Over the first few weeks I shipped **60+ improvements**, almost all of them prompted by parent or admin feedback. Some examples:

| What parents and admins needed | What I changed |
|---|---|
| Not forgetting what they'd signed up for | Automatic reminders the day before |
| A quick look at what's coming this week | A "Next 5 days" view on the home screen |
| Control over their family's contact details | Parents can edit or hide their own family |
| Different jobs within one event, like drivers and chaperones | Named roles inside a volunteer request |
| Sending one urgent announcement right away | Email or WhatsApp a single announcement, with a preview |

## Results

In the first three weeks after launch (late September to mid-October 2026):

- **32 families** on the roster, with **58 parent/guardian emails**
- **44 people signed in**, roughly three out of four invited parents and guardians, with no training or app store
- **55 volunteer sign-ups from 24 different parents** across **39 volunteer requests**, with no spreadsheet or group-chat tally
- **71 dates** and **10 announcements** posted once and shown everywhere: the app, the weekly email and parents' phone calendars
- Weekly emails delivered individually to each family (**116 deliveries** so far), plus automatic day-before volunteer reminders
- An estimated **3 hours 45 minutes a week** saved for the class parent:
  - **About 3 hours** from weekly emails, volunteer and birthday reminders, and sharing information with the teacher, which are now automated or sent with one touch
  - **About 45 minutes** that used to go to answering parents' questions and pointing them to dates and sign-ups, which they now find themselves
- **Run from a phone.** Directing and reminding parents now takes a few taps, where before it meant pulling everything together on a laptop.

That time now goes to supporting other parts of the class community instead of admin.

> "Just signed up using the VERY SICK [class] app. Thank you again to everyone who worked on that. It's so good and SO helpful! 🙏🙏🙏"
>
> — a parent in the class, unprompted, in the class group chat

## What it looks like

*Illustrative mockups with made-up data. To protect families' privacy, no real screens are shown.*

| Parent home | Volunteer sign-up |
|---|---|
| ![Home screen with a photo announcement](screenshots/home.png) | ![Volunteer sign-up](screenshots/volunteer.png) |

| Announcement email with photo | Admin weekly email |
|---|---|
| ![Announcement email with a photo](screenshots/announcement-email.png) | ![Weekly email preview](screenshots/weekly-email.png) |

## How it's built (for the technical reader)

Next.js and TypeScript on Vercel, with a Supabase (Postgres) database using row-level security for access control, Resend for email, and scheduled jobs for reminders and the weekly email. Automated tests and page checks run on every change through GitHub Actions. I built it using AI-assisted development, which is how one person delivered and kept improving a production app this quickly.

## Why this matters for a small business

ClassHub is a class parent tool, but the pattern is the one most small businesses need:

1. **Find the repetitive manual work** (re-typing, chasing, reminding)
2. **Enter information once** and let the system generate emails, reminders and reports from it
3. **Control who can see what**
4. **Ship something small quickly, then improve it** based on how people actually use it
