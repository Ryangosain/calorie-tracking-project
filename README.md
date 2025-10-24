# calorie-tracking-project
# tracker.py
# Author: RYAN
# Project: Daily Calorie Tracker CLI

# Function to collect meal data
def collect_meals():
    meals = []
    calories = []
    count = int(input("How many meals do you want to enter today? "))
    for i in range(count):
        meal = input(f"Enter name of meal {i+1}: ")
        cal = float(input(f"Enter calories for {meal}: "))
        meals.append(meal)
        calories.append(cal)
    return meals, calories

# Function to calculate total and average
def calculate_stats(calories):
    total = sum(calories)
    average = total / len(calories)
    return total, average

# Function to compare with daily limit
def check_limit(total):
    limit = float(input("Enter your daily calorie limit: "))
    if total > limit:
        print(" You have exceeded your daily calorie limit!")
    else:
        print(" You're within your daily calorie limit.")
    return limit

# Function to print summary
def print_summary(meals, calories, total, average):
    print("\nCalorie Summary:\n")
    print("Meal Name\tCalories")
    print("-----------------------------")
    for i in range(len(meals)):
        print(f"{meals[i]}\t\t{calories[i]}")
    print("-----------------------------")
    print(f"Total:\t\t{total}")
    print(f"Average:\t{round(average, 2)}")

# Main function to run the tracker
def run_tracker():
    print("Welcome to the Daily Calorie Tracker CLI!\n")
    meals, calories = collect_meals()
    total, average = calculate_stats(calories)
    limit = check_limit(total)
    print_summary(meals, calories, total, average)

# Run the program
run_tracker()
