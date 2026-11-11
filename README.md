## Welcome to My Bash Scripting Projects 👋

This repository contains a collection of command-line applications and automation scripts built using Bash. Developed as part of a hands-on learning journey, these projects demonstrate core scripting fundamentals, including user input handling, conditional branching, loops, arrays, randomized data generation, and script orchestration.

Whether you're looking to run interactive questionnaires, test your luck with a fortune teller or bingo number generator, or run the entire suite through a single master script, this repository highlights practical, lightweight terminal automation!

## Interactive Questionnaire Script

This lightweight command-line script written in Bash prompts users for their personal details—such as their name, hometown, and favorite coding platform—and dynamically outputs a customized greeting using the collected input.

```bash

#!/bin/bash

echo -e "\n~~ Questionnaire ~~\n"

QUESTION1="What's your name?"
QUESTION2="Where are you from?"
QUESTION3="What's your favorite coding website?"

echo $QUESTION1
read NAME

echo $QUESTION2
read LOCATION

echo $QUESTION3
read WEBSITE

echo -e "\nHello $NAME from $LOCATION. I learned that your favorite coding website is $WEBSITE!"
```

## Surprise Questionnaire Script

This interactive Bash script prompts the user for their age, occupation, and marital status, and then compiles those answers into a playful summary confirmation sentence.

```bash

#!/bin/bash

echo -e "\n~~ Surprise ~~\n"

QUESTION1="How old are you?"
QUESTION2="What's your occupation?"
QUESTION3="What's your marital status?"

echo $QUESTION1
read AGE

echo $QUESTION2
read JOB

echo $QUESTION3
read STATUS

echo -e "\nYou're are a $AGE year old $JOB and $STATUS?"
```

## Countdown Timer Script

This Bash script takes a positive integer as a command-line argument and performs a one-second delayed countdown down to zero. If no valid positive integer is provided, it outputs an instructional error message.

```bash

#!/bin/bash

# Program that counts down to zero from a given argument

  echo -e "\n~~ Countdown Timer ~~\n"

if [[ $1 -gt 0 ]]
then
: '
  for (( i = $1; i >= 0; i-- ))
do
  echo $i
  sleep 1
done
'
I=$1
while [[ $I -ge 0 ]]
do
  echo $I
  (( I-- ))
  sleep 1
done
else
  echo "Include a positive integer as the first argument."
fi
```

## Bingo Number Generator Script

This Bash script generates a random number between 1 and 75, uses conditional statements to categorize it into the traditional Bingo letter columns (B, I, N, G, or O) based on its value, and prints out the formatted result.

```bash

#!/bin/bash

# Bingo Number Generator.

echo -e "\n~~ Bingo Number Generator ~~\n"

NUMBER=$(( $RANDOM % 75 + 1 ))
TEXT="The next number is, ."

echo $NUMBER

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
  echo "The next number is, B:$NUMBER"
elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
  echo "The next number is, I:$NUMBER"
elif (( NUMBER < 46 ))
then
  echo $TEXT N:$NUMBER
  echo "The next number is, N:$NUMBER"
elif [[ $NUMBER -lt 61 ]]
then
  echo $TEXT G:$NUMBER
  echo "The next number is, G:$NUMBER"
else
  echo $TEXT O:$NUMBER
  echo "The next number is, O:$NUMBER"
fi
```

## Fortune Teller Script

This Bash script serves as an interactive fortune teller that prompts the user to ask a yes-or-no question, validates that the input ends with a question mark using a loop and regular expressions, and outputs a randomly selected fortune from a predefined array.

```bash

#!/bin/bash
#Program to tell a persons fortune

echo -e "\n~~ Fortune Teller ~~\n"

RESPONSES=("Yes" "No" "Maybe" "Outlook good" "Don't count on it" "Ask again later")
N=$(( RANDOM%6 ))

GET_FORTUNE() {
  if [[ ! $1 ]]
  then
    echo Ask a yes or no question:
  else
    echo Try again. Make sure it ends with a question mark:
  fi

  read QUESTION

  echo -e "\n${RESPONSES[$N]}"
}

GET_FORTUNE
until [[ $QUESTION =~ \?$ ]]
do
  GET_FORTUNE again
done
```

## Master Program Launcher Script

This Bash script acts as a master runner or orchestrator, sequentially executing five separate custom scripts (**questionnaire.sh**, **surprise.sh**, **countdown.sh**, **bingo.sh**, and **fortune.sh**) in a single streamlined workflow.

```bash

#!/bin/bash

#Program to run my other five programs

./questionnaire.sh

./surprise.sh

./countdown.sh 3

./bingo.sh

./fortune.sh
```
## Comprehensive CLI Suite Overview

This final collection brings together interactive user prompts, conditional logic, looping structures, arrays, and script orchestration into a cohesive command-line toolkit. From gathering custom user input and managing countdown loops to generating randomized bingo outcomes, predicting fortunes with validation checks, and launching automated sequences, these scripts demonstrate core automation and scripting proficiency in Bash.





