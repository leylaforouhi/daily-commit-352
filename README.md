MORSE = {
    "A": ".-", "B": "-...", "C": "-.-.",
    "D": "-..", "E": ".", "F": "..-.",
    "G": "--.", "H": "....", "I": "..",
    "J": ".---", "K": "-.-", "L": ".-..",
    "M": "--", "N": "-.", "O": "---",
    "P": ".--.", "Q": "--.-", "R": ".-.",
    "S": "...", "T": "-", "U": "..-",
    "V": "...-", "W": ".--", "X": "-..-",
    "Y": "-.--", "Z": "--..",
    "0": "-----", "1": ".----",
    "2": "..---", "3": "...--",
    "4": "....-", "5": ".....",
    "6": "-....", "7": "--...",
    "8": "---..", "9": "----.",
    " ": "/"
}

REVERSE = {value: key for key, value in MORSE.items()}

def encode(text):
    return " ".join(
        MORSE.get(char, "?")
        for char in text.upper()
    )

def decode(code):
    result = []

    for symbol in code.split():
        result.append(REVERSE.get(symbol, "?"))

    return "".join(result).replace("/", " ")

def main():
    while True:
        print("\n1. Text to Morse")
        print("2. Morse to Text")
        print("3. Exit")

        choice = input("Choose: ")

        if choice == "1":
            text = input("Enter text: ")
            print("Morse:", encode(text))

        elif choice == "2":
            code = input("Enter Morse code: ")
            print("Text:", decode(code))

        elif choice == "3":
            break

        else:
            print("Invalid choice!")

if __name__ == "__main__":
    main()
