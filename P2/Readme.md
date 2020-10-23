Câu 1: Viết lại hàm evaluationFunction():

Đầu tiên mặc định khoảng cách giữa pacman vs ma và thức ăn gần nhất là 2000
Nếu con ma đang không trong thời gian bị hoảng sợ thì ta đánh giá lại khoảng cách giữa pacman và ma là khoảng cách mahattan sao cho khoảng cách này là xa nhất.
Trong lúc đó đánh giá lại khoảng cách giữa pacman và thức ăn là khoảng cách mahatan sao cho khoảng cách này là bé nhất.
Câu 2: Cài đặt thuật toán minimax để xác định hành động cho pacman

Nếu agentIndex = 0 (ma nhiều hơn 1) trả về maxvalue, Nếu agentIndex != 0 thì trả về minvalue. Trong đó maxvalue và minvalue lần lượt là hành động tốt nhất sau khi thực hiện 1 hành động trước đó.
Cuối cùng sử dụng hàm minimax để tính ra maxScore và bestAction
Câu 3: Tương tự như câu 2 nhưng ta sử dụng thêm 2 biến alpha và beta.

Khác với câu 2 thì ta thêm 2 biến a và b ở 2 hàm maxvalue và minvalue để loại đi 1 số hành động không cần thiết và tìm ra hành động tiếp theo tốt nhất.
Cuối cùng truyền vào 2 biến alpha và beta để tìm ra maxscore và bestaction.
Câu 4: Tương tự như câu 2

Khác với câu 2 ở chỗ ở trường hợp agentIndex!= 0 thì thay vì tìm min của các giá trị minimax thì đi tìm giá trị trung bình.