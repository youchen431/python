from tkinter import *
import tkinter.messagebox
import math
class JSQ:
    def __init__(self):
        self.root = tkinter.Tk()
        self.root.minsize(270, 330)
        self.root.maxsize(270, 330)
        self.root.title('简单科学计算器')
        self.result = tkinter.StringVar()
        self.result.set(0)
        self.lists = []
        self.isPressSign = False
        self.islistsclear = False
        self.isbaifenhao = False
        self.num1 = ''
        self.result3 = None
        self.num = ''
        self.sign1 = ''
        self.layout()
        self.menubar()
        self.root.mainloop()
    def menubar(self):
        allmenu = tkinter.Menu(self.root)
        filemenu = tkinter.Menu(allmenu, tearoff=0)
        filemenu.add_command(label='退出', command=self.root.quit)
        allmenu.add_cascade(label='查看(V)', menu=filemenu)
        editmenu = tkinter.Menu(allmenu, tearoff=0)
        editmenu.add_separator()
        editmenunei = tkinter.Menu(editmenu, tearoff=0)
        self.root.config(menu=allmenu)
    def layout(self):
        label = tkinter.Label(self.root, textvariable=self.result, bg='white', font=('黑体', 20), anchor='e')
        label.place(x=20, y=10, width=230, height=60)
        btnjiantou = tkinter.Button(self.root, text='←', command=lambda: self.jiantou())
        btnjiantou.place(x=20, y=90, width=30, height=30)
        btnce = tkinter.Button(self.root, text='CE', command=lambda: self.CE())
        btnce.place(x=70, y=90, width=30, height=30)
        btnc = tkinter.Button(self.root, text='C', command=lambda: self.clears())
        btnc.place(x=120, y=90, width=30, height=30)
        btnzhengfu = tkinter.Button(self.root, text='±', command=lambda: self.zhenffu())
        btnzhengfu.place(x=170, y=90, width=30, height=30)
        btnkaigen = tkinter.Button(self.root, text='√', command=lambda: self.sqrts())
        btnkaigen.place(x=220, y=90, width=30, height=30)
        btn7 = tkinter.Button(self.root, text='7', command=lambda: self.pressNum('7'))
        btn7.place(x=20, y=130, width=30, height=30)
        btn8 = tkinter.Button(self.root, text='8', command=lambda: self.pressNum('8'))
        btn8.place(x=70, y=130, width=30, height=30)
        btn9 = tkinter.Button(self.root, text='9', command=lambda: self.pressNum('9'))
        btn9.place(x=120, y=130, width=30, height=30)
        btnchu = tkinter.Button(self.root, text='/', command=lambda: self.pressCompute('/'))
        btnchu.place(x=170, y=130, width=30, height=30)
        btnbaifen = tkinter.Button(self.root, text='%', command=lambda: self.baifenhao())
        btnbaifen.place(x=220, y=130, width=30, height=30)
        btn4 = tkinter.Button(self.root, text='4', command=lambda: self.pressNum('4'))
        btn4.place(x=20, y=170, width=30, height=30)
        btn5 = tkinter.Button(self.root, text='5', command=lambda: self.pressNum('5'))
        btn5.place(x=70, y=170, width=30, height=30)
        btn6 = tkinter.Button(self.root, text='6', command=lambda: self.pressNum('6'))
        btn6.place(x=120, y=170, width=30, height=30)
        btncheng = tkinter.Button(self.root, text='*', command=lambda: self.pressCompute('*'))
        btncheng.place(x=170, y=170, width=30, height=30)
        btnfenshu = tkinter.Button(self.root, text='1/X', command=lambda: self.fenshu())
        btnfenshu.place(x=220, y=170, width=30, height=30)
        btn1 = tkinter.Button(self.root, text='1', command=lambda: self.pressNum('1'))
        btn1.place(x=20, y=210, width=30, height=30)
        btn2 = tkinter.Button(self.root, text='2', command=lambda: self.pressNum('2'))
        btn2.place(x=70, y=210, width=30, height=30)
        btn3 = tkinter.Button(self.root, text='3', command=lambda: self.pressNum('3'))
        btn3.place(x=120, y=210, width=30, height=30)
        btnjian = tkinter.Button(self.root, text='-', command=lambda: self.pressCompute('-'))
        btnjian.place(x=170, y=210, width=30, height=30)
        btndenghao = tkinter.Button(self.root, text='=', command=lambda: self.pressEqual())
        btndenghao.place(x=220, y=210, width=30, height=70)
        btn0 = tkinter.Button(self.root, text='0', command=lambda: self.pressNum('0'))
        btn0.place(x=20, y=250, width=80, height=30)
        btndian = tkinter.Button(self.root, text='.', command=lambda: self.pressNum('.'))
        btndian.place(x=120, y=250, width=30, height=30)
        btnjia = tkinter.Button(self.root, text='+', command=lambda: self.pressCompute('+'))
        btnjia.place(x=170, y=250, width=30, height=30)
    def pressNum(self, num):
        self.num1 = num
        if self.isPressSign == False:
            pass
        else:
            self.result.set(0)
            self.isPressSign = False
        if self.islistsclear == False:
            oldNum = self.result.get()
            if oldNum == '0':
                self.result.set(num)
            else:
                newNum = oldNum + num
                self.result.set(newNum)
        else:
            self.result.set('0')
            self.islistsclear = False
            self.result.set(num)
    def pressCompute(self, sign):
        if True:
            self.num = self.result.get()
            self.lists.append(self.num)
            self.lists.append(sign)
            self.sign1 = sign
            self.isPressSign = True
        if self.lists[0] == '0':
            if self.lists[1] == '-':
                self.result.set('-')
                self.isPressSign = False
    def pressEqual(self):
        curnum = self.result.get()
        self.lists.append(curnum)
        computeStr = ''.join(self.lists)
        endNum = eval(computeStr)
        self.result.set(endNum)
        if self.isbaifenhao == True:
            self.result.set(self.result3)
        self.lists.clear()
        self.islistsclear = True
    def clears(self):
        self.lists.clear()
        self.result.set('0')
    def CE(self):
        self.result.set('0')
    def zhenffu(self):
        self.result1 = self.result.get()
        self.result.set(float(self.result1) * (-1))
        self.islistsclear = True
    def sqrts(self):
        result1 = self.result.get()
        self.result.set(math.sqrt(float(result1)))
        self.lists.clear()
        self.islistsclear = True
    def fenshu(self):
        result1 = self.result.get()
        self.result.set(1 / float(result1))
        self.islistsclear = True
    def baifenhao(self):
        listss = []
        if len(self.lists) < 1:
            self.result.set(0)
        else:
            a1 = float(self.num)
            a2 = self.sign1
            a3 = float(self.num)
            a4 = '*'
            a6 = float(self.num1) / 100
            resultmuqian = a3 * a6
            resultbai = str(a1) + a2 + str(a3) + a4 + str(a6)
            self.result3 = eval(resultbai)
            self.result.set(resultmuqian)
            self.isbaifenhao = True
    def jiantou(self):
        result1 = self.result.get()
        result1 = list(result1)
        del result1[-1]
        result1 = str(result1)
        self.result.set(result1)
    def func2(self):
        tkinter.messagebox.askokcancel(title='略过', message='没实现')
myjsq = JSQ()
