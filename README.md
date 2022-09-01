# simple-face-recognition-code
import cv2
cap = cv2.VideoCapture(0)

cv2.namedWindow("FaceDetection")
img_counter = 0

while True:
    _, frame = cap.read()
    cv2.imshow("FaceDetection", frame)

    key = cv2.waitKey(1)
    if key % 256 == 27:
        print("Camera is closed.")
        break

    elif key % 256 == 32:
        img_name = "ScreenShot_{}.png".format(img_counter)
        cv2.imwrite(img_name, frame)
        print("ScreenShot is taken".format(img_name))
        img_counter += 1

cap.release()
cv2.destroyAllWindows()
