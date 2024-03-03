# TCP 3 ways handshake & 4 ways handshake
> 연결을 성립하고 해제
### 3 ways handshake
TCP는 정확한 전송 보장, 따라서 통신하기 전, 논리적인 접속 성립 위해 3 way handshake 진행
1. 클라이언트가 서버에 SYN 패킷을 보냄(sequence : x)
2. 서버가 SYN(x)를 받고 클라이언트에게 받았다는 신호인 ACK와 SYN 패킷을 보냄(sequence: y ACK: x + 1)
3. 클라이언트는 서버 응답 SYN(y)와 ACK(x + 1)을 받고 ACK(y + 1)을 서버로 보냄
### 4 ways handshake
연결 성립 이후 모든 통신이 끝나면 해제해야함
1. 클라이언트는 서버에게 연결을 종료한다느 FIN 플래그를 보냄
2. 서버는 FIN을 받고 확인했다는 ACK를 보냄(이때 모든 데이터를 보내기 위해 CLOSE_WAIT 상태)
3. 데이터를 모두 보냈다면 연결이 종료되었다는 FIN 플래그를 클라이언트에 보냄
4. 클라이언트는 확인하고 FIN 플래그를 서버에 보내는데 아직 받지 못한 데이터가 있을 수 있으니 Time_wait 상태
서버는 ACK 받은 이후 서버를 닫고
클라이언트는 TIME WAIT 기간동안 오지 않으면 닫는다