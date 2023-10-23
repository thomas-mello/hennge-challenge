# Challenge Details

Suppose you have just joined a team responsible for developing an `Email Audit` system.
Assume that this project is a real project and is being used in a production
environment on a trial basis (since the features are not yet complete).

As your first assignment, you are tasked with implementing a component called `RecipientsDisplay`,
to intelligently show email recipients inside the `AuditTable` component.
We have prepared a barebones `RecipientsDisplay` component in three different frameworks.
Your task is to update the component in any one of the frameworks to add this functionality.

## `RecipientsDisplay` component requirements

Assume that an employee can send an email to many recipients.
Due to the limited amount of space, we want to make sure the information is displayed well.
Our design team has come up with the following specs:

- If all the recipient email addresses fit in the available space, we can simply display them delimited by a comma and space (e.g. `a, b`).
- When there is not enough space to display all recipients, we trim the text. However, to prevent showing clipped email addresses that are hard to read, we trim entire email addresses. If we cannot fit the entirety of a recipient email address, it shouldn't be shown at all.
- When at least one recipient is trimmed, we put a comma, space, and ellipsis after the last fitting recipient (e.g. `a, b, ...`). Furthermore, the rightmost end of the column should show a "badge" with the number of trimmed recipients (`+N`).
- If there is not enough space to show even the first recipient, the badge should show the number of trimmed recipients excluding the first recipient, and the recipient should be truncated with an ellipsis only. If there is only one recipient, there will be no badge, and the recipient should still be truncated by an ellipsis.
- This functionality should work on any screen size. For simplicity, this will only be tested in a recent version of the Chrome browser.

### Examples

#### Trim recipients that do not fit in the column.  Show `, ...` after the last fitting recipient and a badge with `+N` at the end of the column.

![Email trim example 1](Email%20trim%20example%201.svg)

#### If there is not enough space to show the ellipsis and the extra space, trim that recipient, too.

Incorrect:

![Email trim example 2A](Email%20trim%20example%202A.svg)

Correct:

![Email trim example 2B](Email%20trim%20example%202B.svg)

#### If there is not enough space to show the first recipient, the badge should show the number of trimmed recipients excluding the first recipient, and the recipient should be truncated with an ellipsis only. If there is only one recipient, there should be no badge.

Two recipients:

![Email trim example 3A](Email%20trim%20example%203A.svg)

One recipient:

![Email trim example 3B](Email%20trim%20example%203B.svg)

## Measurements

![Badge measurements](Badge%20measurements.png)

- Font size: 16px
- Foreground color: #f0f0f0
- Background color: #666666
- Border radius: 3px
- Top padding: 2px
- Bottom padding: 2px
- Left padding: 5px
- Right padding: 5px

![Cell measurements](Cell%20measurements.png)

- Font size: 16px
- Foreground color: #333333
- Top padding: 5px
- Bottom padding: 5px
- Left padding: 10px
- Right padding: 10px
