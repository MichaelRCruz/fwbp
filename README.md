# $ firebase deploy --only hosting:your-career-2

IMAGE

## Why?

Learn to deploy an application to three seperate URLs from a single repository because the secret to hosting any React application with Firebase hosting is easy - know exactly where your `index.html` is relative to the `build/`.

## How to get started with firebase in the terminal?

Clone the repo for the starter code with the following command to get set up if you're not already working with a project.

```terminal
$ npx create-react-app your-career && cd your-career
```

## How to set up hosting in firebase console?

1. Head to the Firebase console and create a project or change into one you already have.

2. After giving the project a name, enabling Google Analytics, agreeing to the terms and conditions, finally click through to reveal your project's config page.

3. Head to the firebase hosting page in the console. Get there via the side menu under Develop and then click Hosting.

4. There, on the hosting landing page click Get Started with hosting by clicking through. You'll be invited to set up the SDK, but not needed. In fact take note of all CLI _suggestions_, but it's okay to continue past.

5. You're done here, but know you can add an additional url on the hosting page if needed.

## How to add an app to a Firebase project?

1. Head to the project overview page by clicking the settings icon next to "project Settings" in the top left.

2. In the area titled, "Your Apps" towards the bottom of the screen, select a web app as the type of app. It's the option directly to the right of Android.

3. Give your app a nickname, try to keep this the same as your app id, and the url name if possible.

4. Check the box to choose hosting for your app, but make sure the selection matches your intended url. The dropdown seems easy to miss at times.

4. Click register app, SDK is not required now.

5. Again, click next, but this time copy the CLI command to your clip board, move to the next step and click "Continue to Console." to finish.

6. Make sure to have the CLI installed for the next section by pasting to the terminal or by typing `npm install -g firebase-tools`. 

### #fwbp - CLI

Hey,

Update your CLI as much as you can remember within reason. For any CLI, when they're new or just out of beta, the software updates are more frequent and have more of an impact compared to later updates across the tool's lifetime. There will be a time, when you're pulling your hair out, but forgot to update the CLI. A good example is Zeit.

### #fwbp - Firebase projects

Hey,

Firebase projects are basiclaly Google Cloud Platform (GCP) projects. A project can have _many_ apps, but for _any_ one app, keep it isolated to one project. In other words try to maintain a set of related apps together in one place.

For example, you have an Android app, two web apps, and a iOS app. These should be developed under _one_ project id. Remember that the project name you chose at the start is _usually_ your project id throughout GCP.

For programmers, please remember best practices expecially regarding naming conventions. You'll find that a consistant naming pattern will save you time and energy when reasoning your way through other surfaces of your system within Firebase and GCP. This is a much larger universe with way more stuff racing through orbit.

## How to use the Firebase CLI with React?

INSERT VIDEO

1. Install Firebase CLI or make sure it's updated with `npm install -g firebase-tools`.
2. Verify that you're logged in with `firebase login`.
3. Configure Firebase for your project via the CLI by running `firebase init`.
4. Make your selections and be sure to define the correct build folder name when asked. Select `yes` for setting up rewrites, and for those with an existing project, select `no` when asked if you would like to overwrite your existing `index.html`.

A more sophisticated project that includes additional Firebase features, will have additonal configuration questions. If you mess up, my hint is to use git obviously, but also know that you need to make sure the Firebase CLI is _itself_ configured to use your intended project. Run the following to be sure.

```
$ firebase use your-career
```

## How to write a simple firebase.json file for React.

1. Navigate to your text editor to modify the manifest.json to allow your app to work out of it's index.html.
2. Make sure `public` is set to the same value as the name of your build folder.
3. Make sure `target` has been named appropriately.
4. Make sure your manifest.json looks like this.

```json
{
  "hosting":
  {
    "target": "your-project",
    "public": "build",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "appAssociation": "AUTO",
    "rewrites": [
      {
        "source": "**",
        "destination": "build/index.html"
      }
    ]
  }
}
```

## How to test Firebase locally.

1. Don't forget `npm i`.
2. Run `npm run build` takes time sometimes :)
3. Run `firebase serve`. Read the logs. This is your static server usually on 5000
4. Shut down server via ctrl + c when needed.

If you're ready for deployment, proceed.

## How to deploy using deploy targets in Firebase.

1. Apply a deploy target to a project by running the below command. Yes, the duplication of `your-career` is intentional. One represents the url and the other represents the app nickname.

```terminal
$ firebase target:apply hosting your-career your-career
```

2. Deploy by running `firebase deploy --only hosting:your-project`
3. Visit your-career.web.app
