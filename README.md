## Ethan C. Lee: software lead of FTC #18225 High Definition

This GitHub portfolio showcases code specifically written by me, as lead programmer, during the IntoTheDeep (2024-2025) and Decode (2025-2026) FIRST Tech Challenge seasons.

## Code highlights
1. **Virtual Spindexer:** [Presets.java, lines 52–81](https://github.com/HiiDeff/Decode/blob/4301e0505f458220a852322cdfb4302b9f218f14/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/task/Presets.java#L52-L81) Changes the order of ball color by shooting low-velocity and reintaking, emulating a "spindexer" outside the robot. Implemented in [CloseSortAuto.java](https://github.com/HiiDeff/Decode/blob/4301e0505f458220a852322cdfb4302b9f218f14/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/auto/sortauto/close/CloseSortAuto.java).
3. **Physics-based turret feedforward:** [Turret.java, lines 118–132](https://github.com/HiiDeff/Decode/blob/b70c7abd3ca2a024099ab02f1856337dd28b5a00/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/drive/Turret.java#L118-L132). Computes torque on the turret's offset center-of-mass due to drivetrain accelerations, to counteract them in the PID. 
4. **Pixel-to-field coordinates:** [`normalizedPixelToRealWorldCoordinates()` in LimelightSampleDetector.java, lines 19–49](https://github.com/HiiDeff/IntoTheDeepWorlds/blob/fb2e1e33b287f742cfa9bd9ccb23e037df43dba5/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/util/limelight/LimelightSampleDetector.java#L19-L49). Converts pixel coords to real-world coords for the auto-intaking pipeline. 

## Repositories and branches

Our team has one repository for the main season and another one for the World Championship each competition season. Each competition lives in its own branch. Note this means that 'main' is not necessarily the most recent branch. 

| Season | Repository | Branch |
| --- | --- | --- |
| Into the Deep (2024–25) | [IntoTheDeep](https://github.com/HiiDeff/IntoTheDeep/tree/worlds_testing) | `worlds_testing` |
| Into the Deep, Worlds | [IntoTheDeepWorlds](https://github.com/HiiDeff/IntoTheDeepWorlds) | `main` |
| Decode (2025–26) | [Decode](https://github.com/HiiDeff/Decode/tree/States) | `States` |

IntoTheDeepWorlds began as a copy of IntoTheDeep, so some vision files had original commits in IntoTheDeep.

## Authorship

| System | Files | Date first created by me | Later changes by others |
| --- | --- | --- | --- |
| Vision auto-intake + arm | [LimelightSampleDetector.java](https://github.com/HiiDeff/IntoTheDeepWorlds/blob/fb2e1e33b287f742cfa9bd9ccb23e037df43dba5/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/util/limelight/LimelightSampleDetector.java), [LimelightProcessorBase.java](https://github.com/HiiDeff/IntoTheDeepWorlds/blob/561e4f6de50b2459bb43cf162a39bb53861458cd/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/util/limelight/LimelightProcessorBase.java), [InvKin.java](https://github.com/HiiDeff/IntoTheDeepWorlds/blob/e655170b4663cddb9c1a5286eb6cf0c1da7993ba/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/common/InvKin.java), [SampleAuto.java](https://github.com/HiiDeff/IntoTheDeepWorlds/blob/0e7c0d54ec935049429a8784b56671a1302e4c9c/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/auto/sampleauto/SampleAuto.java) | Detector and processor base: 3/5/25 in IntoTheDeep ([first versions](https://github.com/HiiDeff/IntoTheDeep/blob/0b72e11dcdc6373569f3b112bdb44c442f1ae86a/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/util/limelight/LimelightSampleDetector.java)), continued in IntoTheDeepWorlds from 3/23/25. InvKin.java: 4/5/25. SampleAuto.java: 4/9/25. | None |
| Turret feedforward | [Turret.java](https://github.com/HiiDeff/Decode/blob/b70c7abd3ca2a024099ab02f1856337dd28b5a00/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/drive/Turret.java) | File: 12/5/25. Physics-based feedforward: 12/7/25. | Ne3re3eksh: tried a different localization method (1 commit) and tuned small values (2 commits). actiniumn404: color sensor testing, changed one value (1 commit). |
| Shooting on the move | [Turret.java](https://github.com/HiiDeff/Decode/blob/b70c7abd3ca2a024099ab02f1856337dd28b5a00/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/drive/Turret.java) | 1/16/26 | Same as above |
| Virtual Spindexer | [Presets.java](https://github.com/HiiDeff/Decode/blob/4301e0505f458220a852322cdfb4302b9f218f14/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/task/Presets.java), [CloseSortAuto.java](https://github.com/HiiDeff/Decode/blob/4301e0505f458220a852322cdfb4302b9f218f14/TeamCode/src/main/java/org/firstinspires/ftc/teamcode/auto/sortauto/close/CloseSortAuto.java) | 1/30/26 | None |

Notes: 
The Kalman filter was later implemented by Actinium404 (subteam member) under my guidance.
The 'FTCRobotController' folder and old commits in each repository were originally from the FIRST SDK. All team code is located in 'TeamCode'.

### Vision pipeline note

The block (sample) detection pipeline that used OpenCV (color detection, Canny edge detection, and the watershed transform) was saved locally on the LimeLight 3A camera, so the Python code wasn't added to the repository. Unfortunately, could not be accessed/found.

## Tools

Code that came before me: FTC SDK, overarching codebase structure (written by a former programming alumnus, Allen Wu), LimeLight firmware/environment. All code highlighted and linked was written, originally, by me. 
Libraries: OpenCV (documentation code inspected for inspiration), PedroPathing (path generation and execution), FTC Dashboard
Other tools: RoboFlow (neural network training) 
Note: used AI to structurally format this .md file specifically. 
