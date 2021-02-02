# REDcap-Project
คู่มือขั้นตอนลงข้อมูล
# **ขั้นตอนการกรอกข้อมูลลงระบบฐานข้อมูลอิเล็กทรอนิกส์ (REDCap)**
1. เตรียมประชุม ชี้แจงรายละเอียด วางแผนร่วมกับทีมผู้รับผิดชอบโครงการ Siriraj Genomics Thailand ได้แก่ เจ้าหน้าที่บริหารงานทั่วไป ผู้ช่วยวิจัย นักสถิติ เจ้าหน้าที่เก็บข้อมูล ผู้ประสานงาน และอาจารย์ที่รับผิดชอบโครงการ 
2. ติดต่อประสานงานขอรับแบบสอบถาม (CRF) จากผู้ช่วยวิจัย มาตรวจสอบและวางแผนสร้าง Data dictionary เพื่อให้สามารถนำข้อมูลที่เก็บลงระบบฐานข้อมูลอิเล็กทรอนิกส์ (REDcap) โดยข้อมูลจะประกอบด้วย 5 ส่วนดังนี้ 
* 2.1 Participant Information ข้อมูลพื้นฐานของอาสาสมัคร
* 2.2 Laboratory ใบขอตรวจทางห้องปฏิบัติการอณูพันธุศาสตร์
* 2.3 Consent หนังสือแสดงเจตนายินยอมเข้าร่วมวิจัย
* 2.4 CRF แบบสอบถาม
* 2.5 Germline Testing Indication
## ขั้นตอนการลงข้อมูล REDcap ##
  |  ตัวแปร REDcap  |  ตัวแปร CRF   | คำอธิบายตัวแปร | เงื่อนไขตัวแปร |
  |-------------|--------------|-------------------|-----------|
  |  SEX -> Female,Male |    เพศ -> หญิง ชาย      |  เพศของอาสาสมัคร|-|
  |Birth Day(DD-MM-YYYY)|วันเดือนปีเกิด (วว-ดด-ปป)|วันเดือนปีเกิดของอาสาสมัคร|  ปีต้องแปลงเป็น ค.ศ.|
  |Date of data collection (DD-MM-YYYY) | วันที่บันทึกข้อมูล (วว-ดด-ปป)|วันที่กรอก CRF |ปีต้องแปลงเป็น ค.ศ.|
  |Age at enrollment | อายุเมื่อบันทึก (ปี)| อายุเมื่อกรอก CRF| บันทึกเป็นปี |
  |Projects involved -> Cancer,Rare disease,Pharmacogenomics,NCD,Infectious Diseases|เกณฑ์เข้าร่วมโครงการ->โรคมะเร็ง ,โรคหายาก , เภสัชพันธุศาสตร์/แพ้ยา ,โรค NCD ,โรคติดเชื้อโรค|โรคที่อาสาสมัครเป็น|ตอบได้ข้อเดียว|
|Is this the patient or the relatives?-> Patient, Relative|ผู้เข้าร่วมวิจัยเป็น -> ผู้ป่วย , ญาติ|คนกรอก CRF |-|\
|Relationship to the index case-> Parents,Siblings,Offspring,Grandparents,Uncle/Aunt|กรณีเป็นญาติ มีความสัมพันธ์เป็น-> พ่อ-แม่ ,พี่น้อง,บุตร,ปู่ย่าตายาย,ลุงป้าน้าอา|ความสัมพันธ์กับผู้ป่วย|ข้อคำถามจะแสดงเมื่อเลือกตัวเลือก ญาติ|
|For cancer and rare disease, do the patient have a family history?-> No,Yes,Unknown|ครอบครัวของผู้วิจัยมีสมาชิกในครอบครัวเป็นโรคกลุ่มเดียวกันในข้อ3หรือไม่(สำหรับโรคมะเร็งและโรคหายาก)->ไม่มี,มี(กีคน),ไม่ทราบ/ไม่แน่ใจ|ครอบครัวของผู้วิจัยมีใครเป็นโรคตามข้อ 3 หรือไม่|ถ้าตอบมี ระบุจำนวนคน|
|Hospital that recruited the patient-> Hospital in the project, Referred from other hospital,Unknown|โรงพยาบาลที่ผู้ร่วมวิจัยเข้ารับการรักษา->โรงพยาบาลที่เข้าร่วมโครงการ,โรงพยาบาลส่งต่อ,ไม่ทราบ/ไม่แน่ใจ|โรงพยาบาลที่เข้ารับการรักษา|-|
|Health policy used by the patient-> Universal Coverage,Social Security,Government Healthcare,Private/Insurance/No coverage|สิทธิการรักษาของผู้เข้าร่วมวิจัย->ประกันสุขภาพถ้วนหน้า,ประกันสังคม,ข้าราชการ/รัฐวิสาหกิจ,ประกันสุขภาพเอกชน/ไม่มี|สิทธิการรักษาของผู้วิจัย|-|
|Biospecimens obtained from the patient->Blood,Surgical tissues,Buccal swab,Skin biopsy|การเก็บสิ่งส่งตรวจ->เลือด,ชิ้นเนื้อผ่าตัด,เยื่อบุช่องปาก,เซลล์ผิวหนัง|สิ่งส่งตรวจของผู้วิจัย|ตอบได้มากกว่า 1|
|Has the patient or family received any genetic test before->No,Yes but got negative result,Yes but positive result not related to the current disase,Yes with positive result for the current condition|ประวัติการได้รับการตรวจทางพันธุกรรมก่อนหน้านี้(ผู้ร่วมวิจัยหรือสมาชิกในครอบครัว)->ไม่เคย,เคยตรวจ ไม่พบความผิดปกติ,เคยตรวจ พบความผิดปกติแต่ไม่เกี่ยวข้องกับโรค,เคยตรวจ พบความผิดปกติเกี่ยวข้องกับโรค|ประวัติการได้รับการตรวจทางพันธุกรรมก่อนหน้านี้|-|
|
|Treatment status of the patient-> Never receive treatment,Complete treatment,targeted treatment specific to disease,Paliative care,Treatment is not applicable|ผู้เข้าร่วมวิจัยได้รับการรักษาโรคในขณะนี้หรือไม่(กรณีโรคมะเร็งและโรคหายาก)->ไม่เคยรักษา,รักษาครบ/หยุดรักษาแล้ว,ได้รับการรักษาจำเพาะ(ตรงกับโรค),ได้รับการรักษาตามอาการ,ไม่เกี่ยวข้อง(โรคอื่นให้ตอบข้อนี้)|ผู้เข้าร่วมวิจัยได้รับการรักษาโรคในขณะนี้หรือไม่|เฉพาะโรคมะเร็งและโรคหายาก|
|Choose the organ with disease manifestation->No/ Not related,Brain,Eyes,Head and neck,Lungs or respiratory track,Esophagus,Stomach,Small intestine,Large bowel and anus,Liver and bile ducts,Pancreas,Uterus or Prostate,Ovary or testis,Other internal Reproductive organ,Orther external reproductive organ ,Kidney,Urinary track,Breast,Heart muscle,Heart valve, Cardiac conduction system,Arterial disease,Venous system, Lymphatic vessels,Lymph node,Connective tissue,Red Blood Cells,White Blood Cells,Platelets,Bone marrow,Skeletal muscles,Bone and joint,Immune system, Peripheral nervous system,Spinal cord, Vertebrae,Ears/Hearing,skin

