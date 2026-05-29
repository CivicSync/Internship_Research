Flutter Habit Tracking App

Team Members
- Gauri Sharma
- Swati Dongare

Objective

The objective of this project is to develop a simple Flutter-based Habit Tracking Application that helps users maintain daily habits and track their consistency. The app allows users to create habits, mark daily completion, and monitor progress through streaks and summaries.

Approach

1. Requirement Analysis

First, the application requirements were analyzed to understand the core functionalities such as habit creation, daily tracking, streak management, and progress monitoring.

2. UI Design

A clean and simple user interface was designed using Flutter widgets. The application contains multiple screens for adding habits, viewing habit lists, daily check-ins, and progress summaries.

3. Database Design

A MySQL database was used to store habit information and daily completion records. Two tables were created:

- "habits"
- "habit_logs"

4. Backend Integration

PHP APIs were used to connect the Flutter application with the MySQL database. APIs handle operations such as:

- Adding habits
- Fetching habits
- Updating completion status
- Retrieving progress data

5. Habit Tracking Logic

The application tracks user consistency by storing completed habit records daily and calculating streak counts based on consecutive completion days.

6. Testing

The application was tested on Android devices to ensure proper functionality of habit creation, tracking, database operations, and UI responsiveness.


Features

- Add new habits
- View all habits
- Mark daily habit completion
- Track habit streaks
- View progress summary
- Simple and user-friendly UI
- MySQL database integration

Tools & Technologies

- Flutter
- Dart
- MySQL
- PHP
- Android Studio


Database Structure

Table: habits
Stores habit details.

Fields:

- id
- title
- category
- reminder_time

Table: habit_logs
Stores daily completion records.

Fields:

- id
- habit_id
- completed_date
- status



App Flow

1. User opens the application
2. User creates a habit
3. Habit appears in the habit list
4. User marks habits as completed daily
5. Progress and streak data are updated automatically


Expected Output

- Flutter source code
- APK file or demo video
- Application screenshots
- Database integration
- Functional habit tracking system


Future Improvements

- Push notifications/reminders
- Dark mode support
- Weekly and monthly analytics


Conclusion

The Flutter Habit Tracking App provides a simple solution for users to build consistency in daily activities. The project demonstrates Flutter UI development, backend integration, and database management using MySQL.
