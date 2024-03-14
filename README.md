<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></h1><a id="user-content-hdl_graph_slam" class="anchor" aria-label="永久链接：hdl_graph_slam" href="#hdl_graph_slam"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是一个开源 ROS 软件包，用于使用 3D LIDAR 进行实时 6DOF SLAM。</font><font style="vertical-align: inherit;">它基于 3D Graph SLAM，具有基于 NDT 扫描匹配的里程计估计和循环检测。</font><font style="vertical-align: inherit;">它还支持多种图形约束，例如 GPS、IMU 加速度（重力矢量）、IMU 方向（磁传感器）和地板平面（在点云中检测）。</font><font style="vertical-align: inherit;">我们已在室内和室外环境中使用 Velodyne（HDL32e、VLP16）和 RoboSense（16 通道）传感器测试了该套件。</font></font></p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://github.com/koide3/hdl_graph_slam/blob/master/imgs/hdl_graph_slam.png"><img src="https://github.com/koide3/hdl_graph_slam/raw/master/imgs/hdl_graph_slam.png" width="712pix" style="max-width: 100%;"></a></p>
<p dir="auto"><a href="https://github.com/koide3/hdl_graph_slam/actions/workflows/build.yml"><img src="https://github.com/koide3/hdl_graph_slam/actions/workflows/build.yml/badge.svg" alt="建造" style="max-width: 100%;"></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">关于旋律和思维</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">小节点</font></font></h2><a id="user-content-nodelets" class="anchor" aria-label="永久链接：Nodelet" href="#nodelets"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">由四个节点组成。</font></font></p>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预过滤节点</font></font></em></li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">scan_matching_odometry_nodelet</font></font></em></li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">楼层检测节点</font></font></em></li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam_nodelet</font></font></em></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">输入点云首先由</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">prefiltering_nodelet</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">进行下采样，然后传递到下一个 Nodelet。</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">scan_matching_odometry_nodelet</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通过</font><font style="vertical-align: inherit;">迭代应用连续帧之间的扫描匹配（即里程计估计）来估计传感器位姿，而</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Floor_detection_nodelet</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通过 RANSAC 检测地板平面。</font><font style="vertical-align: inherit;">估计的里程计和检测到的地板被发送到</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font><font style="vertical-align: inherit;">为了补偿扫描匹配的累积误差，它执行循环检测并优化考虑各种约束的位姿图。</font></font></p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://github.com/koide3/hdl_graph_slam/blob/master/imgs/nodelets.png"><img src="https://github.com/koide3/hdl_graph_slam/raw/master/imgs/nodelets.png" width="712pix" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">约束（边缘）</font></font></h2><a id="user-content-constraints-edges" class="anchor" aria-label="永久链接：约束（边缘）" href="#constraints-edges"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以通过更改启动文件中的参数来启用/禁用每个约束，还可以更改每个约束的权重（*_stddev）和鲁棒内核（*_robust_kernel）。</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">里程计</font></font></strong></em></p>
</li>
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">环闭合</font></font></strong></em></p>
</li>
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">全球定位系统</font></font></strong></em></p>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/gps/地理点</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(geographic_msgs/GeoPointStamped)</font></font></li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/gps/navsat</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> (sensor_msgs/NavSatFix)</font></font></li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/gpsimu_driver/nmea_sentence</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> (nmea_msgs/句子)</font></font></li>
</ul>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam 支持多种 GPS 消息类型。</font><font style="vertical-align: inherit;">所有支持的类型都包含（纬度、经度和海拔高度）。</font><font style="vertical-align: inherit;">hdl_graph_slam 将它们转换为</font></font><a href="http://wiki.ros.org/geodesy" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">UTM 坐标</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，并将它们作为 3D 位置约束添加到图中。</font><font style="vertical-align: inherit;">如果高度设置为 NaN，则 GPS 数据将被视为 2D 约束。</font><font style="vertical-align: inherit;">GeoPoint 是最基本的，仅由 (lat, lon, alt) 组成。</font><font style="vertical-align: inherit;">尽管 NavSatFix 提供了许多信息，但我们仅使用（lat、lon、alt）并忽略所有其他数据。</font><font style="vertical-align: inherit;">如果您使用 HDL32e，您可以</font><font style="vertical-align: inherit;">通过</font><em><font style="vertical-align: inherit;">/gpsimu_driver/nmea_sentence直接将</font></em></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">与</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">velodyne_driver</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">连接。</font></font><em><font style="vertical-align: inherit;"></font></em><font style="vertical-align: inherit;"></font></p>
<ul dir="auto">
<li><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">IMU加速度（重力矢量）</font></font></strong></em>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/gpsimu_driver/imu_data</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（传感器消息/Imu）</font></font></li>
</ul>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此约束旋转每个位姿节点，以便与该节点关联的加速度矢量变为垂直（作为重力矢量）。</font><font style="vertical-align: inherit;">这对于补偿扫描匹配的累积倾斜旋转误差很有用。</font><font style="vertical-align: inherit;">由于我们忽略了传感器运动产生的加速度，因此您不应为此约束赋予很大的权重。</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">IMU 方向（磁传感器）</font></font></strong></em></p>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/gpsimu_driver/imu_data</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（传感器消息/Imu）</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您的 IMU 具有可靠的磁性方向传感器，您可以将方向数据作为 3D 旋转约束添加到图表中。</font><font style="vertical-align: inherit;">请注意，磁定向传感器可能会受到外部磁干扰的影响。</font><font style="vertical-align: inherit;">在这种情况下，应禁用此约束。</font></font></p>
</li>
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">地板平面</font></font></strong></em></p>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/floor_detection/floor_coeffs</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> (hdl_graph_slam/FloorCoeffs)</font></font></li>
</ul>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该约束优化了图形，使得位姿节点的底平面（由 RANSAC 检测到）变得相同。</font><font style="vertical-align: inherit;">这是为了补偿大平面室内环境中扫描匹配的累积旋转误差而设计的。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参数</font></font></h2><a id="user-content-parameters" class="anchor" aria-label="永久链接：参数" href="#parameters"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">所有可配置参数均在launch/hdl_graph_slam.launch</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中作为 ros params</font><font style="vertical-align: inherit;">列出。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">服务</font></font></h2><a id="user-content-services" class="anchor" aria-label="永久链接：服务" href="#services"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/hdl_graph_slam/dump</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">   (hdl_graph_slam/DumpGraph)
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将所有内部数据（点云、楼层系数、odom 和位姿图）保存到一个目录中。</font></font></li>
</ul>
</li>
<li><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/hdl_graph_slam/save_map</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">   (hdl_graph_slam/SaveMap)
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将生成的地图保存为 PCD 文件。</font></font></li>
</ul>
</li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要求</font></font></h2><a id="user-content-requirements" class="anchor" aria-label="永久链接：要求" href="#requirements"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">需要以下库：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">开放MP</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">聚己内酯</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">葡萄糖</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">套件稀疏</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">需要以下 ROS 包：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">大地测量学</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">nmea_消息</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">pcl_ros</font></font></li>
<li><a href="https://github.com/koide3/ndt_omp"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ndt_omp</font></font></a></li>
<li><a href="https://github.com/SMRT-AIST/fast_gicp"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">快速_gicp</font></font></a></li>
</ul>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-c"><span class="pl-c">#</span> for melodic</span>
sudo apt-get install ros-melodic-geodesy ros-melodic-pcl-ros ros-melodic-nmea-msgs ros-melodic-libg2o
<span class="pl-c1">cd</span> catkin_ws/src
git clone https://github.com/koide3/ndt_omp.git -b melodic
git clone https://github.com/SMRT-AIST/fast_gicp.git --recursive
git clone https://github.com/koide3/hdl_graph_slam

