from datetime import datetime


def get_days_from_today(date):
    try:
        given_date = datetime.strptime(date, "%Y-%m-%d").date()
    except ValueError:
        print("Incorrect data format, print YYYY-ММ-DD")
        return None

    today = datetime.today().date()
    difference = today - given_date
    return difference.days
get_days_from_today("2025-06-01")
print(get_days_from_today("2025-06-01"))
