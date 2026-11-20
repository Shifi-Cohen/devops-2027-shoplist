המוצר נוסף בהצלחה


1
chart הוא התבנית, התיקייה helm/shoplist. release הוא התקנה אחת שלו עם שם ו-namespace, כמו shop. מאותו chart אפשר להתקין כמה releases

2
Helm מקבל את ה-namespace מבחוץ, עם -n shop --create-namespace, ומכניס אותו לכל קובץ דרך {{ .Release.Namespace }}. אילו ה-namespace היה כתוב בתוך ה-chart, אי אפשר היה להתקין אותו ב-namespace אחר

3
מ-values.yaml, ברירת המחדל. קובץ -f דורס רק את מה שכתוב בו, וכל השאר נשאר

4
rolling update: Kubernetes לא מוריד pod ישן עד שהחדש מוכן, וה-readinessProbe הוא מה שקובע אם הוא מוכן. ה-pod החדש לא עלה, אז הישנים נשארו ו-Service המשיך לשלוח אליהם

5
rollback לא מוחק היסטוריה. הוא יוצר revision חדש עם התוכן של revision 2. כך רואים מה קרה ומתי, ואפשר גם לחזור על ה-rollback

6
helm uninstall היה מוחק גם את ה-PVC, ואיתו את המוצרים

7
מפתח שלא קיים ב-values מחזיר ריק, לא שגיאה. אז replicas: יצא ריק, ו-Kubernetes השתמש בברירת המחדל שלו, 1. מגלים את זה עם helm template, שמראה replicas: בלי מספר

8
זיכרון: מעל 512Mi ה-container נהרג (OOMKilled) ועולה מחדש. CPU: מעל ליבה אחת הוא רק מואט (throttling). ההבדל: זמן CPU אפשר לחלק ולהמתין לו, אבל זיכרון שכבר תפוס אי אפשר לקחת בחזרה בלי להרוג את התהליך

9
גיבוי הוא משימה שמסתיימת. Deployment דואג שה-pod ירוץ תמיד, אז כשהגיבוי היה מסתיים הוא היה מקים אותו שוב ושוב. היו נוצרים גיבויים בלי סוף , ולא פעם בלילה