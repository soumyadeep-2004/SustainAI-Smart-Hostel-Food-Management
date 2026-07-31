# SustainAI-Smart-Hostel-Food-Management
SustainAI is a smart hostel food management and waste optimization platform that bridges technology, finance, and sustainability (1M1B Green Skills). It is designed to transform high-waste hostel mess halls into data-driven, zero-waste operations.
🏗️ Core Architecture & Shared State
SustainAI operates on a dual-storage replication engine:

Offline Mode: Operates out-of-the-box, persisting the entire application state in the browser's localStorage.
Cloud Mode: Dynamically connects to Google Firebase Firestore via the built-in Console interface in the header. Once connected, RSVPs, mess menus, context variables, and audit trails synchronize instantly in real-time across multiple devices (e.g. students on phones, canteens on tablets).
-------------------------------------------------------------------------------------------------------------------
👤 Role 1: Student App (Meal RSVP)
Designed to gather active attendance data before preparation begins.

Features
Dynamic Weekly Calendar:
Students select days of the week (Sunday through Saturday) to RSVP for meals.
dietary-Aware Color Coding:
Vegetarian items are styled with green badges (🌱 Veg).
If a meal has non-vegetarian options available, it displays a red badge (🍗 Non-Veg). If a meal is set to Veg-only, the Non-Veg selection card is hidden automatically.
Interactive RSVP Controls:
Buttons to confirm attendance as either Attend Veg, Attend Non-Veg, or mark Can't make it.
Immediate status alert updates (e.g., ✓ Attend (Veg) saved in green, ✓ Not Attending saved in grey) to confirm their choice is recorded.
---------------------------------------------------------------------------------------------------------------------
🍳 Role 2: Kitchen Staff Dashboard (Mess Operations)
Empowers cooks to prepare food to the ticket rather than static averages, and edit the mess menu.

Features
AI turnout Forecasting:
Computes expected turnout by blending the hostel's historical averages with live student RSVPs.
Adjusts forecasts automatically for external factors (Exam weeks, heavy rain, public holidays). Toggling these context checkboxes recalculates raw ingredients weight in kilograms (kg) on-the-fly.
✏️ Mess Menu Editor:
Kitchen staff can click ✏️ Edit Menu on any meal ticket.
A modal allows editing the dish name and checking/unchecking the non-vegetarian option.
Saving updates the database instantly, automatically changing the menu names and showing/hiding dietary cards for students in real-time.
Simulate IoT Scale Reading:
Integrates with raw scales to measure prep quantities and plates returned. Click Simulate IoT reading to pull weights, then click Log service to feed data directly to the Admin's analytics.
----------------------------------------------------------------------------------------------------------------------
👑 Role 3: Hostel Admin (Analytics & Procurement)
Restricted dashboard for supervisors to audit, examine waste trend charts, and manage vendor billing.

Features
Secure Login:
Protected behind a password barrier. Enter Admin Username and Admin Password to gain access. Other roles are restricted and locked out.
Tab A: Admin & Analytics Dashboard:
Key Financial KPIs: Displays measured waste rates, servings wasted, and estimated cost saved compared to baseline averages.
Defensive Charts: Interactive Waste Trend Line Chart (with baseline margins) and Hostel Comparison Bar Chart powered by Chart.js. Includes offline text placeholders if local canteens are operating without an internet connection.
Audit Trail & Service Log: High-yield tables documenting food prep logs and actions recorded across canteens.
CSV Data Export: A yellow 📥 Export Training Data (CSV) button to instantly download sustainai_training_data_150_students.csv (1 week of training logs for 150 students).
Tab B: Procurement & Bills (New!):
Supply Chain Summary: Displays metrics like total active suppliers, quarterly invoice spending, pending outstanding payments, and average monthly expenditures.
Supplier Cost-Share Chart: A dynamic Doughnut Chart displaying procurement category shares.
Distributors & Invoices Directory: Lists active vendors and billing logs. Admins can click ✏️ Edit on any vendor/invoice to modify details, delete records, or click ➕ Add to record new logs. The Cost Share Chart and Summary metrics recalculate automatically in real-time!
📹 Full Website Demonstration Tour Script
Follow this chronological flow to demonstrate all features on screen in under 2 minutes:

Mermaid diagram
Step 1: Sign in with Admin Credentials
Select the Hostel Admin card on the login screen.
Enter username adminuser and password to log in successfully.
Step 2: Admin & Analytics Tour
Review the stats card numbers showing cost savings.
Scroll to show the line and bar charts rendering waste metrics.
Scroll to the settings section and click the yellow 📥 Export Training Data (CSV) button. Show the Excel CSV file downloading.
Step 3: Procurement & Bills Tour
Click the Procurement & Bills tab in the navigation bar.
Point out the Doughnut Chart showing food category cost shares.
Click ➕ Record Invoice. Pick a supplier (e.g. Apex Dairy Co.), type amount 50000, item Cheese & Paneer, and click save. Show that the cost-share chart and summary indicators update immediately!
Click Switch role in the top right to log out.
Step 4: Kitchen Dashboard & Menu Editor
Click Kitchen Staff, type name Sanjay, and click log in.
Click ✏️ Edit Menu on today's Dinner ticket.
Change the dish name to Mutton Biryani / Paneer Biryani, check Has Non-Vegetarian option, and click Save. Show the ticket update.
Click Simulate IoT reading on the ticket, then click Log service.
Click Switch role.
Step 5: Student RSVP
Click Student, type name Vipul, select Hostel 12, and click log in.
Go to the My RSVPs tab.
Highlight the dinner ticket: show Paneer Biryani styled in a green chip and Mutton Biryani styled in a red chip.
Click Attend Non-Veg. Point to the green toast: "✓ Attend (Non-Veg) saved".
