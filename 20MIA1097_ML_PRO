from tkinter import*
from PIL import Image, ImageTk
from tkinter import ttk
import pickle
import cv2
import numpy as np
import pandas as pd
from matplotlib import pyplot as plt
from sklearn.preprocessing import StandardScaler


from sklearn.svm import SVR
import datetime

filename = '/Users/utkarsharyan/Downloads/ML PRO PRO/finalized_model.sav'
regressor = pickle.load(open(filename, 'rb'))

test_date = datetime.datetime.strptime("2022-12-01", "%Y-%m-%d")

month1 = pd.date_range(test_date, periods=30)
month3 = pd.date_range(test_date, periods=90)
month6 = pd.date_range(test_date, periods=180)

month1 = pd.to_datetime(month1)
month3 = pd.to_datetime(month3)
month6 = pd.to_datetime(month6)

month1 = np.array(month1)
month3 = np.array(month3)
month6 = np.array(month6)

month1= month1.reshape(-1,1)
month3= month3.reshape(-1,1)
month6= month6.reshape(-1,1)

sc_X1 = StandardScaler()
month1 = sc_X1.fit_transform(month1)
sc_X3 = StandardScaler()
month3 = sc_X3.fit_transform(month3)
sc_X6 = StandardScaler()
month6 = sc_X6.fit_transform(month6)


s2 = 'month6'

def predictor():
    if(s2 == 'month1'):
        result1 = plt.plot(month1, regressor.predict(month1), color = 'green')
        plt.savefig('month1.png')
        image_read = cv2.imread('month1.png')
        resultx = image_read
        cv2.imshow("1 Month Prediction", resultx)
        cv2.waitKey(0)
        cv2.destroyAllWindows()
    elif(s2 == 'month3'):
        result3 = plt.plot(month3, regressor.predict(month3), color = 'green')
        plt.savefig('month3.png')
        image_read = cv2.imread('month3.png')
        resultx = image_read
        cv2.imshow("3 Month Prediction", resultx)
        cv2.waitKey(0)
        cv2.destroyAllWindows()
    else:
        result6 = plt.plot(month6, regressor.predict(month6), color = 'green')
        plt.savefig('month6.png')
        image_read = cv2.imread('month6.png')
        resultx = image_read
        cv2.imshow("6 Month Prediction", resultx)
        cv2.waitKey(0)
        cv2.destroyAllWindows()

root=Tk()
root.title("SVM Currency Rate Predictor")
root.geometry("1350x700+0+0")
root.config(bg="blue")
image=Image.open('/Users/utkarsharyan/Pictures/E-s42MaVgAAahX_.jpeg')
backgroundimage=ImageTk.PhotoImage(image)
imagelabel1=Label(root, image=backgroundimage).place(x=0, y=0, relwidth=1, relheight=1)
aboveimage=Image.open('/Users/utkarsharyan/Pictures/bq11j3vodmg71.png.webp')
abimage=ImageTk.PhotoImage(aboveimage)
imagelabel=Label(root, image=abimage).place(x=200, y=120, width=400, height=500)

formframe=Frame(root, bg="white")
formframe.place(x=600, y=120, width=700, height=500)

title=Label(formframe, text="Rate Prediction", font=("times new roman",20,"bold"),
            bg="white",fg="black").place(x=50,y=20)

C_name=Label(formframe, text="Currency 1", font=("times new roman",15,"bold"),
            bg="white",fg="grey").place(x=50,y=100)

entry_fname=Entry(formframe, font=("times new roman",15), bg="lightgray").place(x=50, y=130, width=250)

contact=Label(formframe, text="Currency 2", font=("times new roman",15,"bold"),
            bg="white",fg="grey").place(x=50,y=180)

entry_contact=Entry(formframe, font=("times new roman",15), bg="lightgray").place(x=50, y=210, width=250)

slot=Label(formframe, text="Timeperiod", font=("times new roman",15,"bold"),
            bg="white",fg="grey").place(x=50,y=260)

slot=ttk.Combobox(formframe, font=("Times new roman", 14), state="readonly", justify=CENTER)

slot['values']=("Select", "1 Month", "3 Month", "6 Month")
slot.place(x=50,y=290)
slot.current(0)

btn1=Button(formframe, text="Predict", bg="green", font=("Times new roman", 15), fg="black", cursor="hand2", command = predictor).place(x=50, y=430, width=150)
SIGNUP=Button(formframe, text="Cancel", bg="white", font=("Times new roman", 15), fg="black", cursor="hand2").place(x=300, y=430, width=150)
title_label=Label( text="20MIA1155 Utkarsh Aryan, 20MIA1097 Tanmay Tiwari, 20MIA1146 Abhineet Raj", background="White", foreground="Black",padx=340, pady=4, font="Verdana 10 bold", borderwidth=3, relief=SUNKEN)
title_label.pack(side=BOTTOM,fill="y")
f1=Label(root,text="Currency Rate Prediction Mechanism", font=("times new roman", 30,"bold"),fg="white", bg="blue", bd=0)
f1.pack(side=TOP, fill="x")
root.mainloop()

