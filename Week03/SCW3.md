![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a5f507e-9f17-4960-9cd7-2611702befcd/Untitled.png)

**TCP/UDP 흐름제어**

1) 전달 받은 패킷이 중간에 회손되지는 않았는지?(오류 검출 방식) 확인하기 위해서 체크섬, 패리티 검사, CRC 등을 이용

세그먼트헤더에서 체크섬 필드를 통해 오류정정, 무결성 보호

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5ed390c9-29ce-4fc9-bb37-e3edb61a5ee1/Untitled.png)

2) 패킷이 중간에 유실되지는 않았는지?(확인 응답) 확인하기 위해서 수신측은 송신측으로부터 패킷을 받고 긍정 응답으로 ACK 패킷을 부정 응답으로 NACK 패킷을 발송

수신측은 송신측으로부터 응답 패킷을 받은 후 어떤 패킷을 다음에 보낼지 결정하게 되는데 이 과정에서 언제까지나 응답 패킷을 기다릴 수 없기 때문에 재전송 타이머가 동작 →  재전송 타이머가 끝나게되면 응답 패킷을 받지 않으면 유실로 간주하고 패킷을 재전송

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9794117a-314e-4aa7-a6c6-e15bfe4ecb38/Untitled.png)

여기서 등장하는 재전송 타이머(RTO, Retransmission Timeout)는 데이터를 재전송하기 위한 타이머 재전송 타이머는 RTT(Round Trip Time)과 어떠한 알고리즘(?)으로 계산되며 동적으로 정해진다. RTT는 3 Way Handshaking에서 SYN 패킷을 보내고 ACK 패킷을 받기까지의 시간이며, 해당 시점은 재전송 타이머가 정해지기 전이기 때문에 Initial RTO를 참고하게 되는데, Initial RTO는 운영체제에 따라서 다르게 설정되어 있으며 보통 1초이며 2제곱으로 늘어난다.

3) 패킷을 어떻게 재전송할지?(ARQ, Automatic Repeat reQuest) 확인하기 위해서 다음 패킷의 크기와 유실 시점으로부터 얼마나 패킷을 재전송할지 결정해야 함.

- Stop and Wait ARQ : 패킷을 한개씩만 보낼 수 있는 가장 단순한 방식. 수신측에서 패킷을 보내고 송신측으로부터 ACK 패킷을 전달 받아야 다음 패킷을 전송. 수신측은 재전송 타이머가 완료되기 전까지 응답 패킷을 받지 못할 경우 마지막에 보낸 패킷을 재전송.

 응답 패킷을 받기 전과 재전송 타이머가 완료되기 전까지 수신측은 아무것도 할 수 없기 때문에 가장 비효율적입니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/790fcf65-e049-4943-bb3a-8d673b2718ee/Untitled.png)

- Go Back N ARQ : 슬라이딩 윈도우를 이용하여 한번에 여러 패킷을 보낼 수 있으며 패킷 유실 시 유실된 시점부터 재전송하는 방식. 수신측은 순서대로 패킷이 도착하지 않았을 경우 패킷을 폐기하며 NACK 패킷으로 유실된 패킷을 재전송 요청. 만약 수신측은 재전송 타이머가 완료되기 전까지 응답 패킷을 받지 못할 경우 응답을 받지 못한 패킷부터 재전송합니다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2efce0e5-5154-46c2-b3db-cefb5d10aee4/Untitled.png)

- Selective Repeat ARQ : 슬라이딩 윈도우를 이용하여 한번에 여러 패킷을 보낼 수 있으며 패킷 유실 시 유실된 패킷만 재전송하는 방식. 수신측은 순서대로 패킷이 도착하지 않았을 경우 패킷을 버퍼에 보관하며 NACK 패킷으로 유실된 패킷을 재전송 요청. 재전송 받은 후 버퍼에 보관된 패킷과 재정렬.

 만약 수신측은 재전송 타이머가 완료되기 전까지 응답 패킷을 받지 못할 경우 응답을 받지 못한 패킷부터 재전송. 가장 효율적이지만 비교적 복잡하고 별도 버퍼와 재정렬이 필요!

슬라이딩 윈도우(Sliding Window)는 수신측과 송신측이 네트워크 상황과 메모리 버퍼를 고려하여 한번에 처리할 수 있는 메모리 버퍼 안에 윈도우 사이즈를 협의. 

수신측은 윈도우 사이즈 이내에서 한번에 패킷을 전송하며 ACK 패킷을 받은 후 새로운 패킷이 있는 방향으로 미는 과정을 반복, 수신측은 현재 수신할 수 있는 여유 윈도우 사이즈(RWND) 전송하면 송신측은 이를 참고하여 전송 윈도우 사이즈(AWND)를 결정. 만약 네트워크 상황이 좋지 않아 혼잡 제어를 위해 윈도우 사이즈의 조절해야 한다면 송신측은 혼잡 윈도우 사이즈(CWND)를 함께 참고하여 전송 윈도우 사이즈(AWND)를 결정

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/236eae17-64b7-4813-b6ed-9e471d633e1c/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fa7d0a63-1aba-47de-b976-a0351a90daed/Untitled.png)

- TCP는신뢰성 높은 전송을 목표로 하며 오류와 흐름을 제어하기 위해서오류 검출 방식, 확인 응답, ARQ 모두 사용하고 있다.

ARQ로는 GoBackN & Selective RepeatARQ 함께 사용

- UDP는빠른 전송을 목표로 하며 최소한의 오류를 제어하기 위해 오류 검출 방식만을 사용하고 있다.

Q1) 수신측은 송신측으로부터 응답 패킷을 받은 후 어떤 패킷을 다음에 보낼지 결정하게 되는데 이 과정에서 언제까지나 응답 패킷을 기다릴 수 없기 때문에 이것이 필요하다. 이것은 무엇인가?

-재전송타이머 (RTO)

Q2) TCP에서 사용하는 ARQ는?

-GoBackN & Selective Repeat ARQ
