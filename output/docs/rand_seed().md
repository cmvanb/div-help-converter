**rand_seed(**&lt;numeric value&gt;**)**

### Description

This function sets a seed for the generator of random numbers
(the numbers generated by the [rand()](rand().md) function).

The seed can be any integer within the range ([min_int](min_int.md) ... [max_int](max_int.md)).
If the seed is set, all the numbers generated by the [rand()](rand().md) function will be
the same in every execution of the program.
After having been established an origin seed, the [rand()](rand().md)
function will return a series of numbers predetermined for this seed.

### Example program
```
PROGRAM example_rand_seed;

PRIVATE
    table[15];
    counter;

BEGIN
    write (0, 0, 184, 0, "Press [ENTER] to set 1234 as a seed.");
    write (0, 0, 192, 0, "Press [SPACE] to calculate random values.");
    FROM counter=0 TO 15;
        write_int(0, 0, counter*10, 0, offset table[counter]);
    END
    LOOP
        IF (scan_code==_space)
            FROM counter=0 TO 15;
                table[counter] = rand(-100, 100);
            END
        END
        IF (scan_code==_enter)

            rand_seed(1234); // A seed is set to generate the random numbers.

        END
        FRAME;
    END
END
```


In the example, a table with 16 bits of data (from 0 to 15) is created. In every iteration
of the main loop,  the data will be filled with random values from -100 and 100 (chosen with the [rand()](rand().md) function) every time the spacebar is pressed.

And when the ENTER key is pressed, then the seed of the random numbers will be defined as 1234 with the **rand_seed()** function.

Notice how, every time the ENTER key is pressed and then, by pressing the space bar, the same series of random numbers (17, 94, -38, ...) is obtained. This series will be different for every possible seed.

---------------------------------------
See: [rand()](rand().md)

