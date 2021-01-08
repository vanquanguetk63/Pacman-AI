# Q1

- Viết tác nhân lặp lại giá trị trong ValueIterationAgent trong file valueIterationAgent.py
- Tác nhân là 1 công cụ lập kế hoạch ngoại ngoại tuyến, không phải tác nhân học tăng cường
  -> vì vậy tùy chọn đào tạo có liên quan là số lần lặp lại giá trị mà nó sẽ chạy (tùy chọn -i) trong giai đoạn lập kế hoạch ban đầu của nó. ValueIterationAgent lấy MDP khi xây dựng và chạy lặp giá trị cho số lần lặp được chỉ định trước khi hàm tạo trả về.

- Phép lặp giá trị tính toán các ước lượng k-bước của các giá trị tối ưu Vk, triển khai các phương pháp sau cho ValueIterationAgent bằng cách sử dụng Vk.

`computeActionFromValues`(trạng thái)
tính toán hành động tốt nhất theo hàm giá trị được cung cấp bởi giá trị tự.
`computeQValueFromValues` ​​(trạng thái, hành động) trả về giá trị Q của cặp (trạng thái, hành động) được cung cấp bởi hàm giá trị do self.values ​​cung cấp.

```python
  python autograder.py -q q1
```

```python
  python gridworld.py -a value -i 100 -k 10
```

```python
  python gridworld.py -a value -i 5
```

# Question 2 (1 point): Phân tích điểm qua cầu

- BridgeGrid là một bản đồ dạng lưới với trạng thái đầu cuối có phần thưởng thấp và trạng thái cuối có phần thưởng cao được ngăn cách bởi một "cây cầu" hẹp, ở hai bên là hố sâu có phần thưởng âm cao. Tác nhân bắt đầu gần trạng thái phần thưởng thấp. Với chiết khấu mặc định là 0,9 và độ ồn mặc định là 0,2, chính sách tối ưu không qua cầu. Chỉ thay đổi MỘT trong các thông số chiết khấu và tiếng ồn để chính sách tối ưu khiến đại lý nỗ lực qua cầu. Đặt câu trả lời của bạn trong question2 () of analysis.py. (Tiếng ồn đề cập đến tần suất một tác nhân kết thúc ở trạng thái kế thừa không mong muốn khi họ thực hiện một hành động.) Giá trị mặc định tương ứng với

```python
  python gridworld.py -a value -i 100 -g BridgeGrid --discount 0.9 --noise 0.2
```

```python
  python autograder.py -q q2
```

# Question 3 (5 points): Policies

- Cho một bản đồ cho trước, có điểm trả giá
- Trong câu hỏi này, bạn sẽ chọn cài đặt của các tham số chiết khấu, độ ồn và phần thưởng sống cho MDP này để tạo ra các chính sách tối ưu của một số loại khác nhau. Việc bạn cài đặt các giá trị tham số cho từng phần phải có thuộc tính mà nếu tác nhân của bạn tuân theo chính sách tối ưu của nó mà không bị nhiễu, nó sẽ thể hiện hành vi đã cho. Nếu một hành vi cụ thể không đạt được đối với bất kỳ cài đặt thông số nào, hãy khẳng định rằng chính sách là không thể bằng cách trả về chuỗi 'KHÔNG CÓ THỂ'.

* Dưới đây là các loại chính sách tối ưu mà bạn nên cố gắng tạo ra:

- Thích lối ra gần (+1), mạo hiểm với vách đá (-10)
- Thích lối ra gần (+1), nhưng tránh vách đá (-10)
- Thích lối ra xa (+10), mạo hiểm với vách đá (-10)
- Thích lối ra xa (+10), tránh vách đá (-10)
- Tránh cả lối ra và vách đá (vì vậy một tập phim sẽ không bao giờ kết thúc)

```python
  python autograder.py -q q3
```

# Question 4 (5 points): Q-Learning

- Viết Q-learning agent, nó thực hiện rất ít trong việc xây dựng, mà thay vào đó học bằng cách thử và sai từ các tương tác với môi trường thông qua phương pháp cập nhật (trạng thái, hành động, trạng thái tiếp theo, phần thưởng). Sơ lược về Q-learning được chỉ định trong QLearningAgent trong qlearningAgents.py và bạn có thể chọn nó bằng tùy chọn '-a q'. Đối với câu hỏi này, bạn phải triển khai các phương thức `update`, `computeValueFromQValues`, `getQValue` và `computeActionFromQValues`.

Với bản cập nhật Q-learning được cung cấp, bạn có thể xem Q-learningner của mình học dưới sự điều khiển thủ công, sử dụng bàn phím:

```python
python gridworld.py -a q -k 5 -m
```

```python
python autograder.py -q q4
```

# Question 5 (3 points): Epsilon Greedy

- Hoàn thành tác nhân học hỏi Q của bạn bằng cách triển khai lựa chọn hành động tham lam epsilon trong `getAction`, có nghĩa là nó chọn các hành động ngẫu nhiên trong một phần thời gian epsilon và theo cách khác, giá trị Q tốt nhất hiện tại của nó. Lưu ý rằng việc chọn một hành động ngẫu nhiên có thể dẫn đến việc chọn một hành động tốt nhất - nghĩa là bạn không nên chọn một hành động tối ưu phụ ngẫu nhiên mà nên chọn bất kỳ hành động pháp lý ngẫu nhiên nào.


```python
python autograder.py -q q5
```

```python
python gridworld.py -a q -k 100 
```
```python
python crawler.py
```

# Question 6 (1 point): Bridge Crossing Revisited
- Đầu tiên, đào tạo một Q-learning hoàn toàn ngẫu nhiên với tốc độ học mặc định trên BridgeGrid không ồn ào trong 50 tập và quan sát xem nó có tìm ra chính sách tối ưu hay không.

```python
python gridworld.py -a q -k 50 -n 0 -g BridgeGrid -e 1
```
- Bây giờ hãy thử thử nghiệm tương tự với epsilon bằng 0. Có epsilon và tỷ lệ học tập mà khả năng cao (lớn hơn 99%) là chính sách tối ưu sẽ được học sau 50 lần lặp không? question6 () trong analyse.py sẽ trả về một bộ gồm 2 mục là (epsilon, tỷ lệ học tập) HOẶC chuỗi 'KHÔNG CÓ THỂ' nếu không có. Epsilon được kiểm soát bởi -e, tỷ lệ học tập bằng -l.

```python
python autograder.py -q q6
```


# Question 7 (1 point): Q-Learning and Pacman

```python
python pacman.py -p PacmanQAgent -x 2000 -n 2010 -l smallGrid 
```

```python
python autograder.py -q q7
```

```python
python pacman.py -p PacmanQAgent -n 10 -l smallGrid -a numTraining=10
```

# Question 8 (3 points): Approximate Q-Learning

```python
python autograder.py -q q8
```