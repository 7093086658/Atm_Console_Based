accounts= {4321:[5000,1152,"lavanyakaicharla@gmail.com","kaicharla_lavanya"],
          1234:[2000,1955,"dileeppollipalli@gmail.com","dileep_pollipalli"],
          1001:[3000,None,"anjanitulasi@gmail.com","anjani_tulasi"],
          2001:[5400,None,"lavanyakaicharla11@gmail.com","AAshrith raj"]}
print(accounts)
while True:
    print("************************")
    print("Choose a option")
    print("1 = WITHDRAW")
    print("2 = DIPOSITE")
    print("3 = PIN GENARATION")
    print("4 = MINI STATEMENT")
    print("5 = pinchange")
    print("6 = EXIT")
    x=int(input("select a option: "))
    if x == 1:
        acc=int(input("enter a account number: "))
        if acc not in accounts:
            print("IN VALID ACCOUNT NUMBER")
        else:
            if accounts[acc][1] is  None:
                print(f"{accounts[acc][-1]} pin is not generated")
            else:
                pin=int(input("enter a pin: "))
                if accounts[acc][1] == pin:
                    amt=int(input("enter a ammount: "))
                    if accounts[acc][0] >= amt:
                        accounts[acc][0] -= amt
                        print(accounts[acc][0])
                        print("WITHDRAW SUCCESSFULL")
                    else:
                        print("IN SUFFICIENT AMOUNT")
                else:
                    print("IN VALID PIN")   
    if x == 2:
        acc=int(input("enter a account number: "))
        if acc not in accounts:
            print("IN VALID ACCOUNT NUMBER")
        else:
            amt=int(input("enter a ammount: "))
            accounts[acc][0] += amt
            print(accounts[acc][0])
            print("DEPOSITE SUCESSFULL")
    if x == 3:
        acc=int(input("enter a account number: "))
        if acc not in accounts:
            print("IN VALID ACCOUNT NUMBER")
        else:
            if accounts[acc][1] is not None:
                print(f"{accounts[acc][-1]} pin is already generated")
            else:
                pin= input("enter a pin: ")
                length=len(pin)
                if length == 4:
                    accounts[acc][1] = pin
                    pin = int(accounts[acc][1])
                    accounts[acc][1] = pin
                    print("PIN GENERATED SUCESSFULL")    
                else:
                    print("enter a four digit number") 
    if x == 4:
        acc=int(input("enter a account number: "))
        if acc not in accounts:
            print("IN VALID ACCOUNT NUMBER")
        else:
            pin=int(input("enter a pin"))
            if accounts[acc][1] == pin:
                print(f"name = {accounts[acc][-1]}")
                print(f"gmail = {accounts[acc][-2]}")
                print(f"balance = {accounts[acc][0]}")
            else:
                print("IN VALID PIN")
    if x == 5:
        acc=int(input("enter a account number: "))
        if acc not in accounts:
            print("IN VALID ACCOUNT NUMBER")
        else:
            if accounts[acc][1] is not None:
               pin=int(input("enter a new pin: "))
               accounts[acc][1]=pin
               print("PIN CHANGE SUCESSFULL")
            else:
               print("you are not generated a pin")
                
    if x == 6:
        print("********************")
        print("**THANK YOU**")
        print("**VISIT AGAIN**")
        print("*******************")
        break
        
    
