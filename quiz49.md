class unaryencoder:
    def __init__(self, userbinary):
        self.userbinary = str(userbinary)

    # This function will convert the users binary into unary
    def encode(self):
        current = 0
        output = "00 0" if self.userbinary[0] == "0" else "0 0"
        # This for loop will continue until the length of the input has reached its limit
        for i in range(1, len(self.userbinary)):
            if self.userbinary[i] == self.userbinary[current]:
                output += "0"
            else:
                output += " 00 0" if self.userbinary[i] == "0" else " 0 0"
                current = i
        return output

print(unaryencoder(1000011).encode())
print(unaryencoder(1111011).encode())
