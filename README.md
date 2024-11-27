[ROS_D455.txt](https://github.com/user-attachments/files/17933396/ROS_D455.txt)# D455
ubuntu18.04+D455 三维重建

必要的）ubuntu系统，我运用的是虚拟机安装ubuntu18.04，其次inteal深度相机D400系列，我用的Intel Realsense D455
1) 在Ubuntu上安装ROS1，这里推荐鱼香ROS一键安装

   Ubuntu终端运行下面指令，根据选项安装ros1
   
    wget http://fishros.com/install -O fishros && . fishros
   
2）安装后验证依次打开三个终端 分别输入以下命令

    roscore	
    
终端完成后 会显示 [/rosout]
   
    rosrun turtlesim turtlesim_node
   
会打开一个蓝色屏幕的小乌龟在中间
   
    rosrun turtlesim  turtle_teleop_key
   
鼠标要在第三个终端，可以通过按下键盘的 ↑ ↓ ← →键来对小海龟进行控制
   
安装成功，配置环境变量，打开终端，运行
  
    wget http://fishros.com/install -O fishros && . fishros
    
   选 4 一键配置
   
3）安装完ROS后，新建ROS工作空间，打开终端运行





  
cd ~/catkin_ws/src

查看数据

rtabmap -d ~/.ros/rtabmap.db

ROS_D455.txt…]()
