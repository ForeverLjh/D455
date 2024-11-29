# D455
ubuntu18.04+D455 三维重建

必要的）ubuntu系统，我运用的是虚拟机安装ubuntu18.04，其次Intel深度相机D400系列，我用的Intel Realsense D455

具体实现步骤：

      （1）Ubuntu安装ROS，具体步骤看 [安装ROS]
   
       (2) 安装 Intel Realsense 的ROS包，具体步骤看 [安装Intel real sense camera的ROS包]
       
      （3）安装IMU ROS节点，打开终端，运行下列命令进入工作空间
      
            cd ~/catkin_ws/src
            
      运行命令，安装
      
            1.sudo apt-get install ros-melodic-imu-filter-madgwick
            
            2.sudo apt-get install ros-melodic-rtabmap-ros
            
            3.sudo apt-get install ros-melodic-robot-localization

      （4）打开三个终端，依次运行
      
            1.roslaunch realsense2_camera rs_camera.launch align_depth:=true unite_imu_method:="linear_interpolation" enable_gyro:=true enable_accel:=true
            
            2.rosrun imu_filter_madgwick imu_filter_node _use_mag:=false _publish_tf:=false _world_frame:="enu" /imu/data_raw:=/camera/imu /imu/data:=/rtabmap/imu
            
            3.roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete_db_on_start --Optimizer/GravitySigma 0.3" depth_topic:=/camera/aligned_depth_to_color/image_raw rgb_topic:=/camera/color/image_raw camera_info_topic:=/camera/color/camera_info approx_sync:=false wait_imu_to_init:=true imu_topic:=/rtabmap/imu



Michigan Technological University https://www.linkedin.com/posts/nathir-rawashdeh-b6019428_we-were-able-to-map-the-nucor-corporation-activity-7141588559219613696-ljjI
