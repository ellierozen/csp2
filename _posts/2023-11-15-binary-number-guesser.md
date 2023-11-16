---
toc: true
comments: false
layout: post
title: Number guesser
description: Example Blog!!!  This shows planning and notes from hacks.
type: plans
courses: { compsci: {week: 0} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Guessing Game</title>
    <style>
        body {
            font-family: 'Courier New', Courier, monospace;
            margin: 20px;
        }
        pre {
            background-color: #f4f4f4;
            padding: 15px;
            border: 1px solid #ddd;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
    </style>
</head>
<body>

<h1>Binary Guessing Game Code</h1>

<pre>
<code>
import random

def generate_binary_number(length):
    return ''.join(random.choice('01') for _ in range(length))

def get_player_guess():
    while True:
        guess = input("Enter your guess (a binary number): ")
        if all(bit in '01' for bit in guess):
            return guess
        else:
            print("Invalid input. Please enter a valid binary number.")

def play_binary_guessing_game():
    print("Welcome to the Binary Guessing Game!")
    print("I've generated a binary number. Try to guess it!")

    binary_number_length = 8  # You can adjust the length of the binary number as desired
    secret_number = generate_binary_number(binary_number_length)

    attempts = 0
    while True:
        player_guess = get_player_guess()
        attempts += 1

        if player_guess == secret_number:
            print(f"Congratulations! You guessed the correct binary number: {secret_number}")
            print(f"It took you {attempts} attempts.")
            break
        else:
            print("Incorrect! Try again.")

if __name__ == "__main__":
    play_binary_guessing_game()
</code>
</pre>

</body>
</html>
