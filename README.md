# Caesar Cipher (Python Edition)

## Description

This Python program implements the classic Caesar Cipher, a simple and widely known encryption technique. It allows users to encode (encrypt) or decode (decrypt) text by shifting each letter a certain number of positions down or up the alphabet. Non-alphabetic characters (like spaces and punctuation) are preserved.

## How to Use

1.  **Run the script:** Execute the Python script. You will see a welcome message and an ASCII art logo.
2.  **Choose operation:** The program will ask you to type either 'encode' to encrypt a message or 'decode' to decrypt a message. Enter your choice and press Enter.
3.  **Enter your message:** You will then be prompted to type your message. Enter the text you want to encrypt or decrypt and press Enter. The message will be converted to lowercase.
4.  **Enter the shift number:** Next, you need to enter the 'shift number'. This is the number of positions each letter in your message will be shifted. Enter an integer and press Enter.
5.  **View the result:** The program will then display the encoded or decoded result.
6.  **Continue or exit:** You will be asked if you want to go again. Type 'yes' to perform another encoding or decoding, or type 'no' to exit the program.

## Functionality

* **Encoding (Encryption):** Shifts each letter in the input text forward in the alphabet by the specified shift amount. For example, with a shift of 3, 'a' becomes 'd', 'b' becomes 'e', and so on. The alphabet wraps around, so 'z' shifted by 1 becomes 'a'.
* **Decoding (Decryption):** Shifts each letter in the input text backward in the alphabet by the specified shift amount (effectively a negative shift).
* **Alphabet Handling:** Works with the lowercase English alphabet.
* **Non-alphabetic Character Handling:** Characters that are not in the alphabet are left unchanged.
* **Shift Amount:** Accepts an integer as the shift value. The program handles shifts larger than the alphabet length using the modulo operator (`%`).
* **Looping:** Allows the user to perform multiple encoding or decoding operations without restarting the program.
* **User Interface:** Provides a simple text-based interface using the `input()` and `print()` functions.
* **ASCII Art:** Displays a logo at the beginning using the `art` module.

## Requirements

* Python 3.x
* `art` module (can be installed via pip: `pip install art`)

## Installation

1.  Ensure you have Python installed on your system.
2.  Install the `art` module if it's not already installed:
    ```bash
    pip install art
    ```
3.  Save the provided code as a `.py` file (e.g., `caesar_cipher.py`).
4.  Run the script using a Python interpreter:
    ```bash
    python caesar_cipher.py
    ```

## Code Explanation

* **`import art`:** Imports the `art` module to display an ASCII art logo.
* **`print(art.logo)`:** Prints the logo.
* **`print("Welcome to Ceaser Cypher! (Python Edition)")`:** Prints a welcome message.
* **`alphabet`:** A list containing all lowercase letters of the English alphabet.
* **`caesar(original_text, shift_amount, encode_or_decode)` function:**
    * Takes the input `original_text`, the `shift_amount`, and the `encode_or_decode` direction ('encode' or 'decode') as arguments.
    * Initializes an empty string `output_text` to store the result.
    * If `encode_or_decode` is 'decode', it negates the `shift_amount` to perform a backward shift.
    * Iterates through each `letter` in the `original_text`.
    * If the `letter` is not in the `alphabet`, it's added directly to the `output_text` (handling non-alphabetic characters).
    * If the `letter` is in the `alphabet`:
        * It finds the current `index` (position) of the `letter` in the `alphabet`.
        * It calculates the `shifted_position` by adding the `shift_amount` to the current `index`.
        * The modulo operator (`% len(alphabet)`) is used to handle wrap-around if the `shifted_position` goes beyond the bounds of the alphabet (e.g., 'z' shifted by 1 becomes 'a').
        * The letter at the `shifted_position` in the `alphabet` is appended to the `output_text`.
    * Finally, it prints the encoded or decoded result.
* **Main Loop (`while should_continue`):**
    * Sets a flag `should_continue` to `True` to start the loop.
    * Prompts the user for the `direction` (encode or decode).
    * Prompts the user for the `text` message.
    * Prompts the user for the `shift` number and converts it to an integer.
    * Calls the `caesar` function with the user's input.
    * Asks the user if they want to continue. If they type 'no', the `should_continue` flag is set to `False`, and the loop ends with a farewell message.

## Potential Improvements

* Handle uppercase letters as well.
* Allow the user to choose a different alphabet.
* Implement error handling for invalid input.
* Create a more user-friendly interface (e.g., a graphical user interface).
