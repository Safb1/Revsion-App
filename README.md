# Revsion-App
A-Level Project Using Python:


import sqlite3 
                                   #Program Construction#
questions = ["Is it true that the market factors and demographic factors infuluence the external environemnt of a business?",
                            "True or Fasle? Changes in the size of a country's population will only effect local businesses by the level of demand for the products they produce",
                            "What two factors don't have an effect the level of demand reguardless of the level of consumer income?",
                            "Give one concequence of high interest rates",
                            "What is a stakeholder?",
                            "Is the following statement true or false? In the past, managers tended to operate largely in the interest their stakeholders",
                            "Can a business have more than one supplier?",
                            "What is measured on the axis of the stakeholder map?",
                            "What is measured on the Boston Matrix?",
                            "On the Product Lifecycle, the third stage is known as...",
                            "An attempt to prolong the decline of sales is known as a contingency stratgey",
                            "Why does outsourcing narrow the company's control over their supplies?",
                            "Holding inventory gives a business competitive advantage",
                            "What is the time taken for supplies to arrive from the time of them being ordered is known as?",
                            "What factors makes a businesses relationship with their suppliers strong?",
                            "Is the following statement true or false? Drawing up detailed cash flow forecasts eliminates all risks of cashflow problems",
                            "Is the following statment true or false? An increase in price will always increase a business's profit",
                            "Debt factoring is... and can allow a business to have improved cashflow",
                            "In Maslows hierarchy of needs what comes first?",
                            "Union representatives negotiating on behalf of many employees can save time and reduce the likelihood of disputes. True or false?",
                            "Name examples of a non-current assest and an example of a current liability",
                            "UK government's policies to protect the natural environment might effect the activities such as the production of a businesses",
                            "Inflation is the rate of decrease of the general price level and the corresponding rise in the value of money",
                            "Porter's five forces include; competitive rivalry, threat of buyer power, threat of new entrant, threat of substitues, threat of supplier power",
                            "What does the Ansoffs Matrix measure?",
                            "What does Porters differentiation strategy focuses on?",
                            "On Bowman's strategic clock, what is a hybrid product labeled as?", 
                            "Diseconomies of scale occurs when the total costs rise with less output. True or false",
                            "Does being innovative allow a business to gain market share and have market growth",
                            "Economies of scale occurs when unit costs fall as a business expands; these economies relate to the volumes of output",
                            "Removing levels of hierarchy in an organisation is known as...",
                            "Critical path shows how long an acticity can overrun without holding up the whole project?",
                            "What are Handy's types of culture?"]


answer_choices = ["a)True\nb)False\n:",
                   "a)True\nb)False\n:",
                   "a)cigarettes\nb)cars\nc)clothing\nd)petrol\n:",
                   "a)people save more\nb)people borrow more\nc)people spend more\n:",
                   "a)someone who holds shares in a business\nb)someone who takes an interest in a business\nc)someone who makes decisions in a business\n:",
                   "a)True\nb)False\n:",
                   "a)Yes\nb)No\n:",
                   "a)market share\nb)power\nc)market growth\nd)level of interest\n:",
                   "a)prodct development\nb)cash cow\nc)market growth\n:",
                   "a)growth\nb)saturation\nc)maturity\n:",
                   "a)True\nb)False\n:",
                   "a)because they are not in control of production\nb)they have passed on this responsibility to someone else\n:",
                   "a)True\nb)False\n:",
                   "a)buffer stock\nb)lead time\nc)re-order level\nd)days\n:",
                   "a)good payback\nb)regular orders\n:",
                   "a)True\nb)False\n:",
                   "a)False\nb)True\n:",
                   "a)collecting debt from people and no\nb)collecting debt from people and yes\nc)selling your debt to someone else to get quick source of income and no\nd)selling your debt to someone else to get quick source of income and yes\n:",
                   "a)physchologiclal needs\nb)physiological needs\nc)security\nd)self esteem\n:",
                   "a)False\nb)True\n:",
                   "a)property\nb)debt\nc)petrol\n:",
                   "a)True\nb)False\n:",
                   "a)False\nb)True\n:",
                   "a)Yes\nb)No\n:",
                   "a)percieved value of product\nb)price\nc)time\nd)product and market\n:",
                   "a)competitive rivalry\nb)cost leadership\nc)highly differentiated products\nd)threat of substitute\n:",
                   "a)high percieved value and high price\nb)low percieved value and low price\nc)high percieved value and low price\nd)low percieved value and high price\n:",
                   "a)True\nb)False\n:",
                   "a)No\nb)Yes\n:",
                   "a)True\nb)False\n:",
                   "a)delayering\nb)fiering managers\nc)flatter orgranisational structure\n:",
                   "a)True\nb)False\n:",
                   "a)power\nb)role\nc)task\nd)person\n:",
                   ":"]