<span class="pl-c1">cd</span> .. <span class="pl-k">&amp;&amp;</span> catkin_make -DCMAKE_BUILD_TYPE=Release

<span class="pl-c"><span class="pl-c">#</span> for noetic</span>
sudo apt-get install ros-noetic-geodesy ros-noetic-pcl-ros ros-noetic-nmea-msgs ros-noetic-libg2o

<span class="pl-c1">cd</span> catkin_ws/src
git clone https://github.com/koide3/ndt_omp.git
git clone https://github.com/SMRT-AIST/fast_gicp.git --recursive
git clone https://github.com/koide3/hdl_graph_slam

<span class="pl-c1">cd</span> .. <span class="pl-k">&amp;&amp;</span> catkin_make -DCMAKE_BUILD_TYPE=Release</pre><div class="zeroclipboard-container">
    
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[可选] </font></font></strong> <em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">bag_player.py</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">脚本需要 ProgressBar2。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>sudo pip install ProgressBar2</pre><div class="zeroclipboard-container">
   
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">示例1（室内）</font></font></h2><a id="user-content-example1-indoor" class="anchor" aria-label="永久链接：示例 1（室内）" href="#example1-indoor"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包档案（小房间内记录）：</font></font></p>
<ul dir="auto">
<li><a href="http://www.aisl.cs.tut.ac.jp/databases/hdl_graph_slam/hdl_501.bag.tar.gz" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_501.bag.tar.gz</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（原始数据，344MB）</font></font></li>
<li><a href="http://www.aisl.cs.tut.ac.jp/databases/hdl_graph_slam/hdl_501_filtered.bag.tar.gz" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_501_filtered.bag.tar.gz</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（下采样数据，57MB，</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">推荐！</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）</font></font></li>
<li><a href="https://zenodo.org/record/6960371" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">镜像链接</font></font></a></li>
</ul>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosparam <span class="pl-c1">set</span> use_sim_time <span class="pl-c1">true</span>
roslaunch hdl_graph_slam hdl_graph_slam_501.launch</pre><div class="zeroclipboard-container">
   
  </div></div>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>roscd hdl_graph_slam/rviz
