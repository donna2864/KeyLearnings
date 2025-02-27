# Creating a New Git Repository and Adding Files

## 1. Initialize a New Git Repository
To create a new Git repository, navigate to your project directory and run:

```sh
git init
```

## 2. Add Files to the Repository
After initializing the repository, add your project files:

```sh
git add .
```

## 3. Commit the Files
Once the files are added, commit them with a meaningful message:

```sh
git commit -m "Initial commit"
```

## 4. Add a Remote Repository
To link your local repository to a remote GitHub repository, use:

```sh
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Replace `YOUR_USERNAME` and `YOUR_REPOSITORY` with your GitHub details.

## 5. Push to GitHub
Push the committed files to GitHub:

```sh
git push -u origin main
```

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

## Adding multiple users in the same machine:
https://www.youtube.com/watch?v=6lA0oPoFCAE&ab_channel=JcMiron

# Deploying Vite + React App on GitHub Pages

Follow these steps to deploy your Vite + React app to GitHub Pages.

## Step 1: Update `vite.config.js`
Add the following line:
```js
export default defineConfig({
  base: "/repo-name/",
  plugins: [react()],
});
```

## Step 2: Update `package.json`
Modify the `package.json` file:
```json
{
  "name": "your-app-name",
  "homepage": "https://github_username.github.io/repo-name/",
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}
```

## Step 3: Install `gh-pages`
Run the following command in your terminal:
```sh
npm install --save gh-pages
```

## Step 4: Deploy the App
Run:
```sh
npm run deploy
```
Once the deployment is complete, you will see a message indicating that the app has been published.

## Step 5: Access Your App
Visit: 
```
https://github_username.github.io/repo-name/
```
At first, you may see a 404 error. Reload the page 2-3 times, and your app should appear successfully hosted on GitHub Pages!

