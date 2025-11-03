import tkinter as tk #Imports the Tkinter program onto the code
import random # Self created data set to be randomised at the end
# (Stack Overflow, 2020) and (Visual Studio Code, n.d.) taught me how to import it onto the project

root = tk.Tk() # Create a frame/window to hold the option buttons (Python Software Foundation, 2019)
root.title("🎵 Hear Me Out Quiz") #Title of the Tkinter window
root.geometry("1200x1200") # Size of the Tkinter window
root.configure(bg="#90ee90") # Background colour to match the aesthetic of the pitch

# Set up of Tkniter to help visualise the quiz (Amos, 2022)

question_label = tk.Label(root, text='', font=("Arial", 50)) #define the question label
question_label.pack(pady=30)

options_frame = tk.Frame(root, bg="#90ee90")
options_frame.pack(pady=20)

# Definition of Result
status_label = tk.Label(root, text="", font=("Arial", 30, "italic"))
status_label.pack(pady=20)

#Genres, Artists and Songs that have the chance of being generated as answers in the quiz, from the manually created data set from Week 7
genres = {
    "Pop": [
        ("Sabrina Carpenter", "Espresso"),
        ("Olivia Rodrigo", "Bad Idea Right"),
        ("Lady Gaga", "Bad Romance"),
    ],
    "Rock": [
        ("ACDC", "Thunderstruck"),
        ("The White Stripes", "Seven Nations Army"),
        ("The Verve", "Bittersweet Symphony"),
    ],
    "HipHop": [
        ("50Cent", "In Da Club"),
        ("Eminem", "Lose Yourself"),
        ("Salt N Pepper", "Push It"),
    ],
    "R&B": [
        ("Summer Walker", "Girl Need Love"),
        ("The Weeknd", "Timeless"),
        ("SZA", "Snooze"),
    ],
    "Club": [
        ("DJ Snake", "Lean On"),
        ("Avicii", "Levels"),
        ("Tinashe", "No Broke Boys"),
    ],
    "Study": [
        ("Beach House", "Space Song"),
        ("Harry Styles", "Matilda"),
        ("J.Alke", "Close"),
    ],
    "Indie": [
        ("Noah Kahan", "Stick Season"),
        ("Tame Impala", "Boarderline"),
        ("Pheobe Bridges", "Scott Street"),
    ],
    "Country": [
        ("Dolly Parton", "Jolene"),
        ("Kacey Musgraves", "Deeper Well"),
        ("Luke Combs", "Fast Car"),
    ]
    }

# Randomise the artisit and song pairs within each genre, (W3Schools, n.d.)
for genre in genres:
    random.shuffle(genres[genre])

# Questions being asked in the quiz
answers = [
    "How Old Are You?",
    "What Are You Doing Right Now?",
    "Which Drink Would You Choose?",
    "Pick a Film:",
    "Pick a TV Show:",
    "What Time of Day is it?",
    "Do you want to Sing or just Listen?",
]

# Tracker for scores
question_index = 0
scores = {genre: 0 for genre in genres}

# Show result function
def show_result():
    top_genre = max(scores, key=scores.get)
    artist, song = random.choice(genres[top_genre])
    result = f"Your genre: {top_genre}\nTry listening to 🎧 {song} by {artist}"
    question_label.config(text="🎶 Your recommended genre and song") # Text when song, artist and genre is going to be generated
    status_label.config(text=result, font=("Arial", 30, "italic"))
    
 # Function to handle the answers
def handle_answers(choice):
    global question_index

