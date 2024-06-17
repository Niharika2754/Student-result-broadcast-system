# Student-result-broadcast-system
using python 
#printing the results table

def printsd(sd):

  print("stuid ","stuname ","sub ","marks ","grade ","Date ","sub ","marks ","grade ","Date ")

  print()

  for i in sd:

    print(i,end=" ")

    for j in sd[i]:

      print(j,end=" ")

    print()

#dic (database) with student results details

sd={101:["Ajay","maths",50,'C',"5-6-2024","science",89,'A',"6-6-2024"],

102:["Vijy","maths",70,'B',"5-6-2024","science",99,'O',"6-6-2024"],

103:["Sanj","maths",70,'B',"5-6-2024","science",50,'C',"6-6-2024"],

104:["Niki","maths",99,'O',"5-6-2024","science",75,'B',"6-6-2024"],

105:["uday","maths",70,'B',"5-6-2024","science",30,'F',"6-6-2024"]

}

printsd(sd)

#dic (database) user table

a={1:["admin1",1,"admin"],

2:["admin2",2,"admin"],

101:["Ajay",101,"student"],

102:["Vijy",102,"student"],

103:["Sanj",103,"student"],

104:["Niki",104,"student"],

105:["uday",105,"student"]

}

#fa=flag

fa=0

#dic d for student {id:pd}

d={}

#initailizing id and pd

for i in range(100,111):

    d[i]=i

#input for login as admin or user

u=int(input("Login as:1. Admin 2.Student: "))

if u==1:

  aid=int(input("enter admin id:"))

  if aid in a:

    apd=int(input("enter password:"))

    l=a[aid]

    #authentication of admin

    if l[1]==apd:

      fa=1

    else:

      print("Not authorized admin")

  if fa==1:

    print("Admin authenticated")

    y=input("Do u want to do any modifications..?")

    if y=='Yes':

      for i in range(5):

        print("which operation do u want to perfom:")

        x=int(input("1.Add student result 2.update student result 3.read student result 4.delete student result 5.exit : "))

        #admin operations

        if x==1: #adding new student details

          print("enter student details : ")

          a=int(input())

          b=input()

          c=input()

          d=int(input())

          e=input()

          f=input()

          l=[b,c,d,e,f]

          if a not in sd:

            sd[a]=l

          else:

            print("Already")

          printsd(sd)

        elif x==2:#update student details

          p=int(input("enterb the student id : "))

          sub=input("enter subject: ")

          mark=int(input("enter student new marks: "))

          if p in sd:

            if sub=="maths":

              l=sd[p]

              l[2]=mark

              if mark>90:

                l[3]="O"

              elif mark<=90 and mark>70:

                l[3]="A"

              elif mark<=70 and mark>50:

                l[3]="B"

              else:

                l[3]="F"

              sd[p]=l

              printsd(sd)

            else:

              l=sd[p]

              l[6]=mark

              if mark>90:

                l[7]="O"

              elif mark<=90 and mark>70:

                l[7]="A"

              elif mark<=70 and mark>50:

                l[7]="B"

              else:

                l[7]="F"

              sd[p]=l

              printsd(sd)

          else:

            print("student not found ")

        elif x==3: #read student details

          view=int(input("enter student id: "))

          if(view in sd):

            l=sd[view]

            print(l[1],":",l[2],",",l[3],",",l[4],"\n",l[5],":",l[6],",",l[7],",",l[8])

          else:

            print("student not found")

        elif x==4: #delete student details

          view=int(input("enter student id: "))

          if(view in sd):

            del sd[view]

            printsd(sd)

          else:

            print("student not found")

        elif x==5: #exit

          break

        else:

          print("\n invalid operation type")

    else:

      print("Invalid details")

else:

  #student operations

  for i in range(4):

    print("enter the operation: 1.login 2.results 3.Download 4.break")

    z=int(input())

    if z==1:

      sid=int(input("enter user id:"))

      f=0

      #print(d)

      if sid in d:

        spd=int(input("enter password:"))

        if spd==d[sid]:

          f=1

      if f==1:

        print("User authenticated")

      else:

        print("Invalid details")

    elif z==2:

      num=int(input("\n enter the id: "))

      if num in sd:

        l=sd[num]

        print(l[1],":",l[2],",",l[3],",",l[4],"\n",l[5],":",l[6],",",l[7],",",l[8])

      else:

        print("student not found")

    elif z==3:

      print("Download pdf")

    else:

      break







