# Deanna Garrett, unit-test automation script for CS-3005, April 2024

# This script is used to run unit tests for CS-3005 assignments
# without navigating out of the program directory or changing windows.
# PLACE THIS INSIDE YOUR SRC DIRECTORY. It runs in the same location as make or ./ppm_menu
# examples at the bottom of the file show the output with different parameters.

# As is, it prints a summary of the test results but it can be modified to print more.
# but it won't print the entire output of the tests unless you change the parameters.
# It will still print any outputs you have in your actual program.
# Currently, it's set to print the results of assignments 5-13, but again that can be changed.

# Currently, this is the only script in the file, so it can be run without a function using:
    # source helper.sh
# It can be run inside a function if other functions might be added by encapsulating it in a function.
# The syntax for creating a function in zsh is: 'function runtests {  .....  }'
# The function can be called using:
    # source helper.sh && runtests

# The script is setup to be able to color the "PASSED" and "FAILED" text in the output.
# These colors work on a Mac using zsh, but they haven't been tested elsewhere.
# If the colors don't work in your terminal, you can comment out the lines that set the colors.

#!/bin/zsh
original_dir=$(pwd) # Save location of current directory
summary="" # Empty summary
cd ../../ut-cs3005-unit-tests-2024-20  # cd to the test directory

# Loop through the tests 5-13, change the range to test other assignments
for i in {05..13}
    do
        output=$(./unit-test.bash $i -j)
        output=$(echo "$output" | sed 's/PASSED/'$'\033[32mPASSED\033[0m''/g')  # Makes "PASSED" green
        output=$(echo "$output" | sed 's/FAILED/'$'\033[31mFAILED\033[0m''/g')  # Makes "FAILED" red
        summary+=$'\n\n'"Output for assignment-$i:"$'\n' # change or comment out to customize the output
        summary+=$(echo -e "$output" | tail -n 4 | head -n 3) # remove "| head -n 3" to print the last 4 (or your choice) lines.
        # Honestly I don't understand how the line indexing here works, but I tried quite a few combinations and I liked this one the best.
        # If you get back failed tests, try removing the | head -n 3 and increasing the int on tail -n to see more lines.
    done

cd $original_dir
echo -e "$summary"



# ----------------- SAMPLE OUTPUT -----------------
# sample output with tail -n 4 | head -n 3
#Output for assignment-05:
#[==========] 195 tests from 36 test suites ran. (101 ms total)
#[  PASSED  ] 195 tests.
#
#Output for assignment-06:
#[==========] 120 tests from 12 test suites ran. (36 ms total)
#[  PASSED  ] 120 tests.
#
#Output for assignment-07:
#[==========] 71 tests from 10 test suites ran. (5 ms total)
#[  PASSED  ] 71 tests.
#
#Output for assignment-08:
#[==========] 55 tests from 12 test suites ran. (170 ms total)
#[  PASSED  ] 55 tests.
#
#Output for assignment-09:
#[==========] 143 tests from 23 test suites ran. (46 ms total)
#[  PASSED  ] 143 tests.
#
#Output for assignment-10:
#[==========] 142 tests from 10 test suites ran. (209 ms total)
#[  PASSED  ] 142 tests.
#
#Output for assignment-11:
#[==========] 172 tests from 12 test suites ran. (371 ms total)
#[  PASSED  ] 172 tests.
#
#Output for assignment-12:
#[==========] 148 tests from 10 test suites ran. (238 ms total)
#[  PASSED  ] 148 tests.
#
#Output for assignment-13:
#[==========] 20 tests from 9 test suites ran. (396 ms total)
#[  PASSED  ] 20 tests.


# sample output with tail -n 6 (removed head -n 3)
#Output for assignment-05:
#
#[----------] Global test environment tear-down
#[==========] 195 tests from 36 test suites ran. (98 ms total)
#[  PASSED  ] 195 tests.
#
#Done building and running unit tests for assignment-05
#
#Output for assignment-06:
#
#[----------] Global test environment tear-down
#[==========] 120 tests from 12 test suites ran. (36 ms total)
#[  PASSED  ] 120 tests.
#
#Done building and running unit tests for assignment-06
#
#Output for assignment-07:
#
#[----------] Global test environment tear-down
#[==========] 71 tests from 10 test suites ran. (5 ms total)
#[  PASSED  ] 71 tests.
#
#Done building and running unit tests for assignment-07
#
#Output for assignment-08:
#
#[----------] Global test environment tear-down
#[==========] 55 tests from 12 test suites ran. (164 ms total)
#[  PASSED  ] 55 tests.
#
#Done building and running unit tests for assignment-08
#
#Output for assignment-09:
#
#[----------] Global test environment tear-down
#[==========] 143 tests from 23 test suites ran. (46 ms total)
#[  PASSED  ] 143 tests.
#
#Done building and running unit tests for assignment-09
#
#Output for assignment-10:
#
#[----------] Global test environment tear-down
#[==========] 142 tests from 10 test suites ran. (209 ms total)
#[  PASSED  ] 142 tests.
#
#Done building and running unit tests for assignment-10
#
#Output for assignment-11:
#
#[----------] Global test environment tear-down
#[==========] 172 tests from 12 test suites ran. (372 ms total)
#[  PASSED  ] 172 tests.
#
#Done building and running unit tests for assignment-11
#
#Output for assignment-12:
#
#[----------] Global test environment tear-down
#[==========] 148 tests from 10 test suites ran. (237 ms total)
#[  PASSED  ] 148 tests.
#
#Done building and running unit tests for assignment-12
#
#Output for assignment-13:
#
#[----------] Global test environment tear-down
#[==========] 20 tests from 9 test suites ran. (381 ms total)
#[  PASSED  ] 20 tests.
#
#Done building and running unit tests for assignment-13
#➜  src git:(main) ✗
