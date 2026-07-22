---
title: "Blog 1"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---



### Các điểm chính cần nắm:
* **Khái niệm:** Session policy là một IAM policy inline được chỉ định khi tạo hoặc cập nhật Pod Identity association.
* **Quyền hiệu quả:** Bằng phép giao (intersection) giữa permissions của IAM role và session policy → session policy chỉ có thể thu hẹp, không thể mở rộng quyền.
* **Tránh cấp quyền thừa:** Giúp tránh tình trạng over-permissioning khi reuse chung một IAM role cho nhiều workloads có nhu cầu khác nhau.
* **Phạm vi hỗ trợ:** Hỗ trợ cả same-account và cross-account (qua IAM role chaining).
* **Tối ưu hạn mức:** Giảm đáng kể số lượng IAM roles cần quản lý, tránh chạm giới hạn quota IAM trong cluster lớn.
* **Cấu hình dễ dàng:** Thao tác thuận tiện qua AWS Management Console, AWS CLI hoặc AWS SDK khi tạo association giữa Kubernetes ServiceAccount và IAM role.

Tính năng này đặc biệt hữu ích khi bạn có nhiều ứng dụng chạy trên cùng một IAM role nhưng cần giới hạn quyền khác nhau (ví dụ: một pod chỉ đọc S3 bucket cụ thể, pod khác chỉ gọi một số API nhất định).

![Sơ đồ Kiến trúc Mini traveloka booking](/images/Diagram.png)

> **Tài liệu tham khảo:**
> * videos hướng dẫn vẽ sơ đồ : [Xem tại đây](https://www.youtube.com/watch?v=l8isyDe-GwY)
> * Link bài gốc trên AWS Study Group VN: [Xem bài viết gốc](https://www.facebook.com/photo?fbid=2705511749850703&set=gm.2215708592527434&idorvanity=660548818043427&locale=vi_VN
)