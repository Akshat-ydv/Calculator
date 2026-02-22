# Calculator
cal = input("Kya calculate karna hai: ")


issme = []
num = ""

for ch in cal:
    if ch.isdigit():
        num += ch
    else:
        if num != "":
            issme.append(num)
            num = ""
        issme.append(ch)

if num != "":
    issme.append(num)


# Division
i = 0
while i < len(issme):
    if issme[i] == '/':
        a = float(issme[i-1]) / float(issme[i+1])
        issme[i-1:i+2] = [str(a)]
        i = 0
    else:
        i += 1

# Multiplication
i = 0
while i < len(issme):
    if issme[i] == '*':
        b = float(issme[i-1]) * float(issme[i+1])
        issme[i-1:i+2] = [str(b)]
        i = 0
    else:
        i += 1

# Addition
i = 0
while i < len(issme):
    if issme[i] == '+':
        c = float(issme[i-1]) + float(issme[i+1])
        issme[i-1:i+2] = [str(c)]
        i = 0
    else:
        i += 1

# Subtraction
i = 0
while i < len(issme):
    if issme[i] == '-':
        d = float(issme[i-1]) - float(issme[i+1])
        issme[i-1:i+2] = [str(d)]
        i = 0
    else:
        i += 1

print("Ye le kar dia calculate:", issme[0])
