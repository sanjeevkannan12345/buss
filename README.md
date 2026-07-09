def ticket_booking_system():
    print("\n=== Ticket Booking System ===\n")
    restart = 'Y'

    while restart.lower() not in ('n', 'no'):
        print("1. Check PNR status")
        print("2. Ticket Reservation")
        print("3. Exit")

        # Validate menu choice
        try:
            option = int(input("\nEnter your option (1-3): "))
        except ValueError:
            print("Invalid input! Please enter a number between 1 and 3.\n")
            continue

        if option == 1:
            print("\nYour PNR status is: T3\n")

        elif option == 2:
            try:
                people = int(input("\nEnter number of tickets you want: "))
                if people <= 0:
                    print("Number of tickets must be positive.\n")
                    continue
            except ValueError:
                print("Invalid number of tickets.\n")
                continue

            passengers = []
            for i in range(people):
                name = input(f"Enter name of passenger {i+1}: ").strip()
                try:
                    age = int(input(f"Enter age of passenger {i+1}: "))
                except ValueError:
                    print("Invalid age. Please enter a number.\n")
                    break
                gender = input(f"Enter gender of passenger {i+1} (M/F/O): ").strip().upper()
                passengers.append({"Name": name, "Age": age, "Gender": gender})

            print("\n--- Ticket Reservation Summary ---")
            for idx, p in enumerate(passengers, start=1):
                print(f"{idx}. {p['Name']} - Age: {p['Age']} - Gender: {p['Gender']}")
            print("Tickets booked successfully!\n")

        elif option == 3:
            print("Thank you for using the Ticket Booking System!")
            break

        else:
            print("Invalid option! Please choose between 1 and 3.\n")
            continue

        restart = input("Do you want to continue? (Y/N): ")

# Run the system
if __name__ == "__main__":
    ticket_booking_system()
