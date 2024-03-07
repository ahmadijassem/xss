# xss
test
import random 

hang_man_pices = ["""
 
    +---+
    |   |
        |
        |
        |
        |
  ========= """, 
    """
    +---+
    |   |
    O   |
        |
        |
        |
  ========= """,
    """              
    +---+
    |   |
    O   |
    |   |
        |
        |
  ========= """,
    """              
    +---+
    |   |
    O   |
   /|   |
        |
        |
  ========= """,
    """              
    +---+
    |   |
    O   |
   /|\  |
        |
        |
  ========= """,
    """              
    +---+
    |   |
    O   |
   /|\  |
   /    |
        |
  ========= """,
    """              
    +---+
    |   |
    O   |
   /|\  |
   / \  |
        |
  ========= """]





random_list =["ugly","handsom","faul" ,"einfach","bra"]
mdnEins = random.choice(random_list)
display = ["_"] * len(mdnEins)
print(" ".join(display))
lives = 6

gussed_letters =[]
print(hang_man_pices[0])
while "_" in display and  lives > 0:
  gussed = input("please guss the letter:: ").lower()

  if gussed in gussed_letters:
    print(" you already have gussed that letter: try again ")
    print(f"you have {lives} more letf")
    continue
    
    

  gussed_letters.append(gussed)

  if gussed not in mdnEins:
    lives -= 1
    print(hang_man_pices[6 -lives])
  else:
    for possition in range(len(mdnEins)):
      if mdnEins[possition] == gussed:
         display[possition] = gussed
  print(" ".join(display))
  print(f"you have {lives} more letf")

if lives == 0:
  print("""
      *********
      you lost
      *********
    """)
  print(hang_man_pices[-1])


else:
  print("""
     ********
     you win
     ********
  """)
