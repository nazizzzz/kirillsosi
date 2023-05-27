
import tkinter as tk
import random
from tkinter.font import Font

import customtkinter as ctk
from PIL import Image, ImageTk


class MyFrame(ctk.CTkFrame):
    def __init__(self, master, **kwargs):
        super().__init__(master, **kwargs)





class App(ctk.CTk):
    def __init__(self):
        super().__init__()
        self.geometry("1280x720+320+180")
        self.resizable(False, False)
        self.grid_rowconfigure(0, weight=1)  # configure grid system
        self.grid_columnconfigure(0, weight=1)
        self.title('борщенкова саси')
        font = ctk.CTkFont(family='Century Gothic', size=25)

        self.sup_frame = MyFrame(master=self, width=400, height=700, corner_radius=0)
        self.sup_frame.grid(row=0, column=0, rowspan=4, sticky='nsew')

        self.supsup_frame = MyFrame(master=self, width=200, height=300)
        self.supsup_frame.grid(row=0, column=0, padx=20, pady=20)

        self.main_frame = MyFrame(master=self, width=1000, height=700, corner_radius=0)
        self.main_frame.grid(row=0, column=1, padx=20, pady=20)

        self.label = ctk.CTkLabel(self, text='Алгоритмы', font=font, bg_color='#2b2b2b')
        self.label.grid(row=0, column=0, sticky='n', pady=30)

        self.label1 = ctk.CTkLabel(self, text='RSA', font=font, bg_color='#2b2b2b')
        self.label1.grid(row=0, column=1, sticky='n', pady=30)

        def hui():
            for btn in self.supsup_frame:
                print(self.supsup_frame.cget())



        radio_var = tk.IntVar(value=0)
        self.radiobutton_1 = ctk.CTkButton(self.supsup_frame, text="RSA", font=font, height=50, width=190, fg_color='grey', text_color='white', corner_radius=5, command=hui)
        self.radiobutton_2 = ctk.CTkButton(self.supsup_frame, text="EGSA", font=font, height=50, width=190, fg_color='grey', text_color='white', corner_radius=5, command=hui)
        self.radiobutton_3 = ctk.CTkButton(self.supsup_frame, text="DSA", font=font, height=50, width=190, fg_color='grey', text_color='white', corner_radius=5, command=hui)
        self.radiobutton_4 = ctk.CTkButton(self.supsup_frame, text="ГОСТ 34.10-94", font=font, height=50, width=190, fg_color='grey', text_color='white', corner_radius=5, command=hui)
        self.radiobutton_1.grid(row=0, column=0, sticky='wens', pady=20)
        self.radiobutton_2.grid(row=1, column=0, sticky='wens', pady=20)
        self.radiobutton_3.grid(row=2, column=0, sticky='wens', pady=20)
        self.radiobutton_4.grid(row=3, column=0, sticky='wens', pady=20)
        # self.supsup_frame.destroy()

app = App()
app.mainloop()
