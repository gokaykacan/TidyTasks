# TidyTasks

A comprehensive iOS To-Do application built with SwiftUI and Core Data, featuring full Turkish-English localization, enhanced notifications, and modern app icons.

## Current Status

🎉 **COMPREHENSIVE FEATURES COMPLETE!** - The app now includes professional app icons, enhanced notifications, complete localization, and advanced category management.

## ✨ Key Features

### 🎨 Professional App Icons
- Complete icon set for all iOS device contexts (iPhone, iPad, App Store)
- Modern, task-focused design following iOS guidelines
- Support for all resolutions and device sizes

### 🔔 Enhanced Notification System
- **Visual Priority Indicators**: 🔴 High, 🟡 Medium, 🟢 Low priority
- **Interactive Actions**: Complete, Postpone, View tasks directly from notifications
- **Rich Content**: Task notes, category info, and urgency indicators
- **Critical Alerts**: High-priority tasks use critical sound
- **Smart Categories**: Different action sets based on task priority

### 🌍 Complete Turkish-English Localization
- Full UI translation for both languages
- Dynamic language switching
- Contextual localization for priorities, recurrence, and notifications
- Professional-quality native translations

### 📁 Advanced Category Management
- **Enhanced Swipe Actions**: Edit, Delete Completed, Delete All Tasks, Delete Category
- **Smart Organization**: Trailing and leading edge actions
- **Confirmation Alerts**: Localized dialogs for destructive operations
- **Haptic Feedback**: Tactile feedback for all interactions

### 🎯 Modern User Experience
- **Smart Keyboard Dismissal**: Universal tap-to-dismiss functionality
- **Enhanced Task UI**: Modern checkbox design with premium animations
- **Priority Visual Hierarchy**: Optimized for better task scanning
- **Gesture Optimization**: Resolved tap zone conflicts
- **60fps Animations**: Smooth transitions throughout the app

### 🛠️ Technical Excellence
- **Notification Delegate**: Proper UNUserNotificationCenterDelegate handling
- **Badge Management**: Intelligent notification counting and clearing
- **Error Recovery**: Robust Core Data error handling
- **Performance Optimization**: Reduced memory usage and improved responsiveness

## 🏗️ Architecture

### Core Technologies
- **Platform**: iOS 15+ with SwiftUI
- **Data**: Core Data with CloudKit synchronization
- **Notifications**: UNUserNotificationCenter with interactive actions
- **Localization**: NSLocalizedString with .lproj bundles
- **Testing**: XCTest for unit and UI tests

### Project Structure
```
TidyTasks/
├── TidyTasks/
│   ├── Assets.xcassets/           # App icons and visual assets
│   ├── Core/
│   │   ├── TaskModel.xcdatamodeld # Core Data model
│   │   ├── CoreDataStack.swift    # Data persistence layer
│   │   ├── Models/                # Entity extensions
│   │   └── Services/              # NotificationManager, LanguageManager
│   ├── Features/                  # Main UI components
│   │   ├── ContentView.swift      # Tab navigation and task lists
│   │   ├── CustomDatePickerField.swift
│   │   └── FloatingActionButton.swift
│   ├── Views/                     # Detail views
│   │   ├── TaskDetailView.swift   # Task creation/editing
│   │   └── CategoryDetailView.swift
│   ├── Enums/                     # TaskPriority and RecurrenceType
│   ├── Extensions/                # Color, String localization
│   ├── en.lproj/                  # English localization
│   ├── tr.lproj/                  # Turkish localization
│   └── TidyTasksApp.swift         # App entry point with AppDelegate
├── TidyTasks Watch App/           # watchOS companion (structure)
├── ToDoWidget/                    # iOS widget extension (structure)
├── Share Extension/               # Share extension (structure)
├── TidyTasksTests/               # Unit tests
└── TidyTasksUITests/             # UI automation tests
```

## 🚀 Getting Started

### Prerequisites
- Xcode 15.0 or later
- iOS 17.6+ target device or simulator
- macOS Sonoma or later

### Building the App
```bash
# Clone and navigate to project
cd /path/to/TidyTasks

# Build for simulator
xcodebuild -project TidyTasks.xcodeproj -scheme TidyTasks -configuration Debug -destination 'platform=iOS Simulator,name=iPhone 16' build

# Run tests
xcodebuild -project TidyTasks.xcodeproj -scheme TidyTasks test
```

### Running in Xcode
1. Open `TidyTasks.xcodeproj` in Xcode
2. Select "TidyTasks" scheme and iOS Simulator
3. Build and run (`Cmd+R`)

## 🔧 Configuration

