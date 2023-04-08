# Hyperledger-Fabric-Platform-Vol.1
# ขอภาษาไทย 
# 7 เมษายน 2566 ส่งต้นฉบับหนังสือ Hyperledger-Fabric-Platform-Vol.1
#ตัวอย่างโค๊ด รอตรวจสอบ (โล่ง มันเหมือนยกหินสักตันออกจากอก) #หลังโดนฝรั่งเอาเปรียบมายาวนาน ทำเองสา
รอๆๆ หาไรทำดี
อยากได้ปก javascript + Python(เจ้างูเหลือมของฉัน) สโลแกน ก้าวข้ามมันไป เเต่ใจผูกพัน อะหะ #บ้า!!
javascript อยู่กันมานาน ถ้าจะก้าวไป Python web 3.0 มันต้องมีอะไรร่วมกัน น้าน ปกหนังสือต้องไม่ธรรมดา ต้องเป็นโค้ดง่าย+ยากๆ รวมกัน
1.ให้โค้ดรัน javascript ใน cmd ของ windows เเละ Python API ออกมาเป็นรูปปก ????
เจ้านายท่านหนึ่งราว 3 ปีก่อน ผู้กล้าลงทุน 1000 บาท ให้เช่าเชฟเวอร์ที่ต่างประเทศ โดยที่ไม่รู้ว่ามันจะทำอะไรวะ o.k
ส่งหนังพอ ครับ ใกล้ละครับผมสร้างแอพพิเคชั่นเเละการเชื่อมต่อไว้เเล้ว เชิฟเก่าจะหมดอายุ วันที่10 เมษา จะอัพลงเชิฟใหม่เลย
แอพ ที่ส่งหนัง...หากลุ่มเเล้วไม่หมดอายุเเค่7วัน เเล้วต้องคมชัดเเบบ hd {เสร็จยังน้อง...O.K
6 เดือนไม่หมดอายุ เก็บไฟล์ลิ้งในตัวได้ 20 GB ปลอดภัย FULL HD
อีกท่านพี่ชาย ผมกินหนูเป็นก็ที่นี้แหละ 1พันกว่าบาทชอต์ฟเเวร์ลิขสิทธิ์เเท้ ราว 2 ปีก่อนที่ชื้อให้ตอนสอนออนไลน์ 
เราได้เรียนรู้ว่าการใช้ของเเท้เเละของปลอมมันโคตรจะต่างกันจริงๆ อีกท่านก็รู้ๆกันอยู่ ท่าน Pigman
#o.k
![Google ](https://www.google.co.th/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png)
..............................................
from PIL import Image, ImageDraw, ImageFont

#กำหนดขนาดภาพ
width = 800
height = 1200

#สร้างภาพเปล่า
img = Image.new('RGB', (width, height), color='white')

# เพิ่มข้อความ "Blockchain Network"
draw = ImageDraw.Draw(img)
text = 'Blockchain Network'
font = ImageFont.truetype('arial.ttf', 100)
textwidth, textheight = draw.textsize(text, font)
x = (width - textwidth) / 2
y = (height - textheight) / 2
draw.text((x, y), text, font=font, fill='black')

#เพิ่มเส้นขอบและบันได
draw.rectangle((50, 50, width-50, height-50), outline='black', width=10)
draw.line((50, height-200, width-50, height-200), fill='black', width=10)

#บันทึกภาพปก
img.save('cover.jpg')
# โค้ดข้างต้นจะสร้างภาพปกหนังสือที่มีขนาด 800x1200 พิกเซล มีข้อความ "Blockchain Network" อยู่ตรงกลาง มีเส้นขอบและบันไดรอบข้าง และบันทึกภาพปกเป็นไฟล์ JPEG 
ชื่อ "benefactor_cover.jpg" ในไดเร็กทอรีเดียวกับไฟล์ Python script ที่เรียกใช้งาน Pillow library นี้

สร้างภาพปกหนังสือด้วย Python ด้วยการใช้ library ชื่อ Pillow มีดังนี้:

1.กำหนดขนาดภาพ (width, height) ที่ต้องการสร้าง
2.สร้างภาพเปล่าโดยใช้คำสั่ง Image.new('RGB', (width, height), color='white') เพื่อสร้างภาพสีขาวตามขนาดที่กำหนด
3.เพิ่มข้อความหรือภาพลงในภาพเปล่าที่สร้างด้วยคำสั่ง ImageDraw.Draw(img) เช่น เพิ่มข้อความ "Blockchain Network" ด้วยคำสั่ง draw.text() 
และกำหนดตำแหน่งและขนาดของข้อความด้วย font=ImageFont.truetype('arial.ttf', 100) เป็นต้น
เพิ่มเส้นขอบและบันไดรอบข้างด้วยคำสั่ง draw.rectangle() และ draw.line()
บันทึกภาพปกเป็นไฟล์ JPEG ด้วยคำสั่ง img.save('benefactor_cover')

from PIL import Image

# โหลดภาพปกหนังสือ
image = Image.open("book_cover.jpg")

# ปรับขนาดภาพเป็น 800x1200 pixels
image = image.resize((800, 1200))

# บันทึกภาพ
image.save("book_cover_resized.jpg")
import cv2

# โหลดภาพปกหนังสือ
image = cv2.imread("book_cover.jpg")

# แปลงภาพเป็น grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# ทำการตัดภาพ
cropped_image = gray_image[50:500, 100:800]

# บันทึกภาพ
cv2.imwrite("book_cover_cropped.jpg", cropped_image)
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

# โหลดภาพปกหนังสือ
image = mpimg.imread("book_cover.jpg")

# แสดงภาพ
plt.imshow(image)
plt.show()
import subprocess

# ใช้คำสั่ง convert ของ ImageMagick เพื่อแปลงไฟล์รูปภาพ
subprocess.run(["convert", "book_cover.jpg", "-resize", "800x1200", "book_cover_resized.jpg"])
