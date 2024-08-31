# G-Forms Webhook

This script allows you to send Google Forms submissions to Discord via webhooks. You can configure the webhook settings to customize how the information is posted to your Discord channel.

## Features

- **Send Submissions to Multiple Webhooks**: Configure multiple Discord webhooks to receive form submissions.
- **Customizable Messages**: Set a custom title, avatar image, description, color, and mention for the message.
- **Flexible Formatting**: Choose between sending data as plain text or an embedded message.
- **Bonus Features**:
  - Convert links to clickable URLs.
  - Convert Discord IDs to mentions.

## Getting Started

1. **Create Your Google Form**: Set up your Google Form as usual.
2. **Set Up Webhooks**: Obtain the webhook URLs from Discord and add them to the script.
3. **Configure Script**: Customize the script to fit your needs (title, avatar, description, etc.).
4. **Deploy**: Save and deploy the script to Google Apps Script.

## Script Configuration

### Webhook URLs

Specify your Discord webhook URLs in the `webhooks` array:

```javascript
const webhooks = ["WEBHOOK_URL_1", "WEBHOOK_URL_2"];
```

### Customizable Settings

- **Title**: Set a custom title for the Discord message. If left blank, the form title is used.
  
  ```javascript
  const title = "Custom Title";
  ```

- **Avatar Image**: URL of the image to be used as the thumbnail in the embed. It must be a direct link.
  
  ```javascript
  const avatarImage = "https://example.com/image.png";
  ```

- **Short Description**: A brief description to include with the submission data.
  
  ```javascript
  const shortDescription = "Description of the form submission";
  ```

- **Color**: Hex color code for the embed's sidebar. If left blank, a random color will be chosen.
  
  ```javascript
  const colour = "#FF5733";
  ```

- **Mention**: Specify a user or role to mention in the message. Use the format `<@USER_ID>` or `<@&ROLE_ID>`.
  
  ```javascript
  const mention = "<@!123456789012345678>";
  ```

- **Type**: Choose between "TEXT" or "EMBED" for how the submission is sent to Discord. Default is "EMBED".
  
  ```javascript
  const type = "EMBED";
  ```

### Bonus Features

- **convert2Link**: Convert URLs in the message to clickable links (default: ON).
  
  ```javascript
  const bonusFeatures = {
    convert2Link: 'ON',
  };
  ```

- **convert2Mention**: Convert Discord IDs in the response to mentions (default: OFF).
  
  ```javascript
  const bonusFeatures = {
    convert2Mention: 'OFF',
  };
  ```

## Code Breakdown

1. **Fetch Responses**: The script retrieves the latest form submission.
2. **Validate Webhooks**: Checks if the provided webhooks are valid Discord webhook URLs.
3. **Process Responses**: Converts the responses into a format suitable for Discord messages.
4. **Send Data**: Sends the formatted data to the specified webhooks, either as plain text or an embed.

### Sending Data

- **Plain Text**:

  ```javascript
  function plainText() {
    // Function to send plain text message
  }
  ```

- **Embed Text**:

  ```javascript
  function embedText() {
    // Function to send an embedded message
  }
  ```

## Error Handling

- Ensure that you have set at least one valid webhook URL.
- Check that image URLs for avatars are direct links.
- Be aware of Discord's message length limit (2000 characters).

## Troubleshooting

- **No Responses Found**: Ensure that your form has submissions.
- **Invalid Webhook URL**: Verify that your webhook URLs are correctly formatted.
- **Image URL Issues**: Ensure your avatar image URL ends with an image file extension.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. This script is provided as-is. Use it at your own risk and ensure compliance with Discord's terms of service and API guidelines.

## Contact

For further assistance, feel free to open an issue on the GitHub repository or contact the script maintainer.