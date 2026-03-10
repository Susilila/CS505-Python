# calculators 

import math

command =0 

while(command !=4):
    print("1. Cartesian Distance\n")
    print("2. Vector X matrix\n")
    print("3. Normalize\n")
    print("4. Quit\n")
    command = int(input("Entering your command:  \n"))

    if command ==1:
        value = input("Entering x1 y1 x2 y2: \n").split()

        if len(value)!=4:    #checking user input
            print("Please entering 4 numbers: \n")
            continue

        x1=float(value[0])
        y1=float(value[1])
        x2=float(value[2])
        y2=float(value[3])
        
        # calculating cartesian distance 
        cartesian = math.sqrt((x2-x1)**2 + (y2-y1)**2)
        print("Cartesian Distance: ", cartesian, "\n")
    
    elif command ==2: 
        values =input("Entering vector 1 2 3 and followed by 9 row-major: \n").split()
        if len(values) !=12:                       # check user input
            print("please entering the right number of arguments:  \n")
            continue

        v1= float(values[0])
        v2= float(values[1])
        v3= float(values[2])
        m11=float(values[3])
        m12=float(values[4])
        m13=float(values[5])
        m21=float(values[6])
        m22=float(values[7])
        m23=float(values[8])
        m31=float(values[9])     
        m32=float(values[10])
        m33=float(values[11])
         
        vector = [v1, v2, v3]
        matrix = [
            [m11, m12, m13],
            [m21, m22, m23],
            [m31, m32, m33]
        ]
        # calculating the vector-matrix multiplication 
        result = []
        for row in matrix:
            total=0 
            for i in range(3):
               total += row[i]*vector[i]
            result.append(total)
    
        print("Vector * Matrix calculation results: ",  end= " ")
        for i in result:
            print(i, end=" ")
        print("\n")   

    elif command ==3:
        value =input("entering three value vector: \n").split()

        if len(value)!=3:                              # checking user input
           print("Please enter three value vector:  \n")
           continue 

        for i in range(len(value)):
            value[i] = float(value[i])

        total=0                 # sum all elements square value 
        for i in range(len(value)):
            total += value[i]**2

        length = math.sqrt(total)
        if length==0:                   # check the denominator 
            print("Length can not be zero! \n")
            continue 
        
        nv=[0,0,0]                        # normalize every element 
        for i in range(3):
            nv[i] = value[i] /length
            print(nv[i], end= " ")

        print()

    elif command==4:
        print("Quit! Thank you!")
