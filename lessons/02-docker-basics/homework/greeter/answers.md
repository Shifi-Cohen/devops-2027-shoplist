
1) docker build -t greeter:v1 + ניתוב
2) docker run -d --name greeter -p 9000:8000 greeter:v1
3) -e GREETING=Shalom
4) Shalom, Rivka!
5) FROM WORKDIR COPY pip install לא יסומנו כ CACHED כי ה IMAGE עובד בשכבות וכל שכבה שלפני השנויים עדיין עדכנית ולא צריכה להשתנות
