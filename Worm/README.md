贪吃蛇游戏
===========

这是贪吃蛇游戏的整个实现思路（具体算法实现见源代码）：
------------------------------

### 1、网格类Cell

    这个类定义了网格的一些基本属性，如：横坐标、纵坐标、大小等，还有用以绘图的paintCell方法。
    
### 2、贪吃蛇类Worm

    变量：（1）定义了控制贪吃蛇上下左右运动的变量。
          （2）贪吃蛇的默认长度、默认运动方向、当前长度和当前运动方向。
          （3）贪吃蛇的初始运动速度、贪吃蛇是否吃到食物。
    方法：（1）getInitSpeed()、getCurrentLength()、getCurrentDirection()函数分别获取贪吃蛇的最初
               速度、当前长度和当前运动方向。
          （2）contains(int x, int y)、changeDirection(int direction)方法功能分别是判断贪吃蛇是否
               某个节点（用于检测随机生成食物是否与贪吃蛇位置重叠和检测贪吃蛇是否会吃到自己）和改
               变贪吃蛇运动方向。
          （3）creep(int direction, Cell food)，爬行算法，控制贪吃蛇的爬行。
          （4）newHead(int currentDirection)，根据当前贪吃蛇运动方向生成头结点的算法。
          （5）hit(int direction)判断贪吃蛇是否发生撞击的算法，包括是否碰到墙壁和是否吃到自己两种
               情况。
          （6）用于绘图的paint方法。               

### 3、舞台类WormStage
    
    变量：（1）舞台的行数和列数。
          （2）食物对象和贪吃蛇对象。
          （3）判断贪吃蛇游戏是开始还是暂停的变量。
    方法：（1）interval()贪吃蛇每次吃掉一个食物便改变贪吃蛇的运动速度。
          （2）randomFood()随机生成食物对象。
          （3）用于绘图的paint方法。
    内部类：Move实现贪吃蛇自动爬行的线程。
            Event实现对贪吃蛇运动的事件控制。
          
### 4、主框架类WormFrame

    变量：（1）舞台类引用。
          （2）标签引用。
