Hariss Corner Detection 
Code :
img = cv2.imread("/content/eye.jpeg")
original = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
dest = cv2.cornerHarris(gray, 2, 3, 0.08)
dest = cv2.dilate(dest, None)
img[dest > 0.01 * dest.max()] = [0, 0, 255]
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
