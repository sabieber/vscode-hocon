# Publishing

The extension is published manually to both the VS Marketplace and Open VSX, using the same `.vsix`.

1. Bump `version` in `package.json`, commit and push.
2. Build the package:
   ```sh
   npx @vscode/vsce package
   ```

### VS Marketplace

* Open the [publisher management page](https://marketplace.visualstudio.com/manage/publishers/sabieber).
* On the HOCON extension, choose `…` → **Update** and upload the `.vsix`.

### Open VSX

* One-time setup:
  * Log in to [open-vsx.org](https://open-vsx.org) with GitHub.
  * Create an [Eclipse account](https://accounts.eclipse.org) with the GitHub username set in its profile.
  * In the [Open VSX profile settings](https://open-vsx.org/user-settings/profile), link the Eclipse account and sign the Publisher Agreement.
* Generate a token in the [Open VSX access token settings](https://open-vsx.org/user-settings/tokens), then:
  ```sh
  OVSX_PAT=<token> npx ovsx publish HOCON-<version>.vsix
  ```
* Check the result on the [extension page](https://open-vsx.org/extension/sabieber/HOCON).
