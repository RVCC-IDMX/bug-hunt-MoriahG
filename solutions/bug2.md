# Bug 2: The grade that's never excellent

## Trace table

| Step | score | Condition checked | Result                            |
| ---- | ----- | ----------------- | --------------------------------- |
| 1    | 95    | score >= 60       | true, DISPLAY "Grade: D - Passing"|

## What's wrong

The if-elseif-else conditions are checked in order and the first condition that is true will execute and break out of the entire statement and skip all other conditions, causing the incorrect grade to be assigned. A 95 will be considered a D because it validates the first condition, score >= 60, and the following conditions are skipped.

## Fixed pseudocode

```pseudo
BEGIN
    DISPLAY "Enter your score (0-100):"
    INPUT score

    IF score >= 90 THEN
        DISPLAY "Grade: A - Excellent"
    ELSEIF score >= 80 THEN
        DISPLAY "Grade: B - Good"
    ELSEIF score >= 70 THEN
        DISPLAY "Grade: C - Satisfactory"
    ELSEIF score >= 60 THEN
        DISPLAY "Grade: D - Passing"
    ELSE
        DISPLAY "Grade: F - Failing"
    ENDIF
END
```

## Reframed explanation

Many games match players based on rank to create even matches and progression. If the ranking system improperly assigns players their rank based on skill levels, the system will be faulty by only separating players into two ranks, above 60 as D or below 60 as F. This would generalize the players skills which would cause a skill imbalance within matches.

## Flowchart

`flowcharts/bug2-fixed.svg`