rviz -d hdl_graph_slam.rviz</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="roscd hdl_graph_slam/rviz
rviz -d hdl_graph_slam.rviz" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosbag play --clock hdl_501_filtered.bag</pre><div class="zeroclipboard-container">
    
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们还提供 bag_player.py 来自动调整播放速度并尽可能快地处理数据。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosrun hdl_graph_slam bag_player.py hdl_501_filtered.bag</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="rosrun hdl_graph_slam bag_player.py hdl_501_filtered.bag" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">你会看到像这样的点云：</font></font></p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/top.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/top.png" height="256pix" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/birds.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/birds.png" height="256pix" style="max-width: 100%;"></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以通过以下方式保存生成的地图：</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosservice call /hdl_graph_slam/save_map <span class="pl-s"><span class="pl-pds">"</span>resolution: 0.05</span>
<span class="pl-s">destination: '/full_path_directory/map.pcd'<span class="pl-pds">"</span></span></pre><div class="zeroclipboard-container">
    
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">示例2（室外）</font></font></h2><a id="user-content-example2-outdoor" class="anchor" aria-label="永久链接：示例 2（室外）" href="#example2-outdoor"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包文件（室外环境录制）：</font></font></p>
<ul dir="auto">
<li><a href="http://www.aisl.cs.tut.ac.jp/databases/hdl_graph_slam/hdl_400.bag.tar.gz" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_400.bag.tar.gz</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（原始数据，约900MB）</font></font></li>
<li><a href="https://zenodo.org/record/6960371" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">镜像链接</font></font></a></li>
</ul>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosparam <span class="pl-c1">set</span> use_sim_time <span class="pl-c1">true</span>
roslaunch hdl_graph_slam hdl_graph_slam_400.launch</pre><div class="zeroclipboard-container">
    
  </div></div>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>roscd hdl_graph_slam/rviz
