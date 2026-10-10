# Promptathon: admin + participant system

## Run (once, on the admin laptop)
    pip install -r requirements.txt
    python app.py
The terminal prints two links. Participants open the first (`http://<laptop-ip>:5000/`), you open `/admin`.
Admin password: `admin123`. Change it before the event:
    Windows:   set ADMIN_PASSWORD=YourPassword && python app.py
    Linux/Mac: ADMIN_PASSWORD=YourPassword python app.py

## Offline lab (no internet)
Download https://cdn.socket.io/4.7.5/socket.io.min.js once and save it as `static/socket.io.min.js`.
All laptops must be on the same WiFi/LAN. Allow port 5000 in Windows Firewall.

## Event flow
1. Participants join with Team Name + Team Number.
2. Admin clicks "Start R1..R4". Problem and timer appear on every screen; timer is server-controlled.
3. Round auto-locks at 00:00 (or click End round). "+1 min" extends time.
4. Admin scores each prompt in the Submissions table. Participants table shows the live leaderboard.
5. "Export Excel (.xlsx)" and "Export CSV" download all prompts, scores and warnings.

## Customise
Edit `rounds.json` (title, minutes, problem) before starting. Change MAX_WARNINGS with an env variable.

## Anti-cheat included
Tab-switch, fullscreen-exit and paste/copy/cut/drop attempts are logged as warnings. One Team Number = one live login.
Browser checks cannot stop a second phone, so keep volunteers walking the room.
