import pickle
import os
def addrecord():
    f=open("product.dat",'ab')
    choice='y'
    while choice=='y':
        pid=int(input("enter pro.id"))
        pname=input("enter pro.name")
        price=float(input("enter price"))
        l=[pid,pname,price]
        pickle.dump(l,f)
        choice=input("add[y/n]")
    f.close()
def display():
    try:
        f=open("product.dat",'rb')
        l=['']
        while l:
            l=pickle.load(f)
            print('pid:',l[0],'\n''pname:',l[1],'\n''price:',l[2],'\n''**************************************************************\n')
    except FileNotFoundError:
            print("file not exist!!!")
    except EOFError:
            f.close()
def copy():
    try:
        f=open("product.dat",'rb')
        f1=input("enter file name. In which you want to copy data.(with extension)")
        nf=open(f1,'wb')
        l=['']
        while l:
            l=pickle.load(f)
            pickle.dump(l,nf)
    except FileNotFoundError:
            print("file not exist!!!")
    except EOFError:
            print('copiesd')
            f.close()
            nf.close()
def update():
    try:
        f=open("product.dat",'rb+')
        l=['']
        B=True
        while B==True:
            pos=f.tell()
            l=pickle.load(f)
            u=int(input("enter pid to update product detail"))
            if l[0]==u:
                c=input("enter what do you want to update pid, pname, price")
                if c=='pid':
                    pid1=int(input("enter new pid"))
                    l[0]=pid1
                    f.seek(pos,0)
                    pickle.dump(l,f)
                elif c=='pname':
                    pname1=(input("enter new pname"))
                    l[1]=pname1
                    f.seek(pos,0)
                    pickle.dump(l,f)
                elif c=='price':
                    price1=float(input("enter new pid"))
                    l[2]=price1
                    f.seek(pos,0)
                    pickle.dump(l,f)
                else:
                    print("wrong chice!!!!")
                c=input("want to update more [y/n]")
                if c=='n':
                    break
                
    except FileNotFoundError:
            print("file not exist!!!")
    except EOFError:
        print('file updated')
        f,close
def delete():
    try:
        f=open("product.dat",'rb')
        nf=open("temp.dat",'wb')
        l=['']
        while l:
            l=pickle.load(f)
            u=int(input("enter pid to delete product details"))
            if l[0]!=u:
                pickle.dump(l,nf)
                c=input("want to delete more [y/n]")
            elif c=='n':
                pass
    except FileNotFoundError:
            print("file not exist!!!")
    except EOFError:
        print("record deleted")
        f.close()
        nf.close()
        os.remove("product.dat")
        os.rename("temp.dat","product.dat")
    

a=True
while a==True :
    fun=input("enter operation:\n1:Add\n2:Display\n3:Copy\n4:Updaste\n5:Delete\n6:Close File\n")
    if fun=='Add':
        addrecord()
    elif fun=='Display':
        display()
    elif fun=='Copy':
        copy()
    elif fun=='Update':
        update()
    elif fun=='Delete':
        delete()
    elif fun=='Close File':
        break
    else:
        print("No such operation exist")
