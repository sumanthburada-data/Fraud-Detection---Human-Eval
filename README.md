🎯 What It Does
This is a single-page web application for manually reviewing AI-flagged delivery images. It lets reviewers evaluate whether AI detection models correctly identified issues in Walmart delivery photos — essentially a human-in-the-loop evaluation tool for image classification AI.

🏗️ Core Capabilities
1. 📊 Dashboard & Analytics
Real-time stats cards showing counts and percentages for:
Total records, Reviewed items, Manual Review ✓/✗
Fraud Photo, Human Face, Inside Vehicle, Profanity detections
Total flagged items
Review progress bar tracking how many records have been evaluated

3. 📁 CSV Data Loading
Drag-and-drop or file picker to load a CSV dataset
Ships with 2 sample rows for demo purposes
Supports round-tripping — if the CSV already has reviewAiCorrect, reviewConfusionMatrix, reviewComments columns, those values are pre-populated


4. 🖼️ Image Comparison Cards
Each record displays as a card with:

Side-by-side images: Processed vs. Original delivery photo
Metadata: Order ID, Task ID, Decision (acceptable/unacceptable), Timestamp
Detection pills: Color-coded badges for each AI flag (Fraud, Face, Vehicle, Profanity)
Click-to-zoom modal for full-size image inspection

4. 🔍 Filtering & Search
Filter	Description
Order ID search	Free-text search by order ID
Decision filter	Dropdown: acceptable / unacceptable
Manual Review filter	Filter by Yes/No review status
Category toggles	Fraud Photo, Human Face, Inside Vehicle, Profanity, All Flagged
Keyboard navigation	Arrow keys for pagination, Escape to close modal

5. ✅ Human Review Section (per card)
Each image card includes a review panel where reviewers can:

Manual Review — Yes / No (was the AI correct?)
Confusion Matrix — TP, TN, FP, FN classification
Comments — Free-text notes
Cards get a green ✓ Reviewed badge once evaluated

6. 📥 CSV Export
Download Reviewed CSV button exports all records with three appended review columns:
reviewAiCorrect, reviewConfusionMatrix, reviewComments
Proper CSV escaping for commas, quotes, and newlines
Timestamped filename: image_review_YYYY-MM-DD-HH-MM-SS.csv

8. 📄 Pagination
Configurable: 5 / 10 / 25 / 50 / All per page
Smooth scroll-to-top on page change
🧠 AI Detection Categories Tracked
Category	Field	What It Detects
🔴 Fraud Photo	isFraudPhoto	Potentially fraudulent delivery images
🟠 Human Face	isHumanFaceDetected	Photos containing human faces (privacy concern)
🔵 Inside Vehicle	isShotFromInsideVehicle	Photos taken from inside a vehicle
🟣 Profanity	isProfanityDetected	Images containing profane content
⚙️ Technical Details
Aspect	Detail
Architecture	Single-file HTML — zero dependencies, no frameworks
Styling	Embedded CSS with responsive design (mobile-friendly at 768px & 480px breakpoints)
JavaScript	Vanilla JS — custom CSV parser, in-memory filtering, DOM rendering
State	All data held in-memory (allData, reviewData, filtered) — no backend/database
Hosting	GitHub Pages at gecgithub01.walmart.com
Image source	images.delivery.walmart.com — Walmart delivery image CDN
💡 Summary
This is a lightweight, self-contained AI evaluation tool that enables reviewers to audit delivery image classification decisions made by AI models. It tracks whether the AI correctly flagged photos for fraud, human faces, vehicle interiors, and profanity — then exports the human review labels (including confusion matrix classifications) back to CSV for model performance analysis.

It's a solid tool for measuring AI model accuracy and building a labeled dataset for retraining! 
