//GTX 970 2(rig)x2(cards)+1(card)
SOL="280"
SOLMIN="270"
SOLMAX="300"
DOWN="230"
wget http://192.168.1.156:21285/getstat -O getstatw1
wget http://192.168.1.235:21285/getstat -O getstatw2
wget http://192.168.1.64:21285/getstat -O getstatw3
sed -e "s/ /\n/g" getstatw1 > gpu_infow1
sed -e "s/ /\n/g" getstatw2 > gpu_infow2
sed -e "s/ /\n/g" getstatw3 > gpu_infow3
clear
echo miner 1 \ \ \ \ \ \ \ \ \ \ \ 192.168.1.156
g0="`sed '17!d' gpu_infow1`"
echo -n GPU0:\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \  &&
GPU0="`echo ${g0//[^0-9]/} \ Sol`"
echo $GPU0

g1="`sed '30!d' gpu_infow1`"
echo -n GPU1:\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \  &&
GPU1="`echo ${g1//[^0-9]/} \ Sol`"
echo $GPU1

echo 

echo miner 2 \ \ \ \ \ \ \ \ \ \ \ 192.168.1.235
g2="`sed '17!d' gpu_infow2`"
echo -n GPU0:\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \  &&
GPU2="`echo ${g2//[^0-9]/} \ Sol`"
echo $GPU2

g3="`sed '30!d' gpu_infow2`"
echo -n GPU1:\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ &&
GPU3="`echo ${g3//[^0-9]/} \ Sol`"
echo $GPU3

echo 

echo miner 3 \ \ \ \ \ \ \ \ \ \ \ \ 192.168.1.64
g4="`sed '17!d' gpu_infow3`"
echo -n GPU0:\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \  &&
GPU4="`echo ${g4//[^0-9]/} \ Sol`"
echo $GPU4

if [ "$GPU0" -lt "$DOWN" ]
then
/usr/bin/nmap -v 192.168.1.156 -Pn -p 21285 | grep open || curl -s -X POST https://api.telegram.org/************:***********************************/sendMessage -d chat_id=********* -d text="Miner 1 Dosnt work"
fi

if [ "$GPU1" -lt "$DOWN" ]
then
/usr/bin/nmap -v 192.168.1.156 -Pn -p 21285 | grep open || curl -s -X POST https://api.telegram.org/************:***********************************/sendMessage -d chat_id=397996171 -d text="Miner 1 Dosnt work"
fi

if [ "$GPU2" -lt "$DOWN" ]
then
/usr/bin/nmap -v 192.168.1.156 -Pn -p 21285 | grep open || curl -s -X POST https://api.telegram.org/************:***********************************/sendMessage -d chat_id=397996171 -d text="Miner 2 Dosnt work"
fi

if [ "$GPU3" -lt "$DOWN" ]
then
/usr/bin/nmap -v 192.168.1.156 -Pn -p 21285 | grep open || curl -s -X POST https://api.telegram.org/************:***********************************/sendMessage -d chat_id=397996171 -d text="Miner 2 Dosnt work"
fi
