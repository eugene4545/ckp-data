PROBLEM 1
ALGORITHM sets_data_structures
// we set the variables and array for the algorithim.
VAR
    setOne : INTEGER [4];// setting the size of array (as it is a static data structure it cannot be changed)
    setTwo : INTEGER [5];
    i,j,sum : INTEGER := 0;// declaring variables "sum", and loop counters "i" and "j"
    isDistinct : BOOLEAN //this helps us check if we have duplicates or distinct integers.
BEGIN
    setOne[0] := 3;
    setOne[1] := 1;
    setOne[2] := 7;
    setOne[3] := 9;

    setTwo[0] :=2;
    setTwo[1] :=4;
    setTwo[2] :=1;
    setTwo[3] :=9;
    setTwo[4] :=3;// assigning values to the arrays setOne and setTwo.

    FOR i FROM 0 TO setOne.length DO
        isDistinct := true;
        FOR j FROM 0 TO setTwo.length DO
            IF setOne[i] = setTwo[j] THEN// here we are comparing values from
                isDistinct := false//setOne array to setTwo arrays to check if they are distinct or not
            END_IF
        END_FOR
        IF isDistinct THEN // if there are distinct values we then add it to the sum
            sum := sum + setOne[i];
        END_IF

    END_FOR
    
    FOR i FROM 0 TO setTwo.length DO//  we do the same for this sub-algorithim if there are any
        isDistinct := true;        //distinct values we add them to the sum. 
        FOR j FROM 0 TO setOne.length DO
            IF setTwo[i] = setOne[j] THEN
                isDistinct := false
            END_IF
        END_FOR
        IF isDistinct THEN
            sum := sum + setOne[i];
    END_IF

END_FOR

write("sum of all distinct elements : ", sum);
END
