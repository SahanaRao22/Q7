def validation(passwd):
    special_symbol = ['!', '"', '#', '$', '%', '&', "'", '(', ')', '*', '+', '-', '.', '/', ':', ';', '<', '=', '>', '?', '@', '[', '\\', ']', '^', '_', '`', '{', '|', '}', '~', ',']
    value = True
    if not len(passwd)>6:
        print("The password should be greater than 6 characters")
        value=False
    if not len(passwd)<16:
        print("The password should be less than 20 characters")
        value=False
    if not any(char.isdigit() for char in passwd):
        print('Password should have at least one numeral')
        value = False

    if not any(char.isupper() for char in passwd):
        print('Password should have at least one uppercase letter')
        value = False

    if not any(char.islower() for char in passwd):
        print('Password should have at least one lowercase letter')
        value = False
    if not any(char in special_symbol for char in passwd):
        print('Password should have at least one symbol')
        value = False
    return value


def main():
    passwd = input()

    if not validation(passwd):
        print("Invalid Password !!")
    else:
        print("Password is valid")
if __name__ == '__main__':
    main()


