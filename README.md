class Final:

    def menu(self):
        return """
1.moghayese adad ha
2.moadel balatar
3.histogram
4.mashin hesab
5.fibonacci
6.
7.tabdil horof koochak be bozorg
8.decoding & encoding
9.jenas ghalb
10.adad haye mosbat
-----------------"""

    def p1(self):
        x = input("enter x: ").lower()
        if x == "end":
            exit()
        y = input("enter y: ").lower()
        if "end" == y:
            exit()

        try:
            x = int(x)
            y = int(y)

            if x > 10:
                raise IOError("Freeze")

            print(x, y)
        except IOError as e:
            print(e)
            global error
            error = True

    def p2(self):
        
        num_scrs = input('enter the number of scores: ').lower()
        if "end" == num_scrs:
            exit()
        num_scrs = int(num_scrs)
        print()
        avg2 = avg1 = counter = 0
        while counter < num_scrs:
            counter += 1
            code = input('enter the %s student code : '%counter)
            if "end" == code:
                break
            code = int(code)
            avg0 = input("enter the %s avg : " %counter)
            if "end" == avg0:
                break
            avg0 = float(avg0)
            print()
            st_num = {counter : code}
            if avg0 > avg1 :
                avg2 = avg1
                avg1 = avg0
            elif avg0 > avg2 :
                avg2 = avg0
                st_code = code  
        print(avg2,st_code)
        

    def p3(self):
        
        list = [3, 7, 16, 8, 6]
        for index in list:
            if index=="end" or index=="End":
                exit()
            print(index, end='')
            while index > 0:
                print('+', end='')
                index -= 1
            else:
                print()
        

    def p4(self):
        num1 = input('enter an integer: ').lower()
        if num1=="end":
            exit()
        num1 = int(num1)

        operation = input('enter the operation(/,*,+,-)').lower()
        if operation=="end":
            exit()
        while True:
            if operation == '*' or operation == '/' or operation == '+' or operation == '-':
                break
            else:
                operation = input('incorrect operation, enter again (/,*,+,-) : ')
        num2 = input('enter an integer(secend number): ').lower()
        if num2=="end":
            exit()
        num2 = int(num2)
        if operation == '*':
            result = num1 * num2
            print('Result:',result)
        elif operation == '/':
            result = num1 / num2
            print('Result:',result)
        elif operation == '+':
            result = num1 + num2
            print('Result:',result)
        elif operation == '-':
            result = num1 - num2
            print('Result:',result)
        

    def p5(self):
        n = input("Enter your number: ").lower()
        if n=="end":
            exit()
        n = int(n)
        a=0
        b=1
        c=0
        print(a,b,end=" ")
        while c<n:
            c=a+b
            a=b
            b=c
            if c>=n:
                break
            print(c,end=" ")
            

    def p6(self):
        counter_a=0
        counter_o=0
        counter_e=0
        counter_i=0
        counter_u=0
        text = input("Enter your text: ").lower()
        if text =="end":
            exit()
        for i in text:
            if i=="a":
                counter_a+=1
            if i=="i":
                counter_i+=1
            if i=="e":
                counter_e+=1
            if i=="o":
                counter_o+=1
            if i=="u":
                counter_u+=1
        print(f"count of your vowel sounds is {counter_o + counter_a + counter_e + counter_i + counter_u}")

    def p7(self):
        
        enter = input('input: ').lower()
        if enter=="end":
            exit()
        for i in enter:
            if 122 >= ord(i) >= 97:
                print(chr((ord(i) - 32)),end = '')
            else:
                print(i,end = '')
        print()
        

    def p8(self):

        def Anonymous(name,flag):
            if name=="end" or flag=="end":
                exit()
            if flag == 'encode':
                for i in name:
                    print(ord(i), end = ' ')
            if flag == 'decode':
                name = name.split()
                for i in name:
                    print(int(chr(i)))

        Anonymous('amir','encode')
        

    def p9(self):

        def jenas_ghalb(t):
            for i in t:
                if i=="end":
                    exit()
                if i==i[::-1]:
                    print(i)
        jenas_ghalb(("lol","asfda","gol","dod","ghollogh"))
            

    
    def p10(self):
        t = (1,3,-4,5,-4,-5,-6,6.5,5,-22,31,4,-7,9,-21)
        if "end" in t:
            exit()
        f = lambda x: x>0
        for i in t:
            if i>0:
                print(i)

        


selector = "0"
error = False

f = Final()

while True:
    try:
        if not error:
            print(f.menu())
            selector = input("choose number of programs: ").lower()
            if selector == "end":
                exit()

        if selector == "1":
            error = False
            f.p1()
        elif selector == "2":
            error = False
            f.p2()
        elif selector == "3":
            error = False
            f.p3()
        elif selector == "4":
            error = False
            f.p4()
        elif selector == "5":
            error = False
            f.p5()
        elif selector == "6":
            error = False
            f.p6()
        elif selector == "7":
            error = False
            f.p7()
        elif selector == "8":
            error = False
            f.p8()
        elif selector == "9":
            error = False
            f.p9()
        elif selector == "10":
            error = False
            f.p10()

        # ...
    except Exception as e:
        print(e)
