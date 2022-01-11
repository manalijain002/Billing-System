# Billing-System
from tkinter import *
from tkinter import ttk
import random
import tkinter.messagebox
from datetime import datetime
import time




class Customer:

    def __init__(self,root):
        self.root=root
        self.root.title("Customer Billing system")
        self.root.geometry("1350x750+0+0")
        self.root.config(background="powder blue")

        ABC=Frame(self.root, bg="purple",bd=20,relief=RIDGE)
        ABC.grid()
        ABC1=Frame(ABC,bd=14,width=1350,height=100,padx=10, bg="powder blue",relief=RIDGE)
        ABC1.grid(row=0,column=0, columnspan=4,sticky=W)
        
        ABC2=Frame(ABC,bd=14,width=450,height=488,padx=10, bg="cadet blue",relief=RIDGE)
        ABC2.grid(row=1,column=0,sticky=W)
        
        ABC3=Frame(ABC,bd=14,width=450,height=488,padx=10, bg="powder blue",relief=RIDGE)
        ABC3.grid(row=1,column=1,sticky=W)
        
        ABC4=Frame(ABC,bd=14,width=460,height=488,padx=10, bg="cadet blue",relief=RIDGE)
        ABC4.grid(row=1,column=2,sticky=W)
        
        ABC5=Frame(ABC4,bd=14,width=370,height=340,padx=10, bg="cadet blue",relief=RIDGE)
        ABC5.grid(row=0,column=0,sticky=W)
        
        ABC6=Frame(ABC4,bd=14,width=370,height=120,padx=10, bg="cadet blue",relief=RIDGE)
        ABC6.grid(row=1,column=0,columnspan=4,sticky=W)

        Date1=StringVar()
        Time1=StringVar()

        Date1.set(time.strftime("%d/%m/%y"))
        Time1.set(time.strftime("%H/%M/%S"))

        self.lblTitle=Label(ABC1,textvariable=Date1,font=('Arial',30,'bold'),pady=9,bd=5,bg='cadet blue',fg="Cornsilk").grid(row=0,column=0)
  
        self.lblTitle=Label(ABC1,text="                       Customer Billing system             \t",font=('Arial',30,'bold'),
                            pady=9,bd=5,bg='cadet blue',fg="Cornsilk").grid(row=0,column=1)

        self.lblTitle=Label(ABC1,textvariable=Time1,font=('Arial',30,'bold'),pady=9,bd=5,bg='cadet blue',fg="Cornsilk").grid(row=0,column=2)

        #======================================================================================================================================================

        def iExit():
            iExit=tkinter.messagebox.askyesno("Customer Billing System","Confirm if you want to exit")
            if iExit>0:
                root.destroy()
                return
        #====================================================================================================================================================
        def Reset():
            self.txtReceipt.delete('1.0',END)
            E_Chips.set("0")
            E_PopCorn.set("0")
            E_American.set("0")
            E_Coldyy.set("0")
            var1.set(0)
            var2.set(0)
            var3.set(0)
            var4.set(0)

        #=========================================================================================================================================================
        CustomerRef=StringVar()
        Firstname=StringVar()
        Surname=StringVar()
        Address=StringVar()
        PostCode=StringVar()
        Mobile=StringVar()
        Email=StringVar()
        Nationality=StringVar()
        DOB=StringVar()
        IDtype=StringVar()
        Gender=StringVar()
        Check_In_Date=StringVar()
        Check_Out_Date=StringVar()
        Meal=StringVar()
        Roomtype=StringVar()
        RoomNO=StringVar()
        RoomExitNo=StringVar()
        SubTotal=StringVar()
        PaidTax=StringVar()
        TotalCost=StringVar()
        



        CustomerRef.set(random.randint(19800,9875648))

        
       ## CustomerRef=StringVar()
        var1=IntVar()
        var2=IntVar()
        var3=IntVar()
        var4=IntVar()
        var5=IntVar()
        var6=IntVar()
        var7=IntVar()
        var8=IntVar()
        var9=IntVar()
        var10=IntVar()
        var11=IntVar()
        var12=IntVar()
        var13=IntVar()
        var14=IntVar()
        var15=IntVar()
        var16=IntVar()


        E_Chips=StringVar()
        E_PopCorn=StringVar()
        E_PlateTime=StringVar()
        E_Coldyy=StringVar()

        E_Chips.set("0")
        E_PopCorn.set("0")
        E_PlateTime.set("0")
        E_Coldyy.set("0")

        #===============================================================================================================================

        def ChkChips():
            if(var1.get()==1):
                self.txtChips.configure(state=NORMAL)
                self.txtChips.focus()
                self.txtChips.delete('0',END)
                E_Chips.set("")
            elif var1.get()==0:
                self.txtChips.configure(state=DISABLED)
                E_Chips.set("0")


        def ChkPopCorn():
            if(var2.get()==1):
                self.txtPopCorn.configure(state=NORMAL)
                self.txtPopCorn.focus()
                self.txtPopCorn.delete('0',END)
                E_PopCorn.set("")
            elif var2.get()==0:
                self.txtPopCorn.configure(state=DISABLED)
                E_PopCorn.set("0")

                
        def ChkPlateTime():
            if(var3.get()==1):
                self.txtPlateTime.configure(state=NORMAL)
                self.txtPlateTime.focus()
                self.txtPlateTime.delete('0',END)
                E_PlateTime.set("")
            elif var3.get()==0:
                self.txtPlateTime.configure(state=DISABLED)
                E_PlateTime.set("0")        
            
                 
        def ChkColdyy():
            if(var4.get()==1):
                self.txtColdyy.configure(state=NORMAL)
                self.txtColdyy.focus()
                self.txtColdyy.delete('0',END)
                E_Coldyy.set("")
            elif var4.get()==0:
                self.txtColdyy.configure(state=DISABLED)
                E_Coldyy.set("0")

        #===============================================================================================================

        def costofItem():
            
            CustomerRef.set(random.randint(19800,9875648))
            Item1=float(E_Chips.get())
            Item2=float(E_PopCorn.get())
            Item3=float(E_PlateTime.get())
            Item4=float(E_Coldyy.get())




            PriceofDrinks=(Item1*20)+(Item2*30)\
                           +(Item3*200)+(Item4*80)


            SubTotalofITEMS="RS",str('%.2f'%PriceofDrinks)
            SubTotal.set(SubTotalofITEMS)
            Tax="RS",str('%.2f'%((PriceofDrinks)*0.15))
            PaidTax.set(Tax)
            TTax=((PriceofDrinks)*0.15)
            TCost="RS",str('%.2f'%(PriceofDrinks+TTax))
            TotalCost.set(TCost)


            self.txtReceipt.insert(END,'ITEMS\t\t\t\t'+"Costs of items \n")
            self.txtReceipt.insert(END,'CustomerRef:\t\t\t\t'+CustomerRef.get()+"\n")
            self.txtReceipt.insert(END,'Chips:\t\t\t\t\t'+E_Chips.get()+"\n")
            self.txtReceipt.insert(END,'PopCorn:\t\t\t\t\t'+E_PopCorn.get()+"\n")
            self.txtReceipt.insert(END,'PlateTime:\t\t\t\t\t'+E_PlateTime.get()+"\n")
            self.txtReceipt.insert(END,'Coldyy:\t\t\t\t\t'+E_Coldyy.get()+"\n")


            self.txtReceipt.insert(END,'\nPaid Tax:\t\t\t\t'+PaidTax.get()+"\n")
            self.txtReceipt.insert(END,'\nSubTotal:\t\t\t\t'+str(SubTotal.get())+"\n")
            self.txtReceipt.insert(END,'\nTotalCost:\t\t\t\t'+str(TotalCost.get())+"\n")
            


        #====================================================================================================================================        
        ##0
        self.lblCus_Ref=Label(ABC2,font=('arial',12,'bold'),text="Custumer Ref:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblCus_Ref.grid(row=0,column=0,sticky=W)

        self.txtCus_Ref=Entry(ABC2,font=('arial',12,'bold'),textvariable=CustomerRef,width=20)
        self.txtCus_Ref.grid(row=0,column=1,pady=3,padx=20)

        ##1
        self.lblFirstname=Label(ABC2,font=('arial',12,'bold'),text=" Firstname:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblFirstname.grid(row=1,column=0,sticky=W)

        self.txtFirstname=Entry(ABC2,font=('arial',12,'bold'),textvariable=Firstname,width=20)
        self.txtFirstname.grid(row=1,column=1,pady=3,padx=20)

        ##2
        self.lblSurname=Label(ABC2,font=('arial',12,'bold'),text="Surname:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblSurname.grid(row=2,column=0,sticky=W)

        self.txtSurname=Entry(ABC2,font=('arial',12,'bold'),textvariable= Surname,width=20)
        self.txtSurname.grid(row=2,column=1,pady=3,padx=20)

         ##3
        self.lblAddress=Label(ABC2,font=('arial',12,'bold'),text="Address :",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblAddress.grid(row=3,column=0,sticky=W)

        self.txtAddress=Entry(ABC2,font=('arial',12,'bold'),textvariable=Address ,width=20)
        self.txtAddress.grid(row=3,column=1,pady=3,padx=20)
          
        ##4
        self.lblEmail=Label(ABC2,font=('arial',12,'bold'),text="Email:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblEmail.grid(row=4,column=0,sticky=W)

        self.txtEmail=Entry(ABC2,font=('arial',12,'bold'),textvariable=Email,width=20)
        self.txtEmail.grid(row=4,column=1,pady=3,padx=20)

        ##5
        self.lblPCode=Label(ABC2,font=('arial',12,'bold'),text="PostCode:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblPCode.grid(row=5,column=0,sticky=W)

        self.txtPCode=Entry(ABC2,font=('arial',12,'bold'),textvariable=PostCode,width=20)
        self.txtPCode.grid(row=5,column=1,pady=3,padx=20)

        ##6
        self.lblMobile=Label(ABC2,font=('arial',12,'bold'),text="Mobile:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblMobile.grid(row=6,column=0,sticky=W)

        self.txtMobile=Entry(ABC2,font=('arial',12,'bold'),textvariable=Mobile,width=20)
        self.txtMobile.grid(row=6,column=1,pady=3,padx=20)


        ##7
        self.lblN=Label(ABC2,font=('arial',12,'bold'),text="Nationality:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblN.grid(row=7,column=0,sticky=W)
        self.cboN=ttk.Combobox(ABC2,textvariable=Nationality,state='readonly',font=('arial',12,'bold'),width=18)
        self.cboN['value']=('','British','Nigeria','kenya','India','Iran','Canada','Norway','American')
        self.cboN.current(0)
        self.cboN.grid(row=7,column=1,pady=3,padx=20)

       # self.txtN=Entry(ABC2,font=('arial',12,'bold'),textvariable=Nationality,width=20)
        #self.txtN.grid(row=7,column=1,pady=3,padx=20)

        ##8
        self.lblCus_Ref=Label(ABC2,font=('arial',12,'bold'),text="Date of birth:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblCus_Ref.grid(row=8,column=0,sticky=W)

        self.txtCus_Ref=Entry(ABC2,font=('arial',12,'bold'),textvariable=DOB,width=20)
        self.txtCus_Ref.grid(row=8,column=1,pady=3,padx=20)

        ##9
        self.lblIDtype=Label(ABC2,font=('arial',12,'bold'),text="Type of ID:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblIDtype.grid(row=9,column=0,sticky=W)
        self.cboIDtype=ttk.Combobox(ABC2,textvariable=IDtype,state='readonly',font=('arial',12,'bold'),width=18)
        self.cboIDtype['value']=('','Pilot Licence','Passport','Adhar Card','Student ID')
        self.cboIDtype.current(0)
        self.cboIDtype.grid(row=9,column=1,pady=3,padx=20)

        #self.txtCus_Ref=Entry(ABC2,font=('arial',12,'bold'),textvariable= IDtype,width=20)
        #self.txtCus_Ref.grid(row=9,column=1,pady=3,padx=20)

         ##10
        self.lblGender=Label(ABC2,font=('arial',12,'bold'),text="Gender:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblGender.grid(row=10,column=0,sticky=W)
        self.cboGender=ttk.Combobox(ABC2,textvariable=Gender,state='readonly',font=('arial',12,'bold'),width=18)
        self.cboGender['value']=('','Male','Female')
        self.cboGender.current(0)
        self.cboGender.grid(row=10,column=1,pady=3,padx=20)

       # self.txtGender=Entry(ABC2,font=('arial',12,'bold'),textvariable=Gender,width=20)
        #self.txtGender.grid(row=10,column=1,pady=3,padx=20)
          
        ##11
        self.lblCheck_In_Date=Label(ABC2,font=('arial',12,'bold'),text="Check In Date:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblCheck_In_Date.grid(row=11,column=0,sticky=W)

        self.txtCheck_In_Date=Entry(ABC2,font=('arial',12,'bold'),textvariable=Date1,width=20)
        self.txtCheck_In_Date.grid(row=11,column=1,pady=3,padx=20)

        ##12
        self.lblCheck_Out_Date=Label(ABC2,font=('arial',12,'bold'),text="Check Out Date:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblCheck_Out_Date.grid(row=12,column=0,sticky=W)

        self.txtCheck_Out_Date=Entry(ABC2,font=('arial',12,'bold'),textvariable=Date1,width=20)
        self.txtCheck_Out_Date.grid(row=12,column=1,pady=3,padx=20)

        ##13
        self.lblMeal=Label(ABC2,font=('arial',12,'bold'),text="Meal:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblMeal.grid(row=13,column=0,sticky=W)
        self.cboMeal=ttk.Combobox(ABC2,textvariable=Meal,state='readonly',font=('arial',12,'bold'),width=18)
        self.cboMeal['value']=('','Breakfast','Lunch','Dinner')
        self.cboMeal.current(0)
        self.cboMeal.grid(row=13,column=1,pady=3,padx=20)


       # self.txtMeal=Entry(ABC2,font=('arial',12,'bold'),textvariable=Meal,width=20)
       # self.txtMeal.grid(row=13,column=1,pady=3,padx=20)

        ##14
        self.lblRoomtype=Label(ABC2,font=('arial',12,'bold'),text=" Roomtype:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblRoomtype.grid(row=14,column=0,sticky=W)
        self.cboRoomtype=ttk.Combobox(ABC2,textvariable=Roomtype,state='readonly',font=('arial',12,'bold'),width=18)
        self.cboRoomtype['value']=('','Single','Double','Family')
        self.cboRoomtype.current(0)
        self.cboRoomtype.grid(row=14,column=1,pady=3,padx=20)

        #self.txtRoomtype=Entry(ABC2,font=('arial',12,'bold'),textvariable= Roomtype,width=20)
        #self.txtRoomtype.grid(row=14,column=1,pady=3,padx=20)

        ##15
        self.lblRoomNO=Label(ABC2,font=('arial',12,'bold'),text="RoomNO:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblRoomNO.grid(row=15,column=0,sticky=W)

        self.txtRoomNO=Entry(ABC2,font=('arial',12,'bold'),textvariable= RoomNO,width=20)
        self.txtRoomNO.grid(row=15,column=1,pady=3,padx=20)

        ##16
        self.lblRoomExitNo=Label(ABC2,font=('arial',12,'bold'),text="RoomExitNo:",padx=2,fg="Cornsilk",bg="Cadet Blue")
        self.lblRoomExitNo.grid(row=16,column=0,sticky=W)

        self.txtRoomExitNo=Entry(ABC2,font=('arial',12,'bold'),textvariable= RoomExitNo,width=20)
        self.txtRoomExitNo.grid(row=16,column=1,pady=3,padx=20)

         ##17
        self.lblTotalCost=Label(ABC3,font=('arial',12,'bold'),text="TotalCost:",bd=7,bg="powder blue",fg="black")
        self.lblTotalCost.grid(row=12,column=0,sticky=W)

        self.txtTotalCost=Entry(ABC3,font=('arial',12,'bold'),textvariable=TotalCost,bd=7,bg="white" ,width=20)
        self.txtTotalCost.grid(row=12,column=1)
          
   #     ##18
        self.lblSubTotal=Label(ABC3,font=('arial',12,'bold'),text="SubTotal:",bd=7,fg="black",bg="powder blue")
        self.lblSubTotal.grid(row=11,column=0,sticky=W)

        self.txtSubTotal=Entry(ABC3,font=('arial',12,'bold'),textvariable=SubTotal,bd=7,bg="white",width=20,justify=LEFT)
        self.txtSubTotal.grid(row=11,column=1)

        ##19
        self.lblPaidTax=Label(ABC3,font=('arial',12,'bold'),text="PaidTax:",bd=7,fg="black",bg="powder blue")
        self.lblPaidTax.grid(row=10,column=0,sticky=W)
        self.txtPaidTax=Entry(ABC3,font=('arial',12,'bold'),textvariable=PaidTax,bd=7,bg="white",width=20,justify=LEFT)
        self.txtPaidTax.grid(row=10,column=1,pady=3,padx=20)

       


        #=============================================================================================

        self.Chips=Checkbutton(ABC3,text="Chips",variable=var1,onvalue=1,offvalue=0,font=('arial',12,'bold'),bg="powder blue",command=ChkChips).grid(row=0,sticky=W)
        self.txtChips=Entry(ABC3,font=('arial',12,'bold'),textvariable=E_Chips,bd=8,width=20,justify='left',state=DISABLED)
        self.txtChips.grid(row=0,column=1)

        self.PopCorn=Checkbutton(ABC3,text="PopCorn",variable=var2,onvalue=1,offvalue=0,font=('arial',12,'bold'),bg="powder blue",command=ChkPopCorn).grid(row=1,sticky=W)
        self.txtPopCorn=Entry(ABC3,font=('arial',12,'bold'),textvariable=E_PopCorn,bd=8,width=20,justify='left',state=DISABLED)
        self.txtPopCorn.grid(row=1,column=1)


        self.PlateTime=Checkbutton(ABC3,text="PlateTime",variable=var3,onvalue=1,offvalue=0,font=('arial',12,'bold'),bg="powder blue",command=ChkPlateTime).grid(row=2,sticky=W)
        self.txtPlateTime=Entry(ABC3,font=('arial',12,'bold'),textvariable=E_PlateTime,bd=8,width=20,justify='left',state=DISABLED)
        self.txtPlateTime.grid(row=2,column=1)

        self.Coldyy=Checkbutton(ABC3,text="Coldyy",variable=var4,onvalue=1,offvalue=0,font=('arial',12,'bold'),bg="powder blue",command=ChkColdyy).grid(row=3,sticky=W)
        self.txtColdyy=Entry(ABC3,font=('arial',12,'bold'),textvariable=E_Coldyy,bd=8,width=20,justify='left',state=DISABLED)
        self.txtColdyy.grid(row=3,column=1)




        self.lblspace=Label(ABC3,text="Tax and Total Sum",font=('arial',12,'bold'),pady=1,bd=9,bg="cadet Blue",
                            fg="Cornsilk",width=26,justify=CENTER).grid(row=8,column=0,columnspan=4)









        #=========================================================================================================================================================
        self.txtReceipt=Text(ABC5,height=19,width=43,bd=10,font=('arial',9,'bold'))
        self.txtReceipt.grid(row=0,column=0)
        ########################################################################################################################################################
        self.btnTotal=Button(ABC6,padx=14,pady=7,bd=5,fg="black",font=('arial',16,'bold'),width=5,height=2,
                             bg="powder blue",text="Total",command=costofItem).grid(row=0,column=0)

        self.btnReset=Button(ABC6,padx=14,pady=7,bd=5,fg="black",font=('arial',16,'bold'),width=5,height=2,
                             bg="powder blue",text="Reset",command=Reset).grid(row=0,column=1)

        self.btnExit=Button(ABC6,padx=14,pady=7,bd=5,fg="black",font=('arial',16,'bold'),width=5,height=2,
                            bg="powder blue",text="Exit",command=iExit).grid(row=0,column=2)
        ########################################################################################################################################################





        
        








if __name__=='__main__':
    root=Tk()
    application= Customer(root)
    root.mainloop()
    


