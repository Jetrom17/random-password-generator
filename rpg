import random
import string

def generate_password(length=12, use_lowercase=True, use_uppercase=True, use_digits=True, use_special=True):
    characters = ""
    if use_lowercase:
        characters += string.ascii_lowercase
    if use_uppercase:
        characters += string.ascii_uppercase
    if use_digits:
        characters += string.digits
    if use_special:
        characters += string.punctuation

    if not characters:
        raise ValueError("Pelo menos um conjunto de caracteres deve ser selecionado.")

    password = ''.join(random.choice(characters) for _ in range(length))
    
    # Avaliação de força da senha
    strength = evaluate_password_strength(password)

    return password, strength

def evaluate_password_strength(password):
    # Avaliação simples de força da senha com base no comprimento
    if len(password) < 8:
        return "Fraca"
    elif len(password) < 12:
        return "Média"
    else:
        return "Forte"

if __name__ == "__main__":
    length = int(input("Comprimento da senha desejado: "))
    use_lowercase = input("Incluir letras minúsculas? (S/n): ").strip().lower() != "n"
    use_uppercase = input("Incluir letras maiúsculas? (S/n): ").strip().lower() != "n"
    use_digits = input("Incluir dígitos? (S/n): ").strip().lower() != "n"
    use_special = input("Incluir caracteres especiais? (S/n): ").strip().lower() != "n"

    password, strength = generate_password(length, use_lowercase, use_uppercase, use_digits, use_special)
    print("Senha segura gerada:", password)
    print("Força da senha:", strength)
