# Ruby is ⌚️ing

## #inspect 2015 🇫🇷

### Boris Bügling - @NeoNacho

![20%, original, inline](images/contentful.png)

![](images/button.gif)

<!--- use Poster theme, black -->

---

![inline](images/klingon-academics.png)

![inline](images/klingon-academics-2.png)

![](images/background.jpg)

---

## CocoaPods

![](images/cocoapods.jpg)

---

## Contentful

![](images/contentful-bg.png)

---

![](images/who.gif)

---

# 💰💰💰💰

![](images/money.gif)

---

# Agenda

- ᴡᴀᴛᴄʜ
- Android Wear
- Developing for both with RubyMotion
- Building a simple app

![](images/background.jpg)

---

# ᴡᴀᴛᴄʜ

![](images/rorschach-2.gif)

---

# watchOS 1.x

- Notifications
- Glances
- WatchKit apps

![](images/background.jpg)

---

# Notifications

![inline](images/apple-notifications.png)

![](images/background.jpg)

---

# Glances

![inline](images/apple-glances.png)

![](images/background.jpg)

---

# WatchKit

![inline](images/apple-watchkit.png)

![](images/background.jpg)

---

# watchOS 2.x

- Apps run natively on the watch
- Custom complications

![](images/background.jpg)

---

# !!!

![](images/blast.gif)

---

![](images/apple-native.jpg)

---

# Complications

![inline](images/apple-complications.png)

![](images/background.jpg)

---

# Android Wear

![](images/ozymandias.gif)

---

# Android Wear

- Enhanced Notifications
- Wearable Apps

![](images/background.jpg)

---

# Enhanced Notifications

![inline](images/wear-notifications.png)

![](images/background.jpg)

---

![](images/wear-design.jpg)

---

# Wearable Apps

![inline](images/wear-apps.png)

![](images/background.jpg)

---

## => pretty much the same

![](images/manhattan-3.gif)

---

# => RubyMotion

![](images/rorschach-comic.gif)

---

![inline](images/app-comm.png)

![](images/background.jpg)

---

# Rakefile

```ruby
Motion::Project::App.setup do |app|
  [...]
  app.target 'WatchApp', :watchapp
end
```

---

# Resources

- Interface.storyboard
- Asset catalogs

![](images/background.jpg)

---

# WatchApp/Rakefile

```ruby
[...]

require 'ib/tasks'

IB::RakeTask.new do |project|
  project.resource_directories = ['watch_app']
end
```

---

# Extension Delegate

```ruby
class ExtensionDelegate
  def applicationDidFinishLaunching
  [...]
  end

  def applicationDidBecomeActive
  [...]
  end

  def applicationWillResignActive
  [...]
  end
end
```

---

# Interface Controller

```ruby
class InterfaceController < WKInterfaceController
  extend IB

  def initWithContext(context)
    if super
      [...]
      self
    end
  end

  def willActivate
  [...]
  end

  def didDeactivate
  [...]
  end
end
```

---

# WKInterfaceController

- Navigation
- Presentation
- Handoff
- Handle notification actions
- Communicate with parent app

![](images/background.jpg)

---

# Running the app in the sim

```bash
rake watch
```

![](images/background.jpg)

---

## Android Wear isn't really supported, yet

![](images/manhattan-2.gif)

---

# Building a simple app

![](images/rorschach-1.gif)

---

![inline](images/keynote-watch-app.png)

![](images/background.jpg)

---

# WatchPresenter

- Remote controls Deckset instead
- Direct connection to the Mac
- Shows a preview of the slides
- Measures heartrate to display the "most exciting" slide
- Taps you if you're running out of time

![](images/background.jpg)

---

## Multipeer Connectivity!

![](images/somebody-knows.gif)

---

# Available Frameworks

![](images/rorschach-3.gif)

---

CFNetwork.framework
ClockKit.framework
Contacts.framework
CoreData.framework
CoreFoundation.framework
CoreGraphics.framework
CoreLocation.framework
CoreMotion.framework
EventKit.framework
Foundation.framework

![](images/nite-owl.gif)

---

HealthKit.framework
HomeKit.framework
ImageIO.framework
MapKit.framework
MobileCoreServices.framework
PassKit.framework
Security.framework
UIKit.framework
WatchConnectivity.framework
WatchKit.framework

![](images/comedian.gif)

---

# BT APIs are private :(

![](images/cry.gif)

---

# Other options

- `NSURLSession` via Wi-Fi
- WatchConnectivity.framework to talk via the phone

![](images/background.jpg)

---

# HealthKit.framework

- not usable in the Watch simulator

![](images/skeleton.gif)

---

# Taptic Engine

```objectivec
typedef NS_ENUM(NSInteger, WKHapticType) {
    WKHapticTypeNotification,
    WKHapticTypeDirectionUp,
    WKHapticTypeDirectionDown,
    WKHapticTypeSuccess,
    WKHapticTypeFailure,
    WKHapticTypeRetry,
    WKHapticTypeStart,
    WKHapticTypeStop,
    WKHapticTypeClick
} WK_AVAILABLE_WATCHOS_ONLY(2.0);
```

```ruby
WKInterfaceDevice.currentDevice.playHaptic(WKHapticTypeStart)
```

---

### but also not usable in the sim

![](images/what-happened-to-dream.gif)

---

# Demo

![](images/dream-came-true.gif)

---

# Tips

![](images/end-is-nigh.gif)

---

# `printf` debugging is great!


![](images/joke.gif)

---

# MMWormhole

- watchOS 1.0: `CFNotificationCenter`
- watchOS 2.0: WatchConnectivity.framework

![](images/minutemen.gif)

---

# Force quit apps

- Long press until "reboot" menu
- Long press again

![](images/background.jpg)

---

## If in doubt, reboot the watch :)

![](images/background.jpg)

---

# What have we learned?

- 

![](images/background.jpg)

---

# Thank you!

![](images/explosion.gif)

---

- https://developer.apple.com/watch/human-interface-guidelines/
- https://developer.apple.com/library/prerelease/watchos/documentation/General/Conceptual/AppleWatch2TransitionGuide/
- https://developer.android.com/wear/index.html
- https://github.com/shu223/watchOS-2-Sampler
- http://www.kristinathai.com/category/watchkit/
- http://www.slideshare.net/peterfriese/introduction-to-android-wear

![](images/manhattan-1.gif)

---

![](images/save-us-no.gif)

---

@NeoNacho

boris@contentful.com

http://buegling.com/talks

![](images/manhattan-1.gif)
