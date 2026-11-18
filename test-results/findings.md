# E2E findings

## Khảo sát và kiểm chứng tính năng AI theo từng Role > 1. Super Admin: Quản trị và kiểm soát tham số vận hành AI

- **note** Super Admin AI parameters: Trợ lý AI 3 tham số Công tắc tổng của các tính năng AI Đã tùy chỉnh Tắt để dừng mọi lời gọi đến dịch vụ trí tuệ nhân tạo. Giá trị hiện hành Bật Mặc định Tắt Đơn vị công tắc Thời điểm thay đổi: 23:33 18/11/2026 Thao tác Tóm tắt hàng chờ duyệt bằng AI Đã tùy chỉnh Chỉ hoạt động khi công tắc trí tuệ nh _(/dashboard/super-admin?tab=reminders)_

## Khảo sát và kiểm chứng tính năng AI theo từng Role > 2. Spending Approver: Tóm tắt hàng chờ duyệt chi bằng AI (US-15-05)

- **note** Spending Approver source: {"queueRevision":"db32dec218541f5e0cb44c509823a1ef77907bea18eeda857a8d0a717e5f1497","stepCount":9,"omittedCount":0} _(/dashboard/spending-approver?tab=queue)_
- **note** Spending Approver AI result: Tóm tắt bằng AI Giả lập — không phải AI Chỉ giúp đọc nhanh hàng chờ, không thay bạn quyết định. Hãy mở từng yêu cầu để xem đủ thông tin trước khi quyết. Tóm tắt lại Bước duyệt chi GitHub cho Hoàng Văn Em, chi phí ước tính 200000 VND. Lý do: [SV-R02] Lô đã trình, kiểm tra ngân sách: trong số cơ sở; đ _(/dashboard/spending-approver?tab=queue)_

## Khảo sát và kiểm chứng tính năng AI theo từng Role > 3. Manager: Tóm tắt hàng chờ duyệt nhu cầu (US-15-05)

- **note** Manager source: {"queueRevision":"3af20b8113b9339da999ff6fb675aa0b93389590476e4bb0b5973784ce8c035e","stepCount":1,"omittedCount":0} _(/dashboard/manager?tab=team-requests)_

## Khảo sát và kiểm chứng tính năng AI theo từng Role > 4. Finance: Kiểm chứng hiện trạng AI đối với vai Tài chính

- **console-error** Failed to load resource: the server responded with a status of 401 (Unauthorized) _(/dashboard/finance)_
- **http-4xx** GET /api/v1/ai/access-request-summaries/source -> 401 AUTHENTICATION_REQUIRED _(/dashboard/finance)_
- **note** Finance gọi /api/v1/ai/access-request-summaries/source: {"status":401} _(/dashboard/finance)_
- **console-error** Failed to load resource: the server responded with a status of 404 (Not Found) _(/dashboard/finance)_
- **http-4xx** GET /api/v1/ai/cost-reports -> 404 HTTP_NOT_FOUND _(/dashboard/finance)_
- **http-4xx** GET /api/v1/ai/cost-report-summaries -> 404 HTTP_NOT_FOUND _(/dashboard/finance)_
- **note** Kiểm tra endpoint AI Finance: {"/backend/api/v1/ai/cost-reports":404,"/backend/api/v1/ai/cost-report-summaries":404,"/backend/api/v1/cost-reports/draft":404} _(/dashboard/finance)_