correct_choices = [{"a", "True"},
                  {"a", "True"},
                  {"a", "cigarettes", "and", "d", "petrol"},
                  {"a", "people save more"},
                  {"b", "someone who takes an interest in a business"},
                  {"a", "True"},
                  {"a", "Yes"},
                  {"b", "power","and", "d", "level of interest"},
                  {"c", "market growth"},
                  {"c", "maturity"},
                  {"b", "False"},
                  {"a", "because they are not in control of production"},
                  {"b","False"},
                  {"b", "lead time"},
                  {"a", "good payback", "and", "b", "regular orders"},
                  {"b", "False"},
                  {"a", "False"},
                  {"d", "selling your debt to someone else to get quick source of income and yes"},
                  {"b","physiological needs"},
                  {"b", "True"},
                  {"a", "property","and", "b", "debt"},
                  {"a", "True"},
                  {"a", "False"},
                  {"a", "Yes"},
                  {"d","product and market"},
                  {"b", "cost leadership","and", "c", "highly differentiated products"},
                  {"c","high percieved value and low price"},
                  {"b","False"},
                  {"b","Yes"},
                  {"a", "True"},
                  {"a", "delayering"},
                  {"b","False"},
                  {"a", "power","and", "b", "role","and", "c", "task","and", "d", "person"}]



correct_answers = ["Is it true that the market factors and demographic factors infuluence the external environemnt of a business? It is True",
                   "True or Fasle? Changes in the size of a country's population will only effect local businesses by the level of demand for the products they produce. It is True",
                   "What two factors don't have an effect the level of demand reguardless of the level of consumer income? cigarretes and petrol",
                   "Give one concequence of high interest rates. Answer: people save more",
                   "What is a stakeholder? A stakeholder is someone who takes an interest in a business",
                   "Is the following statement true or false? In the past, managers tended to operate largely in the interest their stakeholders. This is True",
                   "Can a business have more than one supplier? Answer: Yes",
                   "What is measured on the axis of the stakeholder map? Answer: power AND level of interest",
                   "What is measured on the Boston Matrix? Answer: market growth",
                   "On the Product Lifecycle, the third stage is known as maturity",
                   "An attempt to prolong the decline of sales is known as a contingency stratgey. This is False",
                   "Why does outsourcing narrow the company's control over their supplies? Becsuse they are not in control of production",
                   "Holding inventory gives a business competitive advantage. This is False",
                   "What factors makes a businesses relationship with their suppliers strong. Answer: good payback AND regular orders",
                   "What is the time taken for supplies to arrive from the time of them being ordered is known as? lead time",
                   "What factors makes a businesses relationship with their suppliers strong? Answer: good payback AND regular orders ",
                   "Is the following statement true or false? Drawing up detailed cash flow forecasts eliminates all risks of cashflow problems. This is False",
                   "Is the following statment true or false? An increase in price will always increase a business's profit. This is False",
                   "Debt factoring is SELLING YOUR DEBT TO SOMEONE ELSE TO GET QUICK SOURCE OF INCOME and (YES)can allow a business to have improved cashflow",
                   "In Maslows hierarchy of needs what comes first? Answer: physiological needs",
                   "Union representatives negotiating on behalf of many employees can save time and reduce the likelihood of disputes. True",
                   "Name examples of a non-current assest and an example of a current liability. Answer: property AND debt",
                   "UK government's policies to protect the natural environment might effect the activities such as the production of a businesses. True",
                   "Inflation is the rate of decrease of the general price level and the corresponding rise in the value of money. False",
                   "Porter's five forces include; competitive rivalry, threat of buyer power, threat of new entrant, threat of substitues, threat of supplier power. Yes",
                   "What does the Ansoffs Matrix measure? product AND market",
                   "What does Porters differentiation strategy focuses on? cost leadership AND highly differentiated products",
                   "On Bowman's strategic clock, what is a hybrid product labeled as? high percived value and low price",
                   "Diseconomies of scale occurs when the total costs rise with less output. False",
                   "Does being innovative allow a business to gain market share and have market growth. Yes",
                   "Economies of scale occurs when unit costs fall as a business expands; these economies relate to the volumes of output. True",
                   "Removing levels of hierarchy in an organisation is known as delayering",
                   "Critical path shows how long an acticity can overrun without holding up the whole project? False",
                   "What are Handy's types of culture? ALL of the answers below are correct - power, role, task, person"]


