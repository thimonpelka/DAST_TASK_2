# Data Dictionary for `Rocket League Skillshot Data` (10.82556/myw9-yb20)

This dataset contains features extracted from Rocket League gameplay frames to predict the **skillshot type** used to score goals.

---

### Primary Columns

| Column Name | Data Type | Description | Units / Range | Example Value |
|:------------|:----------|:------------|:--------------|:--------------|
| `id` | Integer | Unique goal identifier. | Positive integers | 0 |
| `window_id` | Float | Frame ID within a 30-frame sequence before the goal. | 0–29 (may be NaN for summary rows) | 0.0 |
| `BallAcceleration` | Float | Ball acceleration magnitude. | Arbitrary units | 1636.80 |
| `Time` | Float | Time elapsed since start of frame sequence. | Seconds | 0.1389 |
| `DistanceWall` | Float | Distance between ball and nearest wall. | Game units | 3494.08 |
| `DistanceCeil` | Float | Distance between ball and ceiling. | Game units | 2012.98 |
| `DistanceBall` | Float | Distance between player and ball (may be missing). | Game units | 229.90 |
| `PlayerSpeed` | Float | Speed of the player. | Units per second | 124248.03 |
| `BallSpeed` | Float | Speed of the ball. | Units per second | 102233.88 |

---

### Player Input Features

| Column Name | Data Type | Description | Units / Range | Example Value |
|:------------|:----------|:------------|:--------------|:--------------|
| `up` | Bool | Binary: Player pressed up. | 0 or 1 | 0.0 |
| `accelerate` | Bool | Binary: Player accelerating. | 0 or 1 | 0.0 |
| `slow` | Bool | Binary: Player slowing down. | 0 or 1 | 0 |
| `goal` | Bool | Binary: Ball is in the goal | 0 or 1 | 1 |
| `left` | Bool | Binary: Steering left. | 0 or 1 | 0 |
| `boost` | Bool | Binary: Boosting. | 0 or 1 | 0 |
| `camera` | Bool | Binary: Camera toggling. | 0 or 1 | 0 |
| `down` | Bool | Binary: Pressing down. | 0 or 1 | 0 |
| `right` | Bool | Binary: Steering right. | 0 or 1 | 0 |
| `slide` | Bool | Binary: Sliding (powersliding). | 0 or 1 | 0.0 |
| `jump` | Bool | Binary: Jumping. | 0 or 1 | 0.0 |

---

### Skewed (Statistical Summary) Features

| Column Name | Data Type | Description |
|:------------|:----------|:------------|
| `BallAcceleration_skew` | Float | Skewness of ball acceleration values. |
| `Time_skew` | Float | Skewness of time values (should be near 0). |
| `DistanceWall_skew` | Float | Skewness of distance to wall. |
| `DistanceCeil_skew` | Float | Skewness of distance to ceiling. |
| `DistanceBall_skew` | Float | Skewness of distance player-ball. |
| `PlayerSpeed_skew` | Float | Skewness of player speed. |
| `BallSpeed_skew` | Float | Skewness of ball speed. |
| `up_skew` | Float | Skewness of 'up' input events. |
| `accelerate_skew` | Float | Skewness of acceleration input events. |
| `slow_skew` | Float | Skewness of slowing input events. |
| `goal_skew` | Float | Skewness of goal indicators (typically uniform). |
| `left_skew` | Float | Skewness of left steering. |
| `boost_skew` | Float | Skewness of boosting. |
| `camera_skew` | Float | Skewness of camera toggling. |
| `down_skew` | Float | Skewness of down inputs. |
| `right_skew` | Float | Skewness of right steering. |
| `slide_skew` | Float | Skewness of sliding actions. |
| `jump_skew` | Float | Skewness of jump actions. |

---

### Label (Target Variable)

| Column Name | Data Type | Description | Units / Range | Example Value |
|:------------|:----------|:------------|:--------------|:--------------|
| `label` | Integer | Skillshot type used to score the goal. See mapping below. | 0–6 | 6 |

**Skillshot Type Mapping:**

| Label Value | Skillshot |
|:------------|:----------|
| 0 | Ground Shot |
| 1 | Aerial Shot |
| 2 | Wall Shot |
| 3 | Ceiling Shot |
| 4 | Air Dribble |
| 5 | Ground Pinch |
| 6 | Flip Reset |
| 7 | Double Touch |

---

## Important Notes
- Some columns (`DistanceBall`, skewed features) contain missing values.
- Labels are consistent and manually validated.
- Data uploaded to DBRepo with DOI and results published on TUWRD to ensure FAIR compliance.
- Hyperparameter optimization was performed during model training.
- Prediction outputs include `.pkl` model files and confusion matrices for model evaluation.
