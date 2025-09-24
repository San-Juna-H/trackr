Trackr

Trackr is a simple macOS menu bar app that combines a Pomodoro timer with a timesheet tracker. Track your tasks, categorize them with tags, and automatically save the work session logs in an XLSX file.

Features
	•	25-minute Pomodoro timer
	•	Task and Tag input at the start of each session
	•	Menu bar timer display
	•	Stop Early option
	•	Notifications on completion or early stop
	•	Automatic XLSX logging with:
	•	Task
	•	Tag
	•	Start Date
	•	Start Time
	•	End Time
	•	Duration (MM:SS)
	•	Menu bar icon support (trackr.icns)

Requirements
	•	macOS
	•	Python 3.10+
	•	Python libraries:
	•	rumps
	•	openpyxl

Install dependencies:

pip3 install rumps openpyxl

Usage
	1.	Open terminal.
	2.	Run the app:

python3 trackr.py

	3.	Enter:
	•	Task: What you are going to work on
	•	Tag: A category or tag for the task
	4.	Timer starts and displays in the menu bar.
	5.	Optionally stop early via the “Stop Early” menu item.
	6.	Notification appears when the timer ends or is stopped.
	7.	XLSX file timesheet.xlsx is automatically updated on your Desktop.

XLSX Format

Task	Tag	Start Date	Start Time	End Time	Duration (MM:SS)


	•	Start Date: date of task start
	•	Start Time: exact start time
	•	End Time: exact end time
	•	Duration: MM:SS

Menu Bar Icon
	•	Default: trackr.icns
	•	To customize, replace ICON_PATH in trackr.py with your .icns file path.

Building a Standalone macOS App

You can create a standalone .app using PyInstaller so that users don’t need to run it from the terminal.
	1.	Install PyInstaller:

pip3 install pyinstaller

	2.	Build the app (replace paths as needed):

pyinstaller \
    --windowed \
    --name "trackr" \
    --add-data "trackr.icns:." \
    trackr.py

	•	--windowed: no terminal window appears
	•	--name: sets the app name
	•	--add-data: includes the icon in the app bundle

	3.	After building, find your app in:

dist/trackr.app

	4.	First launch: Right-click → Open (macOS security prompt for unsigned apps)

Notes
	•	Duration is recorded in MM:SS format.
	•	Start Date is always the date of session start.
	•	Each app run corresponds to a single task session. Run again for new tasks.
