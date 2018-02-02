**Note**: This is a work in progress.

# Mobile application content management using Watson Content Hub and IBM Mobile Foundation

Certain mobile apps need ongoing authoring of the content displayed on them like an healthcare app allowing doctors to post new content to his patients such as seasonal precautions or diet. Subject matter experts (like the doctors in healthcare app) should be able to author new content or edit existing ones using an intuitive interface such as WYSIWYG editors on their tablets/ desktop browsers. The new/updated content should get pushed to user’s mobile apps without needing any app rebuild/version update.
This IBM code pattern shows how to leverage Watson Content Hub (a cloud-based content management system) and IBM Cloud mobile services to easily build such mobile apps that need ongoing authoring of the content displayed on them.

<img src="doc/source/images/Architecture.png" alt="Architecture diagram" width="1200" border="10" />

1. When the user launches the mobile app, a call is made to MobileFirst adapter to fetch the app content.
2. MobileFirst adapter fetches the content from Watson Content Hub and returns it to the mobile app for displaying to user.
3. Content author logs in to Watson Content Hub and creates a new content or updates an existing one.
4. The MobileFirst adapter which keeps polling Watson Content Hub for changes, notices the content change.
5. The MobileFirst adapter which noticed the content change, sends a Push notification to the mobile app with the ID of the new/updated content.
6. Users see a push notification in the notification bar informing them of the new/updated content. If user clicks on the push notification, the mobile app is launched and the new/updated content is fetched from Watson Content Hub and shown to the user.
