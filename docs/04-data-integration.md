# 04) نموذج البيانات والتكامل

## توحيد الهوية
- `user_id` موحد عبر كل الخدمات.
- ربط `student_id` بملف الطالب المركزي.

## عقود أحداث موحدة
- **grade.recorded**
  - `event_id`, `student_id`, `subject`, `score`, `max_score`, `source`, `timestamp`
- **question.attempted**
  - `event_id`, `student_id`, `question_id`, `result`, `weak_skill`, `timestamp`
- **session.created**
  - `event_id`, `user_id`, `role`, `device`, `ip_hash`, `timestamp`

## التكامل الحدثي
- Yara ترسل نقاط الضعف إلى Student Profile.
- Student Profile يرسل توصيات تعلم علاجية.
- Live Library تستقبل الاستعلامات العلاجية تلقائيًا.
