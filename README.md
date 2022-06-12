# react-native-fast-player

#### A `<Video>` component for react-native.

##### `NOTE: Currently this package supports for android platform only`

## Installation

Using npm:

```shell
npm install --save react-native-fast-player
```

or using yarn:

```shell
yarn add react-native-fast-player
```

Then follow the instructions for your platform to link react-native-fast-player into your project:

### Android installation

Linking is not required in React Native 0.60 and above.
If your project is using React Native < 0.60, run `react-native link react-native-fast-player` to link the react-native-video library.

Or if you have trouble, make the following additions to the given files manually:

#### **android/settings.gradle**

The newer ExoPlayer library will work for most people.

```gradle
include ':react-native-fast-player'
project(':react-native-fast-player').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-fast-player/android')
```

#### **MainApplication.java**

If using com.facebook.react.PackageList to auto import native dependencies, there are no updates required here. Please see the android example project for more details.
/examples/basic/android/app/src/main/java/com/videoplayer/MainApplication.java

##### For manual linking

On top, where imports are:

```java
import com.out.rn_video.RNVideoPackage;
```

Add the `RNVideoPackage` class to your list of exported packages.

```java
@Override
protected List<ReactPackage> getPackages() {
    return Arrays.asList(
            new MainReactPackage(),
            new RNVideoPackage()
    );
}
```

## Usage

```javascript
// Load the module

import VideoPlayer from 'react-native-fast-player';

// Within your render function, assuming you have a file called
// "background.mp4" in your project. You can include multiple videos
// on a single screen if you like.

<VideoPlayer
  style={{ width: 320, height: 200 }}
  play={true}
  uri="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
  controls
/>;
```

## Available Props

```javascript
 uri: string;
  play: boolean;
  style: ViewStyle;
  controls?: boolean;
  controlsTimeout?: number;
  volume?: number;
  showBuffering?: boolean;
  repeatMode?: RepeatMode;
  resizeMode?: ResizeMode;
  onBack?: Function;
  onFullScreen?: Function;
```
