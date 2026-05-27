# Visual Assets for lib-js

This document is a sub-part of the [Open Pryv.io assets](https://github.com/pryv/assets-open-pryv.io) documentation.

It describes the visual assets used by the [Pryv JavaScript Library](https://github.com/pryv/lib-js). 

## Content of `lib-js` assets properties

```json
{ 
  "lib-js": {
    "buttonSignIn": {
      "css": "lib-js/buttonSignIn.css",
      "html": "lib-js/buttonSignIn.html",
      "messages": "lib-js/buttonSignInMessages.json"
    }
	}
}
```

### ButtonSignIn

#### Definitions

- **html** The HTML code representing the Button
- **css** The CSS code related to the Button
- **messages** To customize the different messages depending on the state of the Auth Process
  - LOADING: During the loading of the button (Usually not visible as the loading takes less that 150ms)
  - ERROR: Display on Error
  - LOGIN: Text displayed when a Login is required
  - LOGOUT_CONFIRM: Text displayed in an alert message box to confirm Log-out

#### Files

- **buttonSignIn.css** CSS content (declared by `css` property)
- **buttonSignIn.html** HTML content (declared by `html` property)
- **buttonSignIn.png** Image for the button for non CSS3 compatible browsers
- **buttonSignInLogoOnly.png** Image for the button for CSS3 compatible browsers
- **buttonSignInMessages.json** Messages definitions (declared by `messages` property)