### Notification Testing
1. Build and run the app on a simulator or device
2. Create a task with a due date 1-2 minutes in the future
3. Background the app and wait for the notification
4. Long-press the notification to see interactive actions
5. Test Complete, Postpone, and View actions

### Language Testing
1. Go to Settings tab in the app
2. Change language between English and Turkish
3. Restart the app to see full localization
4. Create tasks and categories to test translated content

## 📱 Supported Features

### Task Management
- ✅ Create, edit, delete tasks with title, notes, and priority
- ✅ Due dates with local notifications
- ✅ Priority levels (High, Medium, Low) with visual indicators
- ✅ Subtasks and hierarchical relationships
- ✅ Task completion with progress tracking
- ✅ Search functionality and category filtering
- ✅ Swipe actions and context menus

### Category Organization
- ✅ Color-coded categories with custom icons
- ✅ Category-based task filtering
- ✅ Enhanced swipe actions (Edit, Delete Completed, Delete All, Delete Category)
- ✅ Task count display for each category
- ✅ Category management with confirmation dialogs

### Notifications
- ✅ Visual priority indicators with emojis
- ✅ Interactive action buttons (Complete, Postpone, View)
- ✅ Rich content with notes and category info
- ✅ Critical alerts for high-priority tasks
- ✅ Foreground notification presentation
- ✅ Intelligent badge counting

### Localization
- ✅ Complete Turkish-English translation
- ✅ Dynamic language switching
- ✅ Contextual localization for all UI elements
- ✅ Notification content localization
- ✅ Professional-quality translations

### Settings & Preferences
- ✅ Dark/Light mode support with system sync
- ✅ Language selection with app restart
- ✅ Notification preferences
- ✅ Show/hide completed tasks
- ✅ Data management options

## 🔄 Recent Updates (v2.2) - 🔔 NOTIFICATION SYSTEM OVERHAUL

### 🚀 Major Notification System Refactor
- **Complete NotificationManager rewrite** with enhanced reliability and performance
- **Real-time badge updates** - Badge numbers update instantly without app restart
- **Improved notification scheduling** using UNTimeIntervalNotificationTrigger for better reliability
- **30-second badge update timer** ensures continuous badge accuracy
- **App lifecycle integration** with automatic badge management
- **Enhanced debugging** with comprehensive logging and monitoring tools

### 🏷️ Smart Badge Management System
- **Accurate badge counting** - Only counts overdue tasks (past due date)
- **Real-time synchronization** - Badge updates immediately on task changes
- **Automatic badge clearing** when app becomes active
- **Memory-efficient calculation** with optimized Core Data queries
- **Error resilient** - Badge consistency maintained even during failures

### ⚡ Performance & Reliability Improvements
- **UNTimeIntervalNotificationTrigger** instead of calendar-based triggers for better timing
- **Synchronous permission checking** for instant notification authorization status
- **Automatic notification cleanup** removes stale delivered notifications
- **Background processing optimization** with proper thread management
- **Memory leak prevention** with weak references and proper observer cleanup

### 🔧 Technical Architecture Improvements
- **Centralized initialization** via `NotificationManager.shared.initialize()`
- **Observer pattern integration** for app lifecycle events
- **Convenient extension methods** for different task state changes
- **Enhanced error handling** with rollback support and consistency checks
- **Timer-based badge updates** ensure accuracy even during extended app usage

### 🎯 User Experience Enhancements
- **Instant badge updates** on task completion, deletion, and editing
- **Consistent notification behavior** across all task operations
- **Reliable notification delivery** with improved scheduling system
- **Better app responsiveness** with optimized badge calculation
- **Seamless background/foreground transitions** with automatic state management

## 🔄 Previous Updates (v2.1)

### App Icons & Visual Assets
- Added complete professional app icon set
- Support for all iOS device contexts and resolutions
- Modern task-focused design language

### Notification Enhancements
- Visual priority indicators with emoji system
- Interactive notification actions (Complete, Postpone, View)
- Rich notification content with task details
- Critical alerts for high-priority tasks

### Localization System
- Complete Turkish translation for all UI elements
- Dynamic language switching capability
- Contextual localization for priorities and system messages
- Professional-quality native translations

### Category Management
- Enhanced swipe actions with smart organization
- Delete Completed Tasks functionality
- Proper confirmation dialogs for all destructive actions
- Haptic feedback for all category interactions

### User Experience Improvements
- Universal keyboard dismissal functionality
- Modern checkbox design with premium animations
- Optimized priority visual hierarchy
- Resolved gesture conflicts and improved touch targets

### Technical Enhancements
- AppDelegate integration for notification handling
- UNUserNotificationCenterDelegate implementation
- Intelligent notification badge management
- Robust error handling and recovery systems

