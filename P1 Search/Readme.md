1. Depth First Search
    - Thuật toán: tìm kiếm theo độ sâu dài nhất lân lượt.
    - Giải thuật: 
        + Dùng Stack() để lưu trữ [Vị trí hiện tại, Hướng đi, Số nút đã đi] của 1 node hiện tại.
        + Nếu node đó đã đi qua thì bỏ qua.
        + Nếu chưa đi qua và node đó là vị trí đích thì return đường đi.
        + Nếu không phải vị trí đích thì tìm kiếm các node tiếp theo bằng hàm getSuccesors() và cho vào Stack

2. Breadth First Search
    - Thuật toán: tìm kiếm theo chiều rộng.
    - Giải thuật: 
        + Dùng Queue() để lưu trữ [Vị trí hiện tại, Hướng đi, Số nút đã đi] của 1 node hiện tại.
        + Nếu node đó đã đi qua thì bỏ qua.
        + Nếu chưa đi qua và node đó là vị trí đích thì return đường đi.
        + Nếu không phải vị trí đích thì tìm kiếm các node tiếp theo bằng hàm getSuccesors() và cho vào Queue

3. Uniform Cost Search
    - Thuật toán: tìm kiếm đường đi bằng cách duyệt các nút lân cận có kèm theo trọng số.
    - Giải thuật: 
        + Dùng PriorityQueue() để lưu trữ [Vị trí hiện tại, Hướng đi, Số nút đã đi] của 1 node hiện tại.
        + Node hiện tại sẽ được lấy bằng cách chọn trọng số nhỏ nhất từ priorityQueue
        + Nếu node đó đã đi qua thì bỏ qua.
        + Nếu chưa đi qua và node đó là vị trí đích thì return đường đi.
        + Nếu không phải vị trí đích thì tìm kiếm các node tiếp theo bằng hàm getSuccesors() và cho vào PriorityQueue và thêm trọng số của node đó.

4. A Star Search
    - Thuật toán: tìm kiếm đường đi bằng cách duyệt các nút lân cận có sử dụng hàm heuristic để đánh giá đường đi ngắn nhất.
    - Giải thuật: 
        + Dùng PriorityQueue() để lưu trữ [Vị trí hiện tại, Hướng đi, Số nút đã đi] của 1 node hiện tại.
        + Node hiện tại sẽ được lấy bằng cách chọn trọng số nhỏ nhất từ priorityQueue
        + Nếu node đó đã đi qua thì bỏ qua.
        + Nếu chưa đi qua và node đó là vị trí đích thì return đường đi.
        + Nếu không phải vị trí đích thì tìm kiếm các node tiếp theo bằng hàm getSuccesors() và cho vào PriorityQueue và thêm trọng số của node và hàm ước tính đường đi của node đó.

5. Finding All the Corners
    - Hàm init: khởi tạo vị trí ban đầu và vị trí cac dot
    - Hàm getStartState: trả lại ví trí ban đầu và vị trí các dot
    - Hàm isGoalState: true khi độ dài mảng state[1] lưu trữ vị trí dot == 0
    - Hàm getSuccessors: sử dụng gợi ý sẵn tính nextx, nexty
        + Nếu trùng vị trí các góc thì xóa góc đấy trong list chứa các góc
        + Nếu đó không là tường thì thêm vào successor vị trí tiếp theo
        + trả lại successors.
6. Corners Problem: Heuristic
   - Sử dụng Class CornerProblem Nhưng có thêm hàm tính khoảng cách ngắn nhất giữa vị trí agent và các dot
8. Suboptimal Search
   - Sử dụng thuật toán A* đã cài để tìm vị trí các food.
