# glowing-barnacle

```sh
sudo apt update
sudo apt install cpu-checker

docker run -d --cpus=4 --memory=8g -p 6080:6080 -e EMULATOR_DEVICE="Samsung Galaxy S10" -e WEB_VNC=true --device /dev/kvm --name android-container budtmo/docker-android:emulator_11.0

docker stop android-container && docker rm android-container

```

## Installing APK

To install an APK file into the running Android emulator:

1. Copy the APK to the container:
   ```sh
   docker cp /path/to/your/app.apk android-container:/app.apk
   ```

2. Install using ADB:
   ```sh
   docker exec android-container adb install /app.apk
   ```

Replace `/path/to/your/app.apk` with the actual path to your APK file on the host machine.
