# Visual Studio Codespaces

Welcome to Visual Studio Codespaces! This environment provides you with a full-fidelity development experience, that is accessible from anywhere. It's the same Visual Studio Code experience you already know and love, only powered by the cloud 💙 ☁️

Clone a repo, edit some code, [spin up a terminal](https://docs.microsoft.com/en-us/visualstudio/online/how-to/vscode#using-the-integrated-terminal) and then [start debugging](https://docs.microsoft.com/en-us/visualstudio/online/how-to/vscode#port-forwarding). When you're done working, we'll automatically suspend the environment, so you only pay for the time you actually use it (down to the second!) 👍

If you're working on multiple projects, then go ahead and create multiple environments. You can quickly switch between them, knowing that each one has its own dedicated resources. Additionally, feel free to spin up environments for ad-hoc tasks such as reviewing a PR or doing some pair programming with a colleague. With Visual Studio Codespaces, you can eradicate setup from all of your everyday tasks 🔥 🙌

## Helpful Resources

* [What is Visual Studio Codespaces?](https://docs.microsoft.com/en-us/visualstudio/online/overview/what-is-vsonline)
* [How-to Guide: VS Code](https://docs.microsoft.com/en-us/visualstudio/online/how-to/vscode#install)
* [How-to Guide: Browser](https://docs.microsoft.com/en-us/visualstudio/online/how-to/browser#create-an-environment)
* [Environment configuration](https://docs.microsoft.com/en-us/visualstudio/online/reference/configuring)
* [Environment personalization](https://docs.microsoft.com/en-us/visualstudio/online/reference/personalizing)

If you run into any problems, see our [troubleshooting documentation](https://docs.microsoft.com/en-us/visualstudio/online/resources/troubleshooting) for potential workarounds. Additionally, if you have any questions and/or feedback, please don't hesitate to reach out to the team on [GitHub](https://github.com/MicrosoftDocs/vscodespaces).


## 2. React Native 프로젝트 생성
- npm install -g react-native-cli
- cd ..
- react-native init worksapce

## 3. Android SDK 설치
- cd ~
- wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip
- unzip commandlinetools-linux-6609375_latest.zip
- rm commandlinetools-linux-6609375_latest.zip
- mkdir android-sdk
- mv tools android-sdk/tools

## 4. PATH 설정 (.bachrc에 추가)
- export ANDROID_HOME=$HOME/android-sdk
- export PATH=$PATH:$ANDROID_HOME/tools/bin
- export PATH=$PATH:$ANDROID_HOME/platform-tools

## 5. PATH 설정 후
- source .bashrc

## 6. SDK 설치
- project_root/android/build.gradle 을 통해 Android 버전 확인
- 확인 후 아래 명령어를 통해 Android 28버전 설치
- sdkmanager --sdk_root=${ANDROID_HOME} "platform-tools" "platforms;android-28"

7. apk 빌드 및 생성
- 빌드
workspace/android/.gradlew assembleDebug
- 생성 위치 : workspace/android/app/build/outputs/apk/debug/

8. Git 저장소에 업로드
- APK 파일을 저장소에 업로드(프로젝트가 GitHub에 업로드 되어 있을 경우)
git add workspace/android/app/build/outputs/apk/debug/apk_name.apk
- Commit & Push
