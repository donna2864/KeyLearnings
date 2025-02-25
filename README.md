# Removing Stored Git Credentials

## Clear Saved Credentials in Git
To remove stored Git credentials, use the following command:

```sh
git credential reject https://github.com
```

## Remove Stored Credentials on Windows
If you are using Windows, you may also need to remove the stored credentials from **Windows Credential Manager**:

1. Open **Control Panel**.
2. Navigate to **Credential Manager**.
3. Select **Windows Credentials**.
4. Find the entry for **GitHub**.
5. Click **Remove** to delete the stored credentials.

## Remove Stored Credentials on macOS/Linux
For macOS and Linux users, use the following command:

```sh
git credential reject https://github.com
```

If you are using a credential helper (like Keychain on macOS), you may need to clear stored credentials:

```sh
security delete-generic-password -s github.com
```

After clearing credentials, the next time you push or pull from GitHub, you will be prompted to enter your credentials again.
