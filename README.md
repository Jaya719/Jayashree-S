# Jayashree-S
CodeAlpha
import random

# List of predefined words
word_list = ["apple", "mango", "grape", "lemon", "peach"]

# Choose a random word
secret_word = random.choice(word_list)
guessed_letters = []
attempts = 6

print("🎯 Welcome to Hangman Game!")
print("Guess the word letter by letter.")

# Display with underscores
while attempts > 0:
    display_word = ""
    for letter in secret_word:
        if letter in guessed_letters:
            display_word += letter + " "
        else:
            display_word += "_ "

    print("\nWord:", display_word.strip())

    # Check if word guessed completely
    if "_" not in display_word:
        print("\n🎉 Congratulations! You guessed the word:", secret_word)
        break

    guess = input("Enter a letter: ").lower()

    if guess in guessed_letters:
        print("⚠️ You've already guessed that letter.")
        continue

    guessed_letters.append(guess)

    if guess in secret_word:
        print("✅ Good guess!")
    else:
        print("❌ Wrong guess!")
        attempts -= 1
        print("Remaining attempts:", attempts)

if attempts == 0:
    print("\n💀 Game Over! The word was:", secret_word)
