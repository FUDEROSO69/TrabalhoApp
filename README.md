MIList App

Overview

The MIList App is a simple and intuitive mobile application built with React Native, Expo, and TypeScript to help employees track payment schedules, bills, and events. The app features reminders for due dates (notified one day in advance), daily cost calculations, monthly reports, and categorization of bills by due date. Data is stored locally using AsyncStorage, and navigation is handled by Expo Router. The app follows an ergonomic design for ease of use, with modals for adding, editing, and viewing reports.

Features





MIList: Add, edit, or delete bills with details (name, value, due date, type, payment method, optional payment code).



Daily Cost Calculation: Displays the daily cost of each bill (value divided by the number of days in the due month).



Notifications: Sends reminders one day before a bill’s due date using expo-notifications.



Monthly Reports: Generates reports showing which bills were paid on time or late.



Categorization: Groups bills by due date in a modal for easy tracking.



Local Storage: Persists data using AsyncStorage.

Project Structure

bills-management-app/
├── app/
│   └── index.tsx          # Main screen with bill list and modal triggers
├── components/
│   ├── BillItem.tsx       # Component to display individual bill details
│   ├── AddBillModal.tsx   # Modal for adding/editing bills
│   ├── ReportsModal.tsx   # Modal for monthly payment reports
│   └── CategoriesModal.tsx # Modal for categorizing bills by due date
├── utils/
│   ├── storage.ts         # AsyncStorage functions for saving/loading bills
│   ├── notifications.ts   # Notification scheduling with expo-notifications
│   └── dateUtils.ts       # Date calculations (e.g., daily cost)
├── types/
│   └── index.ts           # TypeScript interfaces (Bill)
├── app.json               # Expo configuration
├── package.json           # Dependencies and scripts
└── README.md              # Project documentation

Prerequisites





Node.js (v16 or higher)



Expo CLI (npm install -g expo-cli)



A physical device for testing notifications (emulators do not support notifications)

Installation





Clone the repository:

git clone <repository-url>
cd bills-management-app



Install dependencies:

npm install
npx expo install expo-router expo-notifications @react-native-async-storage/async-storage @react-native-community/datetimepicker uuid date-fns



Configure notifications:





Update app.json to include notification permissions as per Expo Notifications Documentation.



Run the app:

npx expo start

Scan the QR code with the Expo Go app on a physical device.

Usage





Main Screen: View the list of bills with details (name, value, due date, daily cost). Use buttons to open modals for adding bills, viewing reports, or categorizing by due date.



Add/Edit Bills: Use the modal to input bill details (name, value, due date, type, payment method, optional payment code).



Notifications: Receive reminders one day before a bill’s due date. Notifications are automatically canceled if a bill is paid or deleted.



Reports: Check monthly reports to see which bills were paid on time or late.



Categorization: View bills grouped by due date in a modal.

Development Approach





Interviews: Gathered requirements from employees to ensure the app meets their needs for bill tracking.



Observation: Analyzed user workflows to design an intuitive interface.



Prototyping: Used Figma for wireframes and mockups to validate the UI/UX.



Programming: Implemented in React Native with Expo and TypeScript, using modals for a streamlined experience.



Test-Driven Development (TDD): Wrote unit tests for critical functions (e.g., daily cost calculation, notifications) to ensure reliability.

Evaluation Metrics





Payment Timeliness: Compare the percentage of on-time payments before and after app implementation.



User Satisfaction: Collect feedback via a questionnaire (e.g., ease of adding bills, clarity of notifications).



Operational Efficiency: Measure time spent on bill management tasks through direct observation.



Notification Engagement: Track the percentage of bills paid after receiving reminders.



Functionality: Achieve 100% test coverage for core features using TDD.

Dependencies





expo-router: File-based navigation



expo-notifications: Local and push notifications



@react-native-async-storage/async-storage: Local storage



@react-native-community/datetimepicker: Date picker



uuid: Unique ID generation



date-fns: Date manipulation

Notes





Notifications: Test on a physical device, as emulators do not support notifications.



Permissions: Request notification permissions on app startup using Notifications.requestPermissionsAsync().



TypeScript: Ensures type safety for robust code, with interfaces defined in types/index.ts.

Contributing

Contributions are welcome! Please submit a pull request or open an issue for suggestions or bug reports.

License

MIT License
