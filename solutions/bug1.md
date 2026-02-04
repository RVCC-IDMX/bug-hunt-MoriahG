# Bug 1: The counter that counts wrong

## Trace table

| Step | counter | counter < 5 | Action                           |
| ---- | ------- | ----------- | -------------------------------- |
| 1    | 1       | true        | DISPLAY "Count: 1", SET count++  |
| 2    | 2       | true        | DISPLAY "Count: 2", SET count++  |
| 3    | 3       | true        | DISPLAY "Count: 3", SET count++  |
| 4    | 4       | true        | DISPLAY "Count: 4", SET count++  |
| 5    | 5       | false       | DISPLAY "Done counting to 5!"    |
## What's wrong

The while loop does not display all numbers from 1 to 5 because the counter is incremented after the count is displayed and the loop condition is only true if counter less than 5. So, when the counter reaches 5, the loop does not run again to display 5.

## Fixed pseudocode

```pseudo
BEGIN
    SET counter TO 1

    WHILE counter <= 5 DO
        DISPLAY "Count: " + counter
        SET counter TO counter + 1
    END WHILE

    DISPLAY "Done counting to 5!"
END
```

## Real-world consequences

In a game like Mario Kart, the countdown from 3 to 1 before the race begins could miss displaying the final number. This would cause confusion for the players and may cause some players to start too early or too late, muddying the playing field.

## Flowchart

`flowcharts/bug1-fixed.svg`
