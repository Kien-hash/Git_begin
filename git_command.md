# Các lệnh git thường dùng
## 1. Tạo branch ở local & remote: yêu cầu đã đăng nhập và cấu hình

- Tạo branch ở local: 
> git checkout -b <branch_name>

Lệnh này đồng thời chuyền luôn branch đang làm việc ở local sang branch mới

- Tạo branch mới có tên tương ứng trên remote:
> git push -u origin <branch_name>

Lệnh này vừa tạo mới đồng thời kết nối tương ứng branch hiện tại với git remote

## 2. Xoá branch ở local khi đã merge trên remote
> git branch -d <branch_name>



# Quy trình làm việc của github
Tương đối khác với gitlab, việc không có merge request để làm việc một cách chuyên nghiệp nên github có quy trình làm việc như sau:
> Create branch => Add Commit => Create Pull Request => Review and Discuss => Deploy => Merge

## 1. Create branch
![Create branch](https://i.ibb.co/4149CV4/Capture.png)

Trong một dự án, sẽ có một loạt các tính năng hoặc ý tưởng khác nhau được triển khai trong bất kì thời điểm nào (kiểu như sếp thích or khách nói thì bạn có việc để làm, thế thôi :D ) => các tính năng được hoàn thiện vào các thời điểm khác nhau. Branch (nhành) xuất hiện để giúp quản lý quy trình làm việc này.

Khi tạo một branch trong dự án của mình <=> tạo ra một bản copy của branch master tại thời điểm mà branch nhánh được tạo. Những thay đổi thực hiện trên một branch không ảnh hưởng đến branch chính (master), vì vậy bạn có thể tự do thử nghiệm và commit các thay đổi, đến khi nào được review là thành công thì có thể được merge vào master.

### Tip:
-   Nguyên tắc căn bản nhất: Bất kể cái gì đã nằm trên branch master đều phải chạy được, chạy ổn định, đáp ứng đủ yêu cầu kĩ thuật (xịn sò nhất mới được sếp merge vào chứ :D)
-   Nhánh tạo ra phải ở ngoài nhánh master, phải đặt tên có tính gợi nhớ.

## 2. Thêm các commit
![Add commits](https://i.ibb.co/LxmyJK6/Capture.png)

Bất cứ khi nào bạn thêm, chỉnh sửa hoặc xóa một tệp, sau đó quá trình lưu lại các thay đổi đó được gọi là commit. Các commit cho phép bạn lưu lại các phiên bản khác nhau của công việc mà bạn đang làm.

Các phiên bản khác nhau được tạo ra khi làm việc sẽ hình thành nên lịch sử minh bạch về công việc của bạn mà những người khác có thể theo dõi để hiểu bạn đã làm gì và tại sao. Mỗi commit đều có một phần mô tả, nên viết phần này một các gợi nhớ vắn tắt. Điều này cho phép ta quay lại các thay đổi nếu phát hiện thấy lỗi hay quyết định đi theo một hướng khác.

### Tip:
Thông báo commit rất quan trọng, đặc biệt vì Git theo dõi các thay đổi của bạn và sau đó hiển thị chúng dưới dạng commit khi chúng được đẩy lên máy chủ. Bằng cách viết thông điệp commit rõ ràng, bạn có thể giúp người khác theo dõi và cung cấp phản hồi dễ dàng hơn.

## 3. Mở Pull Request
![Open Pull Request](https://i.ibb.co/jgcn6XC/Capture.png)

Đấy là một tính năng tương tự như merge request của git lab nhưng kém chuyên nghiệp hơn (vì đồ free mà :d ). Pull Requests khời tạo phần thảo luận cho commit của bạn. Vì chúng được tích hợp chặt chẽ với Git repository bên dưới, nên bất kỳ ai cũng có thể thấy chính xác những thay đổi nào sẽ được merge nếu họ chấp nhận yêu cầu của bạn.

Bạn có thể mở một Pull Request tại bất kì thời điểm nào trong quá trình làm việc: khi có ít hoặc không có code nhưng muốn chia sẻ một số ảnh chụp màn hình hoặc ý tưởng chung, khi bạn gặp khó khăn và cần trợ giúp hoặc lời khuyên hoặc khi bạn sẵn sàng cho ai đó để xem xét công việc của bạn. Bằng cách sử dụng hệ thống @mention của GitHub trong Pull Request message, bạn có thể yêu cầu phản hồi từ những người hoặc nhóm cụ thể, cho dù họ ở bất kì nơi đâu.

### Tip
Pull Requests hữu ích để đóng góp vào các dự án nguồn mở và quản lý các thay đổi đối shared repositories. Nếu bạn đang sử dụng mô hình Fork & Pull, Pull Requests cung cấp một cách để thông báo cho những maintainer của dự án về những thay đổi mà bạn muốn họ xem xét. Nếu bạn đang sử dụng Mô hình Shared Repository, Pull Requests giúp review code và đối thoại về các thay đổi được đề xuất trước khi chúng được merge vào master.

## 4. Thảo luận & review code
![Discuss and review your code](https://i.ibb.co/Bs0Wyhj/image.png)

Khi Pull Request đã được mở, người hoặc nhóm xem xét  thay đổi của bạn có thể có câu hỏi hoặc nhận xét. Do phong cách viết code không phù hợp với các nguyên tắc của dự án, sự thay đổi thiếu các bài kiểm tra đơn vị hoặc có thể mọi thứ trông tuyệt vời và các đạo cụ theo thứ tự. Pull Request được thiết kế để khuyến khích và nắm bắt kiểu trò chuyện này.

Bạn cũng có thể tiếp tục thúc đẩy chi nhánh của mình để thảo luận và phản hồi về commit của bạn. Nếu ai đó nhận xét rằng bạn quên làm điều gì đó hoặc nếu có lỗi trong code, bạn có thể sửa lỗi đó trong chi nhánh của mình và đẩy mạnh thay đổi. GitHub sẽ hiển thị các commit mới của bạn và mọi phản hồi bổ sung mà bạn có thể nhận được trong chế độ xem Pull Request thống nhất.

### Tip
Nhận xét của Pull Request được viết bằng Markdown, vì vậy bạn có thể nhúng hình ảnh và biểu tượng cảm xúc, sử dụng các khối văn bản được định dạng trước và các định dạng nhẹ khác.

## 5. Triển khai
![Deploy](https://i.ibb.co/T04RBck/image.png)

Với GitHub, bạn có thể triển khai từ một nhánh để thử nghiệm lần cuối trong quá trình sản xuất trước khi merge với master.

Khi Pull Request của bạn đã được xem xét và chi nhánh vượt qua các bài kiểm tra của bạn, bạn có thể triển khai các thay đổi của mình để xác minh chúng trong sản phẩm. Nếu chi nhánh của bạn gây ra sự cố, bạn có thể khôi phục nó bằng cách triển khai chi nhánh master hiện có vào sản phẩm.

Các đội khác nhau có thể có các chiến lược triển khai khác nhau. Đối với một số người, tốt nhất có thể là triển khai đến một môi trường thử nghiệm được cung cấp đặc biệt. Đối với những người khác, triển khai trực tiếp vào sản phẩm có thể là lựa chọn tốt hơn dựa trên các yếu tố khác trong quy trình làm việc của họ.

## 6. Merge
![Merge](https://i.ibb.co/m8x0Rkb/image.png)

Bây giờ các thay đổi của bạn đã được xác minh trong quá trình làm việc, đã đến lúc merge code của bạn vào nhánh master.

Sau khi merge, Pull Request sẽ lưu giữ bản ghi về các thay đổi lịch sử đối với code của bạn. Bởi vì chúng có thể tìm kiếm được, chúng cho phép bất kỳ ai quay ngược thời gian để hiểu tại sao và cách một quyết định được đưa ra.

ProTip
Bằng cách kết hợp các từ khóa nhất định vào văn bản của Pull Request, bạn có thể liên kết các vấn đề với code. Khi Pull Request của bạn được merge, các vấn đề liên quan cũng được đóng lại. Ví dụ: nhập cụm từ Closes #32 sẽ đóng issue số 32 trong repository. 