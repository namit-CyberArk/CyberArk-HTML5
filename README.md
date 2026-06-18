# CyberArk-HTML5 PSM Docker installtion via script
Pre-Requisite
Downalod CyberArk HTML5 From Marketplace below link

"https://community.cyberark.com/marketplace/s/#software#---Name-Privileged%20Access%20Manager%20Self-Hosted"

Port Open From HTML5 Server to PVWA 443/80 and PSM Server 3389/443/445

Source	Destination	Protocol	Port	Purpose
PVWA	Gateway	TCP	9443	PVWA → Gateway for HTML5 session initiation
Gateway	PVWA	TCP	443	Gateway → PVWA for API calls (authentication, session details)
Gateway	PSM	TCP	443	Gateway → PSM for management/communication
Gateway	PSM	TCP	3389, 22, etc.	Gateway → PSM for actual RDP/SSH session traffic

Below Point need be Edit in Script
----------------------------------
CONTAINER_NAME="HTML5"      (Change Name)
NETWORK="cyberark"          (Don't Change)
HOST_PORT="9443"            (Change Port Number)
CONTAINER_PORT="8443"       (Don't Port Change)
CERT_HOST_DIR="/opt/cert"   (Don't Change Path)
IMAGE="cahtml5gw:14_2_1_13" (Change Version)
----------------------------------

