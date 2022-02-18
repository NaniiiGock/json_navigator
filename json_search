"""module for navigation through the .json file"""

import json
def recur(object1):
    """
    this is the recursive function for looking for the
    information in the file
    it has 3 options how to show the object
    depending on the file type:

    - if it is a dictionary it shows the keys

    - if it is the list it shows the number of objects inside
    and asks for the index of the list object that must be shown

    - if is the object of other types the function just prints it
    as an answer

    --- the user has an option to go back to the first level
    where he is choosing the section but without
    choosing the file one more time

    """
    print("if you want to go back print 'b', else: Enter ")
    inp = input(">>> ")
    if inp == "b":
        print("<<< ")
        return
    try:
        if isinstance(object1,dict):
            for key in object1.keys():
                print("- ", key)
            print("what section you want?")
            section = input()
            recur(object1[section])
        elif isinstance(object1,list):
            print("- ", " list  ")
            lenn = len(object1)
            print("you have ", lenn, "sections in the list, which you want?")
            i = int(input())
            recur(object1[i])

        else:
            print('answer:')
            if not object1:
                print("the answer is empty")
            else:
                print(object1)
    except Exception:
        print("try one mpre time")
        recur(object1)


def read_file():
    """
    the function received the file name, which should be read
    after opening the file it calls the recursive function
    to move through the file, chosen by the user

    user has the option to end the program pressing "n"
    """
    path_to_file = input("what file do you want to explore?")
    with open(path_to_file, encoding='utf-8') as file:
        data = json.load(file)
    while True:
        print("to start press \"y\", to go out press \"n\": ")
        text = input(">>> ")
        if text == "y":
            recur(data)
        elif text == "n":
            print("ok, do pobachennia")
            return
read_file()
