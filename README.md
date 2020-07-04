# amplify-sns-fedaration

> ID-Fedaration Sample with AWS Amplify on Vue.js

## Required

- yarn

```
yarn -v
1.22.4
```

- Amplify CLI

```
amplify -v
4.21.3
```

- AWS Account

## ID-Fedaration Target

- Google
- LINE
- FaceBook

## Amplify Project setup

### Configure

```
amplify configure
```

#### Sign in to your AWS administrator account

```
$ amplify configure
Follow these steps to set up access to your AWS account:

Sign in to your AWS administrator account:
https://console.aws.amazon.com/
Press Enter to continue
```

> Press Enter

### Specify the AWS Region

```
Specify the AWS Region
? region:
  eu-west-1
  eu-west-2
  eu-central-1
❯ ap-northeast-1
  ap-northeast-2
  ap-southeast-1
  ap-southeast-2
```

### Specify the username of the new IAM user:

- If you have already created an IAM user, skip the user creation and proceed (Press Enter)
- If no IAM user is created, proceed with the default (Press Enter)

```
Specify the username of the new IAM user:
? user name:  amplify-laWUg
```

### Complete the user creation using the AWS console

```
Complete the user creation using the AWS console
https://console.aws.amazon.com/iam/home?region=undefined#/users$new?step=final&accessKey&userNames=amplify-laWUg&permissionType=policies&policies=arn:aws:iam::aws:policy%2FAdministratorAccess
Press Enter to continue
```

> Press Enter

### Enter IAM Secret

```
Enter the access key of the newly created user:
? accessKeyId:  ********************
? secretAccessKey:  ****************************************
```

### This would update/create the AWS Profile in your local machine

```
This would update/create the AWS Profile in your local machine
? Profile Name:  (default)
```

### Setup AWS Resource

```
amplify init
```

> Specify the AWS profile you specified earlier, and enter the following to proceed.

```
$ amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project amplifysnsfedaration
? Enter a name for the environment prod
? Choose your default editor: Visual Studio Code
? Choose the type of app that you're building javascript
Please tell us about your project
? What javascript framework are you using vue
? Source Directory Path:  src
? Distribution Directory Path: dist
? Build Command:  yarn build
? Start Command: yarn serve
Using default provider  awscloudformation

For more information on AWS Profiles, see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-multiple-profiles.html

? Do you want to use an AWS profile? Yes
? Please choose the profile you want to use amplify-xxxxx
```

### Add Auth Module

```
amplify add auth
```

> Enter the Client ID and Secret that you obtained in advance on GCP to proceed

```
% amplify add auth
Using service: Cognito, provided by: awscloudformation

 The current configured provider is Amazon Cognito.

 Do you want to use the default authentication and security configuration? Default configuration with Social Provider (Federation)
 Warning: you will not be able to edit these selections.
 How do you want users to be able to sign in? Email
 Do you want to configure advanced settings? No, I am done.
 What domain name prefix do you want to use? amplifysnsfedaration8a671f45-8a671f45
 Enter your redirect signin URI: http://localhost:8080/
? Do you want to add another redirect signin URI No
 Enter your redirect signout URI: http://localhost:8080/
? Do you want to add another redirect signout URI No
 Select the social providers you want to configure for your user pool: Google

 You've opted to allow users to authenticate via Google.  If you haven't already, you'll need to go to https://developers.google.com/identity and create an App ID.

 Enter your Google Web Client ID for your OAuth flow:  <Enter your Google Web Client ID>
 Enter your Google Web Client Secret for your OAuth flow:  <Enter your Google Web Client Secret>
Successfully added resource amplifysnsfedaration66e13a9f locally

Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud
```

## 参考リンク

- Amplify を利用した開発

  - [AWS 怠惰なプログラマ向けお手軽アプリ開発手法](https://feature-webpush.dma9ecr5ksxts.amplifyapp.com/)

- Google 側の連携設定
  - [Google アカウントの連携を有効にする](https://qiita.com/poruruba/items/189945dc64edfe1f2464#google%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B)
