# Text_analyzer
text = input("Enter a string: ")


pure_words = []
mixed_words = []
special_characters = []
combined_numbers = ""
total_of_numbers = 0


for word in text.split():


    if word.isalpha():
        pure_words.append(word)


    elif any(c.isalpha() for c in word) and any(c.isdigit() for c in word):
        mixed_words.append(word)


    num_part = ""
    for char in word:
        if char.isdigit():
            num_part += char
        elif not char.isalnum():
            special_characters.append(char)

    if num_part:
        total_of_numbers += int(num_part)
        combined_numbers += num_part


print("\n--- Results ---")
print("Only Words:", pure_words)
print("Mixed Words (Letters + Digits):", mixed_words)
print("Concatenated Numbers:", combined_numbers)
print("Sum of All Numbers Found:", total_of_numbers)
print("Count of Words + Mixed Words:", len(pure_words) + len(mixed_words))

if special_characters:
    print("Special Characters Found:", special_characters)
else:
    print("No Special Characters Found.")


