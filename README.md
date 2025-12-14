> This repository contains documentation only.  
> Source code is intentionally excluded as this project was submitted as part of CS50.

<div align="center">

# Study Tracker

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Documentation](https://img.shields.io/badge/Documentation-red)

</div>

#### Language: Python
#### Video Demo:  [CS50 python final project on YouTube](https://www.youtube.com/watch?v=B9mLAShodyQ)
#### Description:
A command line application that will help you in tracking your study routine and can view your progress report or generate a progress report file in (csv or txt). It also tracks your daily streak, each day you track your study, the streak increases by one and if you miss a day, it resets to `1 day` similar to many study apps.


#### Usage
1. **Tracking your progress**
    - you can track your study progress by using following command,
    ```bash
    python project.py track
    ```
    - This command will request you to input `username`, `subject` *(subject that you want to track)* and `time spent` in `h:m` format, Example:
        - `0:30` for `30min`
        - `1` for `1hour`
        - `2:30` for `2hour and 30min`

2. **View your tracked progress**
    - you can view your progress using following command,
    ```bash
    python project.py show:progress -n YourName
    ```
    - this will output an overall report that total data for all subjects that you tracked
    ```
    +------------------+------------+
    | Last Tracked     | 2025-9-1   |
    +------------------+------------+
    | Streak           | 1 day      |
    +------------------+------------+
    | Total Time Spent | 45 minutes |
    +------------------+------------+
    ```
    - you can also view your progress for specific subject, using same command with additional option `-s`,
    ```bash
    python project.py show:progress -n YourName -s YourSubject
    ```
    - this will output a report for specific subject,
    ```
    +------------------+------------+
    | Last Tracked     | 2025-9-1   |
    +------------------+------------+
    | Streak           | 1 day      |
    +------------------+------------+
    | Total Time Spent | 15 minutes |
    +------------------+------------+
    ```

3. **Generate a progress report**
    - you can generate a progress in csv or txt format, using this following command,
    ```bash
    python project.py generate:report -n David
    ```
    - this is also similar to `show:progress`, this will generate a overall report in default `txt` extension, under `study_tracker/reports` path.

    - Example:
        - *reports/2025-09-01_David.txt*
        ```
        Name: David
        last_tracked: 2025-9-1
        streak: 1 day
        time_spent: 45 minutes

        Subjects:

        English
        last_tracked: 2025-9-1
        streak: 1 day
        time_spent: 15 minutes

        Spanish
        last_tracked: 2025-9-1
        streak: 1 day
        time_spent: 30 minutes
        ```

    - you can also generate a specific subject and also file in `csv` using same command with additional options `-s` and `-e`
    ```bash
    python project.py generate:report -n David -s spanish -e csv
    ```

    - this will generate a report for specific subject in csv format

    - Example:
        - *reports/2025-09-01_David_spanish.csv*
        ```
        Name,David
        Subject,Spanish
        last_tracked,2025-9-1
        streak,1 day
        time_spent,30 minutes
        ```

#### Commands

| Command          | Options                                      | Description                          |
|-----------------|---------------------------------------------|--------------------------------------|
| track           |   -                                         | Track study progress                  |
| show:progress   | `-n`, `--name` *(required)*<br>`-s`, `--subject` *(optional)* | View overall or subject-specific progress |
| generate:report | `-n`, `--name` *(required)*<br>`-s`, `--subject` *(optional)*<br>`-e`, `--extension` *(optional)* | Generate TXT or CSV report           |