rviz -d hdl_graph_slam.rviz</pre><div class="zeroclipboard-container">
    
  </div></div>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>rosbag play --clock hdl_400.bag</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="rosbag play --clock hdl_400.bag" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://github.com/koide3/hdl_graph_slam/blob/master/imgs/hdl_400_points.png"><img src="https://github.com/koide3/hdl_graph_slam/raw/master/imgs/hdl_400_points.png" height="256pix" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer" href="https://github.com/koide3/hdl_graph_slam/blob/master/imgs/hdl_400_graph.png"><img src="https://github.com/koide3/hdl_graph_slam/raw/master/imgs/hdl_400_graph.png" height="256pix" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPS 示例</font></font></h2><a id="user-content-example-with-gps" class="anchor" aria-label="永久链接：GPS 示例" href="#example-with-gps"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">福特 Campus Vision 和激光雷达数据集</font></font><a href="http://robots.engin.umich.edu/SoftwareData/Ford" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[URL]</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下脚本将福特激光雷达数据集转换为 rosbag 并播放它。</font><font style="vertical-align: inherit;">在此示例中，</font></font><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">利用 GPS 数据来校正位姿图。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-c1">cd</span> IJRR-Dataset-2
rosrun hdl_graph_slam ford2bag.py dataset-2.bag
rosrun hdl_graph_slam bag_player.py dataset-2.bag</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="cd IJRR-Dataset-2
rosrun hdl_graph_slam ford2bag.py dataset-2.bag
rosrun hdl_graph_slam bag_player.py dataset-2.bag" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/ford1.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/ford1.png" height="200pix" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/ford2.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/ford2.png" height="200pix" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/ford3.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/ford3.png" height="200pix" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在您的系统中使用 hdl_graph_slam</font></font></h2><a id="user-content-use-hdl_graph_slam-in-your-system" class="anchor" aria-label="永久链接：在您的系统中使用 hdl_graph_slam" href="#use-hdl_graph_slam-in-your-system"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ol dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 static_transform_publisher 定义传感器（LIDAR、IMU、GPS）和系统的 base_link 之间的转换（请参见第 11 行，hdl_graph_slam.launch）。</font><font style="vertical-align: inherit;">所有传感器数据将被转换为公共的base_link帧，然后馈送到SLAM算法。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"></font><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重新映射prefiltering_nodelet</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的点云主题</font><font style="vertical-align: inherit;">。</font><font style="vertical-align: inherit;">喜欢：</font></font></p>
</li>
</ol>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>  <span class="pl-k">&lt;</span>node pkg=<span class="pl-s"><span class="pl-pds">"</span>nodelet<span class="pl-pds">"</span></span> type=<span class="pl-s"><span class="pl-pds">"</span>nodelet<span class="pl-pds">"</span></span> name=<span class="pl-s"><span class="pl-pds">"</span>prefiltering_nodelet<span class="pl-pds">"</span></span> ...
    <span class="pl-k">&lt;</span>remap from=<span class="pl-s"><span class="pl-pds">"</span>/velodyne_points<span class="pl-pds">"</span></span> to=<span class="pl-s"><span class="pl-pds">"</span>/rslidar_points<span class="pl-pds">"</span></span>/<span class="pl-k">&gt;</span>
  ...</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="  <node pkg=&quot;nodelet&quot; type=&quot;nodelet&quot; name=&quot;prefiltering_nodelet&quot; ...
    <remap from=&quot;/velodyne_points&quot; to=&quot;/rslidar_points&quot;/>
  ..." tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">常见问题</font></font></h2><a id="user-content-common-problems" class="anchor" aria-label="永久链接：常见问题" href="#common-problems"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参数调优指南</font></font></h3><a id="user-content-parameter-tuning-guide" class="anchor" aria-label="永久链接：参数调整指南" href="#parameter-tuning-guide"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">映射质量很大程度上取决于参数设置。</font><font style="vertical-align: inherit;">特别是扫描匹配参数对结果影响很大。</font><font style="vertical-align: inherit;">按照以下说明调整参数：</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Registration_method</font></font></strong></em>
<strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> [已更新] 简而言之，在大多数情况下使用 FAST_GICP，如果处理速度很重要，则使用 FAST_VGICP 或 NDT_OMP</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此参数允许更改用于里程计估计和循环检测的注册方法。</font><font style="vertical-align: inherit;">请注意，PCL1.7（ROS 动力学）或更早版本中的 GICP 在初始猜测处理中存在错误。</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您使用 ROS kinetic 或更早版本，请勿使用 GICP</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
</li>
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ndt_resolution</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
该参数决定NDT的体素大小。</font><font style="vertical-align: inherit;">通常，较大的值适合室外环境（室内为 0.5 - 2.0 [m]，室外为 2.0 - 10.0 [m]）。</font><font style="vertical-align: inherit;">如果您选择NDT或NDT_OMP，请调整此参数，以便获得良好的里程估算结果。</font></font></p>
</li>
<li>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">其他参数</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
所有可配置的参数都可以在启动文件中找到。</font><font style="vertical-align: inherit;">复制模板启动文件（hdl_graph_slam_501.launch 适用于室内，hdl_graph_slam_400.launch 适用于室外）并调整启动文件中的参数以使其适应您的应用程序。</font></font></p>
</li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执照</font></font></h2><a id="user-content-license" class="anchor" aria-label="永久链接：许可证" href="#license"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该软件包是根据 BSD-2-Clause 许可证发布的。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请注意，g2o 中的 cholmod 求解器已获得 GPL 许可。</font><font style="vertical-align: inherit;">您可能需要构建不依赖 cholmod 的 g2o 以避免 GPL。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">相关套餐</font></font></h2><a id="user-content-related-packages" class="anchor" aria-label="永久链接：相关包" href="#related-packages"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><a href="https://github.com/koide3/interactive_slam"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">互动猛击</font></font></a></li>
<li><a href="https://github.com/koide3/hdl_graph_slam"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_graph_slam</font></font></a></li>
<li><a href="https://github.com/koide3/hdl_localization"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">HDL_本地化</font></font></a></li>
<li><a href="https://github.com/koide3/hdl_people_tracking"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hdl_people_tracking</font></font></a></li>
</ul>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/koide3/hdl_graph_slam/blob/master/imgs/packages.png"><img src="/koide3/hdl_graph_slam/raw/master/imgs/packages.png" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文件</font></font></h2><a id="user-content-papers" class="anchor" aria-label="永久链接：论文" href="#papers"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Kenji Koide、Jun Miura 和 Emanuele Menegatti，用于长期和广域人员行为测量的基于便携式 3D LIDAR 的系统，先进机器人系统，2019 年</font></font><a href="https://www.researchgate.net/publication/331283709_A_Portable_3D_LIDAR-based_System_for_Long-term_and_Wide-area_People_Behavior_Measurement" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[链接]</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接触</font></font></h2><a id="user-content-contact" class="anchor" aria-label="永久链接：联系方式" href="#contact"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">小出健二，</font></font><a href="mailto:k.koide@aist.go.jp"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">k.koide@aist.go.jp</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，</font></font><a href="https://staff.aist.go.jp/k.koide" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://staff.aist.go.jp/k.koide</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">日本丰桥工业大学主动智能系统实验室</font></font><a href="http://www.aisl.cs.tut.ac.jp" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[URL]</font></font></a><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
日本产业技术综合研究所 (AIST) 移动机器人研究团队  </font></font><a href="https://unit.aist.go.jp/hcmrc/mr-rt/contact.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[URL]</font></font></a></p>
</article></div>
