# Prompt History Summary - Q3 AI Food Assistant

## 1. ตีโจทย์และวาง workflow

Prompt:

ช่วยอ่านโจทย์ข้อ 3 จากไฟล์ Excel และสรุปว่าต้องทำอะไร ตั้งแต่เริ่มจนจบ ต้องส่งอะไรบ้าง และควรทำ workflow อย่างไร

Output:

ได้ workflow สำหรับ AI Food Assistant: เก็บข้อมูลร้านอาหาร, clean data, scoring, AI analysis, automation, HTML final report และ reflection

## 2. ปรับ scope เป็น 5 ย่าน

Prompt:

โจทย์ต้องทำทั้ง 5 ย่าน ได้แก่ สยาม อารีย์ ทองหล่อ อโศก พร้อมพงษ์ และควรมีข้อมูล 25 ร้านต่อย่าน ช่วยปรับ workflow และ template ให้รองรับข้อมูล 125 ร้าน

Output:

สร้าง template สำหรับ 5 ย่าน มี Raw_GoogleMaps, Raw_Wongnai, Clean_Data, Scoring, Area_Top3, Prompt_History และ Submission_Checklist

## 3. เปลี่ยน data collection จาก Browse AI เป็น Apify

Prompt:

พี่จะเปลี่ยนมาใช้ Apify Store แทน Browse AI ช่วยบอกขั้นตอนและ actor ที่ควรใช้

Output:

แนะนำ Google Maps Scraper สำหรับ Google Maps และใช้ Wongnai เป็น source ที่ 2 สำหรับ validate Top 3 พร้อมขั้นตอน export CSV/XLSX

## 4. ตรวจ CSV จาก Apify

Prompt:

นี่คือไฟล์ restaurants_all_areas.csv ที่ export จาก Apify Google Maps Scraper ช่วยตรวจว่าข้อมูลครบไหม กี่ร้าน แยกย่านได้ไหม และทำอะไรต่อ

Output:

ตรวจพบ 200 ร้าน มีคอลัมน์ title, totalScore, reviewsCount, street, website, phone, categories, url และ categoryName จากนั้น clean/infer area และคัด Top25 ต่อพื้นที่

## 5. Clean data และ preliminary scoring

Prompt:

ช่วยจัดข้อมูล Google Maps ให้เป็น clean data, Top25 ต่อพื้นที่ และ Top3 preliminary

Output:

สร้าง googlemaps_clean_scoring_workbook.xlsx, googlemaps_top25_per_area_en.csv และ googlemaps_top3_preliminary_en.csv พร้อม scoring เบื้องต้น 100 คะแนน

## 6. เพิ่ม source ที่ 2 จาก Wongnai

Prompt:

พี่ทำไฟล์ Top-3 Restaurant.xlsx มาแล้ว มีร้าน Top 3 ของแต่ละย่านพร้อม Wongnai rating และ URL ช่วยรวมกับ Google Maps score

Output:

สร้าง final_top3_recommendations.xlsx มี Final_Top3, Area_Summary และ HTML_Copy พร้อม Google Maps URL + Wongnai URL

## 7. ทำ Google Sheets submission workbook

Prompt:

ช่วยรวมไฟล์นี้เข้า Google Sheets / ทำให้เป็นไฟล์เดียวสำหรับส่งงาน

Output:

สร้าง Q3_AI_Food_Assistant_Submission_Workbook.xlsx แล้วอัปโหลดเป็น Google Sheets native:

https://docs.google.com/spreadsheets/d/14RhEClkrsKdN_Ko45am6PHDZ-aDfVTYZlxuEgR3mi3w/edit

## 8. Automation ด้วย n8n

Prompt:

ช่วยทำ automation evidence ใน n8n ให้หน่อย

Output:

สร้าง n8n workflow JSON สำหรับ import:

Manual Trigger -> Read Final_Top3 CSV from Google Sheets -> Summarize Recommendations

ผล run สำเร็จ:

- status: OK
- totalRestaurantsRead: 15
- areasCovered: 5
- summary มี Ari, Siam, Thong Lo, Asok, Phrom Phong

## 9. HTML final report

Prompt:

ใช้ Google Sheets link, Final_Top3, Top10, n8n screenshots และ reflection ทำ HTML final report ให้ครบตามโจทย์

Output:

สร้าง q3-ai-food-assistant-report.html มี Header, Objective, Workflow Overview, Tools Used, Data Sources, Scoring Criteria, Top10 Ranking, Top3 Recommendation, Restaurant Comparison, Automation Evidence และ Reflection
