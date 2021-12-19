gundam_robot Panama

+++++++++++++++++++++++
Configurar el ambiente de trabajao

	abrir una terminal

crear una carpeta para el ambiente de trabajo

	$ mkdir -p catkin_ws/src
	$ cd  catkin_ws
	$ wstool init src
	$ wstool update -t src
	$ source /opt/ros/$ROS_DISTRO/setup.bash
	$ rosdep install -y -r --from-paths src --ignore-src
	$ catkin build
	$ source devel/setup.bash
	
++++++++++++++++++++++++++
dentro de la carpeta src descomprimir el archivo gundam_panama.zip

desde la terminal compilar 
	$ catkin_make
	$ source devel/setup.bash
	
	
++++++++++++++++++++++++++
Cargar el mundo Gundam

Correr el Roscore para cargar el ambiente

	$ roscore

+++++++++++++++++++++++
abrir una nueva terminal para cargar el mundo gundam_panama
	
	$ cd catkin_ws
	$ source devel/setup.bash
	$ roslaunch gundam_rx78_gazebo gundam_rx78_walk_panama.launch	
	
+++++++++++++++++++++++
abrir una terminal para cargar el movimiento hacia adelante, atras, derecha, izquierda
	
	$ cd catkin_ws
	$ source devel/setup.bash
	$ rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find gundam_rx78_control`/sample/csv/walk-forward.csv
	$ rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find gundam_rx78_control`/sample/csv/walk-forward.csv
	$ rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find gundam_rx78_control`/sample/csv/walk-backward.csv
	$ rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find gundam_rx78_control`/sample/csv/walk-to-right.csv
	$ rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find gundam_rx78_control`/sample/csv/walk-to-left.csv



+++++++++++++++++++++++++++
Para visualizar el modelo Gundam URDF

	$ roslaunch gundam_rx78_description display.launch


