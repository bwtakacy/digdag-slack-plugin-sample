# Digdag Plugin for Slack Notification

Forked from original repo https://github.com/KimuraTakaumi/digdag-slack-plugin-sample.

## How to build

1. Decide the target digdag version and build digdag

2. Update build.gradle

```
$ cd digdag-plugin/example
```
Update build.gradle for target digdag version and dependencies libralies version.

3. Copy the depended digdag jars into `libs` directory

* digdag-client-X.X.X.jar
* digdag-plugin-utils-X.X.X.jar
* digdag-spi-X.X.X.jar

4. build and publish

```
$ ./gradlew clean build publish
```

This command makes local repository of this plugin jars in `build/repo` directory.

5. Test


```
$ cd ../
```

Edit plugin.dig and message.txt:

* message.txt: the message body notified to slack
* webhook: the webhook url of the target slack channel's Incoming WebHooks
* channel: the channel name to notify
* username: the username who notify
* icon_emoji: the icon for notify user

Run the dig with plugin repository path.

```
$ digdag run plugin.dig -p repository_path=/path/to/digdag-plugin-example/build/repo
```
