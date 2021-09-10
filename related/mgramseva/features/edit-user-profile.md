# Edit User Profile

mGramSeva users will be able to edit their basic information like name, add gender, email and change password through hamburger menu on any screen.

![](../../../.gitbook/assets/image%20%2819%29.png)

1. User will click on hamburger menu from any screen. A slider from left opens up.
2. User will be able to
   1. Change Language
   2. Edit profile
   3. Logout
3. Changing language will change localization as per standards
4. Edit profile will take user to next screen where changes can be made to user pfile
   1. Name - Can be changed
   2. Phone number - Cannot be changed
   3. Gender - This field is not present by default. Whatever user enters will be stored
   4. Email ID - Its an empty field. User input will be stored as user’s email id
   5. change Password - This will take user to password changing screen where old password, new password and confirm new password are to be entered as per given standards.
      1. Dynamic password validation will happen same like registration flow.
      2. Until all fields are entered, primary CTA will be disabled.
      3. Changing password will show a nudge to user “ Password updated successfully” and closing this nudge will take user to user profile screen.
   6. Clicking save will show a nudge to user” Details saved successfully”. Upon closing this user will remain on the screen but fields will show as edited.

![Edit Profile](../../../.gitbook/assets/image%20%2824%29.png)

![Change Password](../../../.gitbook/assets/image%20%2829%29.png)

