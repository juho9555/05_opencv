# OpenCV
### 📌 주요 내용
- `pyzbar`와 `OpenCV`를 이용해 **웹캠으로 QR코드 인식**
- 인식된 QR코드의 **외곽선을 녹색 사각형**으로 표시
- QR코드 내부 정보(예: 링크 주소)를 **QR 위에 출력**
- 인식된 링크로 **사이트 접속 가능**

### 핵심 코드
- `pyzbar.decode()` – QR 코드 디코딩
- `cv2.rectangle()` – QR코드 외곽선 그리기  
  ```python
  cv2.rectangle(img, (d.rect[0], d.rect[1]), 
                     (d.rect[0] + d.rect[2], d.rect[1] + d.rect[3]), 
                     (0, 255, 0), 15)

---

### 📌 단일 마커(ArUco 등) 인식 및 거리 경고

- 단일 마커를 웹캠으로 인식
- 인식된 마커의 **위치(Pos)**, **회전(Rot)** 값 추출
- 거리 계산 후, **거리에 따른 경고 메시지 출력**  

<img width="642" height="512" alt="image" src="https://github.com/user-attachments/assets/5630a1f2-fcc8-4efe-8fb7-f4fa7bd8747a" />


### 사용 함수 및 처리 흐름
- `cv2.aruco.detectMarkers()`
- `cv2.aruco.estimatePoseSingleMarkers()`
- 거리 계산 → 임계값 설정 → 경고 텍스트 출력

---

## 핵심 키워드 요약

| 기능                    | 핵심 함수 / 메서드                          |
|-------------------------|---------------------------------------------|
| **QR 코드 인식**        | `pyzbar.decode()`                          |
| **QR 외곽선 시각화**    | `cv2.rectangle()`                          |
| **텍스트 표시**         | `cv2.putText()`                            |
| **체커보드 캘리브레이션** | `cv2.findChessboardCorners()`<br>`cv2.calibrateCamera()` |
| **왜곡 보정**           | `cv2.initUndistortRectifyMap()`<br>`cv2.remap()` |
| **마커 인식 및 포즈 추정** | `aruco.ArucoDetector.detectMarkers()`<br>`cv2.solvePnP()` |
| **좌표축 시각화**       | `cv2.drawFrameAxes()`                      |



---
