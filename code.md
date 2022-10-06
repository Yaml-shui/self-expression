```python
from tkinter import *
from tkinter import messagebox
import pygame
from turtle import *

# 初始化
pygame.init()
pygame.mixer.init()
pygame.mixer.music.load('七里香.mp3') # 加载歌曲
pygame.mixer.music.play() # 播放
pygame.event.get()

# 去掉窗口最大化最小化按钮，只保留关闭
def Attributes(a):
    a.attributes("-toolwindow", 2)

    #设置窗口大小并居中
    def size(ww,wh,window_name):
        # 设置窗口大小
        ww = ww
        wh = wh
        x = (sw - ww) / 2
        y = (sh - wh) / 2
        # 让窗口居中操作
        window_name.geometry("%dx%d+%d+%d" % (ww, wh, x, y))

        #定义'嗯对，收到了'按钮的提示
        def Receive():
            root.destroy()  #关掉上一个窗口
            receive = Tk()
            size(610,376,receive)
            receive.title('单选按钮')
            Attributes(receive)
            receive.protocol('WM_DELETE_WINDOW', close_receive) #禁止关闭，点击右上角关闭按钮会弹出警告
            lb = Label(receive)
            lb.pack()
            var = IntVar()
            s = "那我问你，你喜欢听周杰伦还是Taylor Swift"
            mysel = lb.config(text=s,font = ('微软雅黑',22),fg='OrangeRed')
            #添加两个选项
            rd1 = Radiobutton(receive, text="肯定是杰伦呀，华语乐坛还有谁能和他比",font = ('微软雅黑',20), variable=var, value=0, command=mysel) #closeallwindow(lb)
            rd1.pack()
            rd2 = Radiobutton(receive, text="都不是，我心中已经有人了",font = ('微软雅黑',20), variable=var, value=1, command=mysel)
            rd2.pack()
            btn = Button(receive, text='确定',font = ('微软雅黑',18), width=10, height=1,fg = "black",bg = 'NavajoWhite', relief=RAISED, command=App)
            btn.pack(side='bottom')  # 将按钮放在底部

            #定义’确定‘按钮提示
            def App():
                app = Tk()
                app.title('再来个单选')
                app.geometry('450x278+0+0')
                longtext = '''就知道你也喜欢杰伦 
    那我们就是朋友喽！！！'''
                said = Label(app, text=longtext, font=('微软雅黑', 27), fg='OrangeRed')
                said.pack()
                Attributes(app)
                app.protocol('WM_DELETE_WINDOW', close_app)#禁止关闭，点击右上角关闭按钮会弹出警告
                #定义两个按钮
                btn_1 = Button(app, text='哪里想跟你做朋友了',fg = "black",bg = 'NavajoWhite', width=15, height=2, relief=RAISED, command=Court)
                btn_1.pack(side = 'left')  # 将按钮放在左边
                btn_2 = Button(app, text='哈哈哈哈勉为其难', fg = "black",bg = 'NavajoWhite',width=15, height=2, relief=RAISED, command=Court)
                btn_2.pack(side='right')  # 将按钮放在右边

                #定义上面两个按钮提示
                def Court():
                    court = Tk()
                    court.title('这才是重点')
                    court.geometry('450x278+820+0')
                    longtext = '''啰嗦那么多，其实，我只是想说： 
        我喜欢你呀！！！'''
                    said = Label(court, text=longtext, font=('微软雅黑', 21), fg='OrangeRed')
                    said.pack()
                    Attributes(court)
                    court.protocol('WM_DELETE_WINDOW', close_Court)#禁止关闭，点击右上角关闭按钮会弹出警告
                    btn_1 = Button(court, text='我也稀饭你', width=10, height=1, font=('微软雅黑', 30),fg = "black",bg = 'NavajoWhite',relief=RAISED, command=love_heart)
                    btn_1.pack(side='bottom')  # 将按钮放在底部
                    # 不同意对的起我写了两天的代码！必须同意
                    btn_2 = Button(court, text='不喜欢', width=6, height=1, font=('微软雅黑',15),fg = "black",bg = 'NavajoWhite', relief=RAISED, command=not_Court)
                    btn_2.pack(side='bottom')  # 将按钮放在底部

                    #定义’我也稀饭你‘按钮提示,画图
                    def love_heart():
                        colormode(255)
                        pencolor((255, 69, 0))
                        fillcolor("pink")
                        setup(1920, 1080, 0, 0)
                        speed(5)
                        pensize(5)
                        left(180)
                        penup()
                        fd(330)
                        right(90)
                        fd(100)
                        pendown()
                        begin_fill()
                        circle(80, 180)
                        circle(220, 75)
                        left(31)
                        circle(220, 75)
                        circle(80, 180)
                        end_fill()
                        left(90)
                        penup()
                        fd(500)
                        left(90)
                        fd(50)
                        pendown()
                        begin_fill()
                        circle(120, 180)
                        circle(360, 70)
                        left(39)
                        circle(360, 70)
                        circle(120, 180)
                        end_fill()
                        penup()
                        goto(-570, 40)
                        right(90)
                        pendown()
                        fd(-1090)
                        seth(90)
                        fd(30)
                        fd(-60)
                        seth(30)
                        fd(60)
                        seth(150)
                        fd(60)
                        speed(1)
                        penup()
                        goto(-300,300)
                        for i in range(5):
                            circle(50)
                            speed(3)
                            goto(-300,-250)
                            pendown()
                            write('打开任务管理器关闭程序哦 doge',font = ("宋体", 30, "normal"))
                            done()

                            #定义’不喜欢‘的按钮提示
                            def not_Court():
                                court = Tk()
                                court.title('我写了两天的代码')
                                size(610,376, court)
                                said = Label(court, text='不喜欢不给你关，嘻嘻，doge', font=('微软雅黑', 31), fg='OrangeRed')
                                said.pack()
                                Attributes(court)
                                court.protocol('WM_DELETE_WINDOW', close_not_Court)#禁止关闭，点击右上角关闭按钮会弹出警告
                                btn_1 = Button(court, text='好叭', width=10, height=1, font=('微软雅黑', 50), fg="black", bg='NavajoWhite', relief=RAISED,
                                               command=court.destroy)
                                btn_1.pack(side='bottom')  # 将按钮放在底部



                                #定义关闭窗口提示
                                def close_root():
                                    messagebox.showinfo(title='警告',message='不许关闭')
                                    return

                                #定义关闭窗口提示
                                def close_receive():
                                    messagebox.showinfo(title='警告',message='答完题才能关闭')
                                    return

                                #定义关闭窗口提示
                                def close_app():
                                    messagebox.showinfo(title='警告',message='你关不了')
                                    return

                                #定义关闭窗口提示
                                def close_Court():
                                    messagebox.showinfo(title='警告',message='我说了不许关闭，滚回去选一个')
                                    return

                                #定义关闭窗口提示
                                def close_not_Court():
                                    messagebox.showinfo(title='警告',message='你气不气')
                                    return


                                #创建窗口
                                root = Tk()
                                root.title('偷偷告诉你')

                                # 得到屏幕宽度与高度
                                sw = root.winfo_screenwidth()
                                sh = root.winfo_screenheight()
                                size(610,376,root) #居中操作
                                label = Label(root,text = 'hey，打开这个文件就证明你收到喽！！！', font = ('微软雅黑',22), fg='OrangeRed')
                                Attributes(root)
                                label.pack()

                                #插入图片
                                photo = PhotoImage(file ='1(1).png')
                                imageLable = Label(root,image = photo)
                                imageLable.pack()

                                #禁止关闭，点击右上角关闭按钮会弹出警告
                                root.protocol('WM_DELETE_WINDOW',close_root)

                                #添加'嗯对，收到了'按钮并将按钮设置颜色
                                btn = Button(root, text = '嗯对，收到了',font = ('微软雅黑',16), width = 11,height = 5,fg = "black",bg = 'NavajoWhite',relief = RAISED,command = Receive)
                                btn.pack(side = 'bottom') #将按钮放在底部


                                root.mainloop()

```

