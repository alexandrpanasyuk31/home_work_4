import random


def get_numbers_ticket(min, max, quantity):
    if min < 1:
        return []
    if max > 1000:
        return []
    if min > max:
        return []
    if quantity < 1 or quantity > max - min + 1:
        return []
    numbers = set()
    while len(numbers) < quantity:
        number = random.randint(min, max)
        numbers.add(number)
    result = sorted(numbers)
    return result


lottery_numbers = get_numbers_ticket(1, 49, 6)
print("Ваші лотерейні числа:", lottery_numbers)
