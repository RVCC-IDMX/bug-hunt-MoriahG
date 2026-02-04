# Bug 3: The infinite greeting

## Trace table

| Step | usersGreeted | usersGreeted < 3 | Action |
| ---- | ------------ | ---------------- | ------ |
| 1    | 0            | true             | DISPLAY "What is your name?", INPUT userName, DISPLAY "Hello, " + userName + "!" |
| 2    | 0            | true             | DISPLAY "What is your name?", INPUT userName, DISPLAY "Hello, " + userName + "!"       |
| 3..  | 0            | true             | DISPLAY "What is your name?", INPUT userName, DISPLAY "Hello, " + userName + "!"       |

## What's wrong

An infinite loop is created because the variable used for the condition is never incremented within the loop, so usersGreeted remains 0 and the condition stays true.

## Fixed pseudocode

```pseudo
BEGIN
    SET usersGreeted TO 0

    WHILE usersGreeted < 3 DO
        DISPLAY "What is your name?"
        INPUT userName
        DISPLAY "Hello, " + userName + "!"
		SET usersGreeted TO usersGreeted + 1
    END WHILE

    DISPLAY "All users have been greeted!"
END
```

## Warning for future students

Warn you, I must: Infinite loops, a coder's trap they are. Always check, you should, that your loop's condition will one day be false. Change the variables inside your loop, you must, or forever it will run. Finished, your loop is not, until the exit you can clearly see!

**Voice chosen:** Yoda

**Used AI assistant (yes/no):** Yes, GitHub Copilot GPT-4.1

## Flowchart

`flowcharts/bug3-fixed.svg`