def quiz(): 
    score = 0 
    for question, answer, right_choice, right_answers in zip(questions, answer_choices, correct_choices, correct_answers):
        print(question)
        UserAnswer = input(answer).lower()
        if UserAnswer in right_choice: 
            print("Well done, you are correct!")
            score += 1 
        else:
            print("Incorrect!", right_answers)
    print(score, "out of", len(questions), "that is", float(score/len(questions))*100, "%")
    return score 


                                            #User SignUp/LogIn Section#
def SignUp(): 
    print("Hello! Welcome to your A-Level Business Revision Application. \n") 
    print("To begin with please create and sign up to create your own personal profile to track your progress.\n")
    print("Please complete these simple steps")
    db = sqlite3.connect('database.db')
    cursor = db.cursor()
    cursor.execute('''CREATE TABLE IF NOT EXISTS userinformation(username TEXT, password TEXT)''')
    db.commit()
    username = input("Username:")
    password = input("Password:")
    cursor.execute('''INSERT INTO userinformation(username, password) VALUES (?,?)''',(username, password))
    print("Saved")
    db.commit()
    cursor.execute('''SELECT username, password FROM userinformation''')
    userinfo = cursor.fetchone()
    #print(username, password) #FOR TESTING PURPOSES
    while True: 
        if username == userinfo: 
            print("SUCCESS!")
        elif password == userinfo:
            print("SUCCESS!") 
            WelcomeMessage()
        else: 
            print("ACCESS DENIED!")
            break 
        cursor.close 
        db.close 

def WelcomeMessage(): 
    username1 = input("Name: ") 
    print("++++++++++++++++++++++++++++++++++++++")
    print("!Welcome to your revision application!")
    print("++++++++++++++++++++++++++++++++++++++")
    print()
    print("Hello {}, welcome to your A-Level Business Studies revison application. \n".format(username1)) 
    print("We hope to make revision more exciting for you by allowing you to take part in a quick quiz to help you boost your knowledge. \n")
    MainMenu()
    
def MainMenu(): 
    print("=========")
    print("MAIN MENU")
    print("=========")
    print()
    print("1. Quiz yourself") 
    print("2. View your progress")
    print("3. Quit") 
    print("\n")
    Choice = int(input("Please enter your choice: "))
    while True: 
        if Choice == int("1"): 
            quiz() 
        elif Choice == int("2"):
            score = quiz() 
        elif Choice == int("3"): 
            break 
        else: 
            print("This is not a choice, please try again.")

                                  #Main Programme Call#   
if __name__ == "__main__":
    SignUp()
    
