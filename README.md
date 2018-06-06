# EConTara_OrbSlam2_CheckerBoardDetector
  Repozytorium zawiera paczki do środowiska ROS Kinetic, pozwalające na uruchomienie kamery sterowizyjnej E-Con Tara. Dodatkowo zawiera pakiet zwracający informację o położeniu i orientacji planszy konfiguracyjnej w postaci x,y,z oraz kwaternionów. Rejestracja w przestrzeni trajektorii ruchu kamery odbywa się za pomocą pakietu ORB-SLAM2.
  
  
### Pakiety niezbędne do prawidłowego działania
  ROS:
  http://wiki.ros.org/ROS/Installation

  
  Pangolin:
  https://github.com/stevenlovegrove/Pangolin
  
  Eigen3:
  https://github.com/OPM/eigen3
  

  ```
  sudo apt-get install ros-kinetic-camera-info-manager
  sudo apt-get install libudev-dev
  sudo apt-get install libv4l-dev
  sudo apt-get install ros-kinetic-rqt-image-view
  ```


### Adresy repozytoriów, na podstawie których pracowano
  Deimos:
  https://github.com/i3drobotics/deimos-ros
  
  CheckerBoard Detector:
  https://github.com/jsk-ros-pkg/jsk_recognition
  
  ORB-SLAM2:
  https://github.com/raulmur/ORB_SLAM2
  
  
### Przygotowanie Workspace dla ROS
  ```
  mkdir ~/ROS_WS
  cd ~/ROS_WS
  git clone https://github.com/luki193/EConTara_OrbSlam2_CheckerBoardDetector.git
  catkin_make
  source devel/setup.bash
  ```
  
  W przypadku pojawienia się błędów z paczkami należy zainstalować niezbędne powiązania między pakietami ROS:
```
rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
```
  
  
### Instalacja ORB-SLAM2
  Instalacja ORB-SLAM2 może spowodować zawieszenie się komputera w przypadku niedostatecznej ilości pamięci RAM. W takim przypadku należy ponownie uruchomić komputer (format dowolny, preferowany hard reset) i ponowić ostatnią komendę.
  
  
  Przed zbudowaniem ORB-SLAM2 należy dodać ścieżkę dostępu do przykładów ORB-SLAM2 w pliku .bashrc.
  
  Otwarcie pliku .bashrc:
```
cd ..
gedit .bashrc
```
  Na końcu pliku .bashrc należy dodać poniższą linijkę:
```
export ROS_PACKAGE_PATH=${ROS_PACKAGE_PATH}:~/ORB_SLAM2/Examples/ROS
```

  Po wykonaniu powyższych czynności można zbudować ORB-SLAM2:
```
cd ORB_SLAM2
chmod +x build.sh
./build.sh
```

