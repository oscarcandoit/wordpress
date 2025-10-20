---
url: https://www.advancedcustomfields.com/resources/conditional-logic
scraped_at: 2025-10-20T02:27:05.936Z
---

# Conditional Logic

Last updated Oct 2, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#overview)

## Overview

Link copied

Conditional logic allows you to set rules regarding when a custom field should appear, based on the values of other fields in the same field group. The “Conditional Logic” setting tab is available for most ACF field types, giving you a great degree of control in how fields are presented to content editors.

Conditional logic in ACF is typically applied _within_ a field group. It does not control where the field group itself will appear, which is handled by the [Location Rules](https://www.advancedcustomfields.com/resources/creating-a-field-group/#location) in the field group’s settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#screenshots)

## Screenshots

Link copied

![This screenshot shows the field group “Author Info”, which contains three fields: a Text field labeled “Author Name”, an Email field, and an Image field labeled “Author Image.” Conditional logic settings are shown for the Email and Image fields, indicating they will only appear when a value has been entered in the “Author Name” field. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/Conditional-Logic-Example-Screenshot.png)

Email and Image fields with conditional logic settings applied so they will only appear when a user enters a value in the “Author Name” field.

![The first of two screenshots of a post being edited in WordPress with the “Author Info” field group displayed. In this screenshot, the “Author Name” field is blank, and no other fields are showing.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Conditional-Logic-Fields-NOT-Displayed-1.png)

The “Author Name” field as it appears to content editors before entering input.

![In the second screenshot, a value has been entered for “Author Info”, and the Email and Image fields are now visible and ready to receive input.  ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Conditional-Logic-Fields-Displayed-1.png)

Conditional logic in action. The user has entered a value for “Author Name”, causing the other fields in the group to display.

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#basic-usage)

## Basic Usage

Link copied

The “Conditional Logic” tab initially presents you with a single toggle, allowing you to turn it on. You can do this with any field, even the first field in a newly created field group. However, you would not be able to build rules in this case, as there are no other fields present on which to base them.

![The Conditional Logic tab of an unlabelled Text field in a field group where no other fields are present. The dropdowns for creating rules are visible, but the selections will remain blank until at least one more field is created.](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Blank-Rule-1.png)

Each conditional logic rule consists of three dropdowns. Clicking the first dropdown menu displays a list of the fields currently in the field group. The second dropdown defines the condition that must be met. The third dropdown further defines these conditions with specific values.

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#conditions)

### Conditions

Link copied

There are six possible conditions you can choose from when creating these rules. The conditions that appear are based on the type of field selected in the first dropdown. Some fields cannot possibly meet certain conditions, so those options are not shown when applying logic based on those fields.

- Has any value
- Has no value
- Value is equal to
- Value is not equal to
- Value matches pattern
- Value contains

If you can’t define values or choices when creating the field, you cannot provide specific values or patterns when using conditional logic. The only “value” that can be read in this case is whether or not the field has received input.

For example, choosing **Image** in the first dropdown will limit you to choosing between **Has any value** and **Has no value** in the second. This is because the “value” of an Image field is based on whether or not it has content. The condition is fulfilled as long as an image is present (or not). You can ensure that the image itself meets certain specifications by making adjustments to the Image field’s Validation settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#setting-multiple-rules)

### Setting Multiple Rules

Link copied

The precise method you use to add additional rules depends on your objective. Multiple rules for conditional logic in ACF follow the “and/or” principle. If you want two or more conditions to be fulfilled, you would use “and.” You would use “or” for situations where _any_ of the conditions being met is sufficient for your purposes.

Click **and** at the end of any rule to duplicate it. Modify the new rule as usual via the dropdown menu, and click **Save Changes** to save it to your field group. This will ensure _both_ rules are followed for the condition to be met.

![Conditional logic in ACF using multiple rules. In this case, both the “Author Info” field and the Email field must contain a value for the Image field to be displayed.](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Setting-AND-Rules.png)

Click **Add rule group** below the current rule to add an “or” rule. Make your selections from the dropdown menus, and click **Save Changes**. In this case, the conditional logic will be applied if _either_ condition is met.

![Another view of conditional logic in ACF using multiple rules. In this case, either the “Author Info” field or the Email field must contain a value for the Image field to be displayed. As long as there is a value in at least one of those fields, the Image field will be shown. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Setting-OR-Rules.png)

To remove rules, hover over the end of the rule and click the minus sign when it appears.

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#contradictory-conditional-logic)

### Contradictory Conditional Logic

Link copied

Care must be taken when using the conditional logic settings, as there are cases where it’s possible to set up rules that contradict each other.

For example, you can configure a rule that says a particular condition is filled only when a [True/False](https://www.advancedcustomfields.com/resources/true-false/) field is both checked and not checked. This is clearly impossible to fulfill.

![A conditional logic setting with two mutually exclusive rules. The first indicates that the condition is fulfilled when a True/False checkbox is checked, and the second indicates that the condition is fulfilled when the checkbox is left unchecked. Because these were created as “and” rules, the conditions can never be fulfilled. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/Conditional-Logic-Contradictory-Rule-for-Checkbox.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#how-to-use-conditional-logic)

## How to Use Conditional Logic

Link copied

This short tutorial demonstrates how to use conditional logic to give content editors the most suitable field based on a previous selection they have made. The first step is to [create a field group](https://www.advancedcustomfields.com/resources/creating-a-field-group/#) called “Event Details” with the following fields:

- A [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/) field
- A [Date Time Picker](https://www.advancedcustomfields.com/resources/date-time-picker/) field
- A [Google Map](https://www.advancedcustomfields.com/resources/google-map/) field
- A [URL](https://www.advancedcustomfields.com/resources/url/) field

![An ACF field group with four fields: a Radio Button labeled “Event Type”, a Date Time Picker labeled “Event Date and Time”, a Google Map field labeled “Event Map”, and a URL field labeled “Event Link”.](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Event-Details-Field-Group-1.png)

Next, click on the **Radio Button field** and give it a descriptive label like “Event Type.” Fill in two entries in the **Choices** box: Physical and Virtual. You’ll use these options as the basis for your conditional logic.

The only change you’ll need to make to the Date Time Picker field is to give it a label like “Event Date and Time.” It will appear for both types of events, so there’s no reason to use conditional logic just yet.

The last two fields, Google Map and URL, are where you’ll define the conditional logic settings. Assign a label like “Event Map” to the Google Map field, and click on the **Conditional Logic** tab.

Click the **Conditional Logic** switch to set the first rule. The first dropdown defaults to the first field listed in the group, but you can click on it to change this to a different field. In this case, leave it set to **Event Type**. Click the second dropdown and select **Value is equal to**. Finally, click the third dropdown and select **Physical**.

Next, click the **and** button at the end of the rule to add a second rule. This time, set the first dropdown to **Event Date and Time**, and the second to **Has any value**. This will ensure content editors do not see the Google Map field until they have selected the type of event _and_ indicated the time and date.

![Two conditional logic rules are set for the Google Map field, ensuring it will only appear to content editors after they have entered the event type as well as the date and time. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Event-Map-Rules.png)

The last step is to set up a similar rule for the URL field. Open the field, and assign a label like “Event Link”. Click on the **Conditional Logic** tab and repeat the process from above, but this time set the third dropdown to **Virtual**.

Alternatively, you could set the second dropdown to **Value is not equal to**, and leave the third set to **Physical.** This would allow you to create more types of virtual events in the “Event Type” Radio Button, while ensuring that only physical events display the Google Map field and all virtual events display the URL field.

![The conditional logic for the URL field only requires one rule. In this case, it will display the field when a content editor selects "Virtual" in the Radio Button field. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Event-Link-Rules-1.png)

Finally, click **Save Changes** to save the new conditional logic rules to your field group. You can start a new post to see the conditional logic in action.

![A view of the WordPress post editor, showing some of the new custom fields. The editor has selected a Physical event and entered the date and time, so the Google Map field is displayed. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/ACF-Conditional-Logic-Tutorial-End.png)

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/conditional-logic/#related)

## Related

Link copied

- Choice: [Select](https://www.advancedcustomfields.com/resources/select/)
- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)
- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/conditional-logic/#)