class Agent:
    def __init__(self, name):
        self.name = name

    def choose(self, choice):
        if choice not in ['A', 'B', 'C']:
            raise ValueError("Invalid choice")

        # Agent X contradicts the choice
        if self.name == 'X':
            contradicted_choice = 'B' if choice == 'A' else ('A' if choice == 'B' else 'B')

        # Agent X1 contradicts the choice and prints it
        elif self.name == 'X1':
            contradicted_choice = 'A' if choice == 'B' else ('B' if choice == 'A' else 'C')
            print(f"{self.name} chooses {contradicted_choice}")

        # Agent X2 contradicts the choice and prints it
        elif self.name == 'X2':
            contradicted_choice = 'B' if choice == 'A' else ('A' if choice == 'B' else 'C')
            print(f"{self.name} chooses {contradicted_choice}")

        # Agent X3 does not contradict the choice and prints it
        elif self.name == 'X3':
            contradicted_choice = choice
            print(f"{self.name} chooses {contradicted_choice}")

        return contradicted_choice

def get_user_choice(agent_name):
    while True:
        user_choice = input(f"{agent_name}: Choose A, B, or C: ").strip().upper()
        if user_choice in ['A', 'B', 'C']:
            return user_choice
        print("Invalid choice. Choose A, B, or C.")

def main():
    agents = [Agent('X'), Agent('X1'), Agent('X2'), Agent('X3')]

    while True:
        # Agent X initializes with a user choice
        user_choice = get_user_choice('Agent X')
        choice = agents[0].choose(user_choice)

        # Agent X1 processes the choice from Agent X
        choice = agents[1].choose(choice)

        # Agent X2 asks for user input and processes it
        user_choice = get_user_choice('Agent X2')
        choice = agents[2].choose(user_choice)

        # Agent X3 asks for user input and processes it
        user_choice = get_user_choice('Agent X3')
        agents[3].choose(user_choice)

        print("Restarting the cycle...\n")

if __name__ == "__main__":
    main()
