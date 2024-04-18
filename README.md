class User:
    def __init__(self, username, email, password):
        self.username = username
        self.email = email
        self.password = password

    def update_profile(self, new_username, new_email):
        self.username = new_username
        self.email = new_email

class UserManager:
    def __init__(self):
        self.users = []

    def register_user(self, username, email, password):
        new_user = User(username, email, password)
        self.users.append(new_user)
        return new_user

    def find_user_by_username(self, username):
        for user in self.users:
            if user.username == username:
                return user
        return None

# Приклад використання
user_manager = UserManager()
new_user = user_manager.register_user("john_doe", "john@example.com", "password123")
print("Registered user:", new_user.username)
