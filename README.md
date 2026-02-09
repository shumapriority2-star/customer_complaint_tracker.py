print("Customer Complaint and Resolution Tracker")

customers = []
issues = []
resolution_days = []

entries = int(input("Number of complaints received today: "))

for i in range(entries):
    print("\nComplaint", i + 1)
    customer = input("Customer name: ")
    issue = input("Issue type: ")
    days = int(input("Days taken to resolve: "))

    customers.append(customer)
    issues.append(issue)
    resolution_days.append(days)

total_complaints = len(resolution_days)
average_days = sum(resolution_days) / total_complaints if total_complaints > 0 else 0
fast_resolutions = sum(1 for d in resolution_days if d <= 2)
slow_resolutions = sum(1 for d in resolution_days if d > 2)

print("\nDaily Resolution Report")
print("Total complaints:", total_complaints)
print("Average resolution time:", round(average_days, 1), "days")
print("Fast resolutions (2 days or less):", fast_resolutions)
print("Slow resolutions (more than 2 days):", slow_resolutions)