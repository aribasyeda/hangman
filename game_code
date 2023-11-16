from hangman_art import stages, logo
from hangman_words import word_list
import random
from replit import clear

print(logo)

chosen_word = random.choice(word_list)
word_length = len(chosen_word)

display = []
for _ in range(word_length):
    display += "_"
print(f"{' '.join(display)}")

end_of_game = False
lives = 6
prev_guessed_letter = []

while not end_of_game:

  guess = input("\n 👉 Guess a letter: ").lower()

  clear()

  if guess in prev_guessed_letter:
    print(f"\n 📢 You already guessed '{guess}'. Try another letter. \n")
    continue

  prev_guessed_letter.append(guess)

  if guess in chosen_word:
    print(f"\n ✔️  CORRECT '{guess}' is in the word 🎊\n")
    for position in range(word_length):
        letter = chosen_word[position]
        if letter == guess:
          display[position] = letter          
  else:
    lives -= 1
    print(f"\n ❌ Oh oh you gussed '{guess}', that is not in the word.\n")
    print(f"\n -1 life point 💔\n")
    if lives == 1:
      print("\n 🚨 1 LIFE POINT REMANING 🚨\n")
    if lives == 0:
      end_of_game = True
      print(f"😭😭😭 GAME OVER 💔 The word was {chosen_word} 😭😭😭 \n")

  if "_" not in display:
    end_of_game = True
    print(f"🎉🎉🎉  You defeated hangman 🎉 The word was {chosen_word} 🎉🎉🎉 \n")

  print(f"{' '.join(display)}")
  
  current_stage = stages[lives]
  print(f"{current_stage}")

  if lives > 0:
    print(f"Life points remaining: {' ❤️ ' * lives}\n")
