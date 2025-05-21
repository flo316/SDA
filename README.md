def isBalanced(s: str) -> bool:
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    
    for char in s:
        if char in mapping.values():  # Buka kurung
            stack.append(char)
        elif char in mapping.keys():  # Tutup kurung
            if not stack or stack.pop() != mapping[char]:
                return False
    return not stack  # Stack harus kosong jika seimbang

# Test cases
print(isBalanced("([]{})"))  # True
print(isBalanced("[(()]"))   # False
print(isBalanced("{[}]"))    # False
print(isBalanced("({[]})"))  # True
print(isBalanced("("))       # False