# Scoring, using (Rod Milstead, 2023) as a basis of the 
    if question_index == 0: # Answer for Age question index
        if choice == "Under 10":
            scores["Pop"] += 1
        elif choice == "11-12":
            scores["Indie"] += 1
        elif choice == "13-16":
            scores["HipHop"] += 1
        elif choice == "17-20":
            scores["Club"] += 1
        elif choice == "21-25":
            scores["R&B"] += 1
        elif choice == "26-35":
            scores["Rock"] += 1
        elif choice == "36-45":
            scores["Study"] += 1
        elif choice == "Above 45":
            scores["Country"] += 1
    
    elif question_index == 1: # Answer for Activity question index
        if choice == "Driving/Commuting":
            scores["HipHop"] += 1
            scores["R&B"] += 1
        elif choice == "Studying":
            scores["Indie"] += 1
            scores["Study"] += 1
        elif choice == "Working":
            scores["Rock"] += 1
        elif choice == "Getting ready":
            scores["Pop"] += 1
        elif choice == "Exercising":
            scores["Club"] += 1
        elif choice == "Other":
            scores["Country"] += 1
    
    elif question_index == 2: # Answer for Drink question index
        if choice == "Water":
            scores["Study"] += 1
        elif choice == "CocaCola":
            scores["Pop"] += 1
        elif choice == "Energy drink":
            scores["R&B"] += 1
            scores["Rock"] += 1
        elif choice == "Tea":
            scores["Indie"] += 1
        elif choice == "Cocktail":
            scores["Club"] += 1
        elif choice == "Coffee":
            scores["HipHop"] += 1
        elif choice == "Beer":
            scores["Country"] += 1

    elif question_index == 3: # Answer for Film question index
        if choice == "School of Rock":
            scores["Rock"] += 1
        elif choice == "Perks of Being a Wallflower":
            scores["Indie"] += 1
        elif choice == "Project X":
            scores["Club"] += 1
        elif choice == "The Godfather":
            scores["HipHop"] += 1

    elif question_index == 4: # Answer for TV question index
        if choice == "The Summer I Turned Pretty":
            scores["Pop"] += 1
        elif choice == "Yellowstone":
            scores["Country"] += 1
        elif choice == "Succession":
            scores["Study"] += 1
        elif choice == "Abbott Elementary":
            scores["R&B"] += 1

    elif question_index == 5: # Answer for Time question index
        if choice == "Morning":
            scores["Pop"] += 1
        elif choice == "Midday":
            scores["Rock"] += 1
            scores["R&B"] += 1
        elif choice == "Afternoon":
            scores["Country"] += 1
            scores["HipHop"] += 1
        elif choice == "Evening":
            scores["Study"] += 1
            scores["Indie"] += 1
        elif choice == "Late night":
            scores["Club"] += 1

    elif question_index == 6: # Answer for Song/Listen question index
        if choice == "Sing along":
            scores["Pop"] += 1; scores["HipHop"] += 1; scores["Club"] += 1; scores["Rock"] += 1
        elif choice == "Just listen":
            scores["Study"] += 1; scores["Indie"] += 1; scores["Country"] += 1; scores["R&B"] += 1

# If there are no more questions, show result
    question_index +=1
    if question_index >= len(answers):
        show_result()
    else:
        show_question()

# Function to show question
def show_question():
    global question_index
    question_label.config(text=answers[question_index]) # Shows current question
    
    for widget in options_frame.winfo_children(): # Clears the previous question/buttons
        widget.destroy()

# Determines options based on the question index
    if question_index == 0:
            options = ["Under 10", "11-12", "13-16", "17-20", "21-25", "26-35", "36-45", "Above 45"]
        
    elif question_index == 1:
            options = ["Driving or Commuting", "Studying", "Working", "Getting Ready", "Exercising", "Other"]
        
    elif question_index == 2:
            options = ["Water", "CocaCola", "Energy drink", "Tea", "Cocktail", "Coffee", "Beer"]
    
    elif question_index == 3:
            options = ["School of Rock", "Perks of Being a Wallflower", "Project X", "The Godfather"]
    
    elif question_index == 4:
            options = ["The Summer I Turned Pretty", "Yellowstone", "Succession", "Abbott Elementary"]
    
    elif question_index == 5:
            options = ["Morning", "Midday", "Afternoon", "Evening", "Late night"]

    elif question_index == 6:
            options = ["Sing along", "Just listen"]
    else:
        options = []

# Creates the buttons for the available options (TKinter, 2022), (Amos, 2022)
    for option in options: # Options in the list of strings
        tk.Button(options_frame,
            text=option, # Button Text
            width=30,
            font=("Arial", 30),
            bg="#444141",
            command=lambda o=option: handle_answers(o) # call function (W3Schools, 2019)
                ).pack(pady=5)

# Links up tknitner to run the quiz
show_question()
root.mainloop()