## 🧪 Testing

The app includes comprehensive test coverage:
- **Unit Tests**: Core Data operations, entity relationships, business logic
- **UI Tests**: User interactions, navigation, form submissions
- **Performance Tests**: Task creation, data operations, memory usage
- **Localization Tests**: String validation, language switching

## 📄 Documentation

For detailed technical documentation, see:
- [`CLAUDE.md`](./CLAUDE.md) - Complete development guide and architecture details
- Code comments throughout the project
- Inline documentation for all public APIs

## 🎯 App Features Overview

### Core Task Management
- **Task Creation**: Create tasks with title, description, priority levels, and due dates
- **Smart Organization**: Automatic categorization (Overdue, Today, Tomorrow, Upcoming)
- **Priority System**: High (🔴), Medium (🟡), Low (🟢) priority levels with visual indicators
- **Completion Tracking**: Swipe-to-complete with visual feedback and progress tracking
- **Search & Filter**: Real-time search and category-based filtering

### Category Management
- **Custom Categories**: Create color-coded categories with custom icons
- **Advanced Actions**: Edit, delete completed tasks, or delete entire categories
- **Task Organization**: Filter and organize tasks by categories
- **Visual Indicators**: Category-specific colors and task counts

### Notification System
- **Smart Notifications**: Due date reminders with priority-based styling
- **Interactive Actions**: Complete, postpone, or view tasks directly from notifications
- **Badge Management**: Real-time app icon badge updates
- **Rich Content**: Notifications include task details, notes, and category information

### Internationalization
- **Dual Language Support**: Full Turkish and English localization
- **Dynamic Switching**: Change language on-the-fly with immediate UI updates
- **Contextual Translation**: All UI elements, notifications, and system messages
- **Professional Quality**: Native-level translations for both languages

## 🛠️ Technical Specifications

### Development Environment
- **Xcode Version**: 15.0 or later
- **iOS Deployment Target**: iOS 15.0+
- **Swift Version**: Swift 5.9+
- **Architecture**: SwiftUI with Core Data

### Key Technologies
- **UI Framework**: SwiftUI with custom components
- **Data Persistence**: Core Data with CloudKit synchronization
- **Notifications**: UNUserNotificationCenter with rich interactions
- **Localization**: NSLocalizedString with .lproj resource bundles
- **Testing**: XCTest framework for unit and UI tests

### Performance Features
- **Real-time Updates**: Automatic UI refresh with @FetchRequest
- **Memory Management**: Efficient Core Data operations with proper cleanup
- **Battery Optimization**: Smart timer management and background processing
- **Gesture Handling**: Optimized touch interactions and haptic feedback

## 🎨 User Interface

### Modern Design Elements
- **Tab Navigation**: Clean tab-based interface (Tasks, Categories, Settings, Insights)
- **Floating Action Button**: Quick task and category creation
- **Swipe Gestures**: Intuitive swipe actions for common operations
- **Dark Mode Support**: Automatic system theme detection with manual override
- **Accessibility**: VoiceOver support and proper contrast ratios

### Visual Feedback
- **Smooth Animations**: 60fps transitions and micro-interactions
- **Haptic Feedback**: Tactile responses for user actions
- **Progress Indicators**: Visual completion states and loading animations
- **Color Coding**: Consistent color scheme throughout the app

## 🔐 Data & Privacy

### Data Storage
- **Local First**: All data stored locally with Core Data
- **CloudKit Sync**: Optional iCloud synchronization across devices
- **Offline Support**: Full functionality without internet connection
- **Data Export**: Built-in data management and clearing options

### Privacy Protection
- **No Third-party Analytics**: No external tracking or data collection
- **Local Processing**: All operations performed on-device
- **Secure Notifications**: Notifications handled through Apple's secure framework
- **User Control**: Full control over data synchronization and storage

## 🤝 Contributing

This project uses:
- SwiftUI for modern iOS development
- Core Data for local persistence with CloudKit sync
- UNUserNotificationCenter for local notifications
- Comprehensive localization with .lproj bundles
- XCTest for testing

### Development Guidelines
- Follow SwiftUI best practices and conventions
- Maintain comprehensive test coverage
- Ensure all UI strings are localized
- Test on multiple device sizes and orientations
- Verify notification functionality on physical devices

### Code Structure
- Use direct Core Data integration with @FetchRequest
- Implement proper error handling and recovery
- Follow Apple's Human Interface Guidelines
- Maintain clean separation of concerns
- Document all public APIs and complex logic

## 📝 License

This project is part of a development portfolio. See individual file headers for specific licensing information.

---

**Built with ❤️ using SwiftUI, Core Data, and modern iOS development practices**