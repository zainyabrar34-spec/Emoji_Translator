This Python project is an Emoji Translator that replaces words with emojis based on a predefined dictionary. Users can type any sentence, and the program will translate it into emoji-rich text. It also saves all translations into a file for future reference.

def emoji_translator(text):
    emoji_dict = {
        "hi":"👋",
        "happy": "😊",
        "sad": "😢",
        "love": "❤️",
        "angry": "😡",
        "food": "🍕",
        "cat": "🐱",
        "dog": "🐶",
        "sun": "☀️",
        "moon": "🌙",
        "star": "⭐",
        "school": "🏫",
        "book": "📚",
        "computer": "💻",
        "music": "🎶",
        "game": "🎮",
        "birthday": "🎂",
        "car": "🚗",
        "travel": "✈️",
        "coffee": "☕",
        "flower": "🌸",
        "rain": "🌧️",
        "fire": "🔥",
        "phone": "📱",
        "money": "💰",
        "cake": "🍰",
        "smile": "😄",
        "friends":"🫂",
        "cool":"😎",
        "me":"🙋‍♀️",
        "oh oh":"🤦‍♀️",
        "speak":"🗣️",
        "rainbow":"🌈",
        "bouquet":"💐",
        "watching":"👀",
        "watch":"⌚",
        "ring":"💍"
        }

    words = text.split()
    translated = []

    for word in words:
        if word.lower() in emoji_dict:
            translated.append(emoji_dict[word.lower()])
        else:
            translated.append(word)

    return " ".join(translated)

print("🌟 Welcome to Emoji Translator! 🌟")
print("Type a sentence and see the magic! (Type 'exit' to quit)\n")

while True:
    user_input = input("Enter a sentence: ")

    if user_input.lower() == "exit":
        print("Goodbye! 👋 Thanks for using Emoji Translator.")
        break

    result = emoji_translator(user_input)
    print("✨ Translated Text:", result)

    with open("translations.txt", "a", encoding="utf-8") as f:
        f.write(user_input + " --> " + result + "\n")

    print("-" * 50)  # separator for neat output
