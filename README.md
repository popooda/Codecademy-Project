# Codecademy-Project
U.S. Medical Insurance Costs

import csv
ins_costs = list()
smoke_status = list()
ages = list()
with open('insurance.csv', newline='') as csvfile:
    csvreader = csv.DictReader(csvfile)
    for row in csvreader:
        ins_costs.append(row["charges"])
        smoke_status.append(row["smoker"])
        ages.append(row["age"])
# print(ins_costs)
# print(smoke_status)
# print(ages)

def analyze():
    num_of_records = len(ins_costs)
    total_age = 0
    total_ins_cost = 0
    total_smokers = 0
    for ins_cost in ins_costs:
        total_ins_cost += float(ins_cost)
    for age in ages:
        total_age += int(age)
    for smoker in smoke_status:
        if smoker == "yes":
            total_smokers +=1
    average_ins_cost = total_ins_cost/num_of_records
    round_average_ins_cost = round(average_ins_cost,2)
    average_age = total_age/num_of_records
    round_average_age = round(average_age)
    percentage_smoker = total_smokers/num_of_records*100
    round_percentage_smoker = round(percentage_smoker,2)
    print(f"There are {num_of_records} records in insurance.csv.")
    print(f"The average insurance cost is $ {round_average_ins_cost}.")
    print(f"The average age is {round_average_age}.")
    print(f"{round_percentage_smoker} % of them are smokers.")
 
    
print(analyze())
