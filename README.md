# Play
class Player:
    def __init__(self, name, age, position):
        self.name = name
        self.age = age
        self.position = position

class Team:
    def __init__(self, name):
        self.name = name
        self.players = []

    def add_player(self, player):
        self.players.append(player)

    def remove_player(self, player_name):
        self.players = [player for player in self.players if player.name != player_name]

    def display_players(self):
        print(f"Players in team {self.name}:")
        for player in self.players:
            print(f"Name: {player.name}, Age: {player.age}, Position: {player.position}")

def main():
    team_name = input("Enter team name: ")
    team = Team(team_name)

    while True:
        print("\nMenu:")
        print("1. Add player")
        print("2. Remove player")
        print("3. Display players")
        print("4. Quit")

        choice = input("Enter your choice: ")

        if choice == '1':
            name = input("Enter player's name: ")
            age = int(input("Enter player's age: "))
            position = input("Enter player's position: ")
            player = Player(name, age, position)
            team.add_player(player)
            print("Player added successfully!")

        elif choice == '2':
            name = input("Enter player's name to remove: ")
            team.remove_player(name)
            print("Player removed successfully!")

        elif choice == '3':
            team.display_players()

        elif choice == '4':
            print("Exiting program...")
            break

        else:
            print("Invalid choice, please try again.")

if __name__ == "__main__":
    main()
