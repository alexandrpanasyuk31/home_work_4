from datetime import datetime, timedelta


def get_upcoming_birthdays(users):
    upcoming_birthdays = []
    today = datetime.today().date()

    for user in users:
        # перетворюємо рядок у дату
        birthday = datetime.strptime(user["birthday"], "%Y.%m.%d").date()

        # день народження в цьому році
        try:
            birthday_this_year = birthday.replace(year=today.year)
        except ValueError:
            # якщо це 29 лютого, а рік не високосний, беремо 1 березня
            birthday_this_year = datetime(today.year, 3, 1).date()

        # якщо день народження вже минув, беремо наступний рік
        if birthday_this_year < today:
            try:
                birthday_this_year = birthday.replace(year=today.year + 1)
            except ValueError:
                birthday_this_year = datetime(today.year + 1, 3, 1).date()

        days_left = (birthday_this_year - today).days
        if 0 <= days_left <= 7:
            congratulation_date = birthday_this_year

            if congratulation_date.weekday() == 5:
                congratulation_date = congratulation_date + timedelta(days=2)
            elif congratulation_date.weekday() == 6:
                congratulation_date = congratulation_date + timedelta(days=1)

            upcoming_birthdays.append({
                "name": user["name"],
                "congratulation_date": congratulation_date.strftime("%Y.%m.%d")
            })

    return upcoming_birthdays


users = [
    {"name": "John Doe", "birthday": "1985.01.23"},
    {"name": "Jane Smith", "birthday": "1990.01.27"},
    {"name": "Alice Johnson", "birthday": "1995.01.30"},
    {"name": "Bob Brown", "birthday": "2000.02.01"}

]

upcoming_birthdays = get_upcoming_birthdays(users)
print("Список привітань на цьому тижні:", upcoming_birthdays)
