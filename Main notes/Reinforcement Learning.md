[[Machine Leanring - AI]]
Reinforcement learning (RL) là một lĩnh vực của học máy (machine learning) trong đó một agent (tác nhân) học cách thực hiện các hành động trong một môi trường để tối đa hóa một phần thưởng tổng hợp nào đó. Cơ bản của RL là sự tương tác liên tục giữa agent và môi trường, thông qua một quá trình thử và sai, để tìm ra chiến lược tối ưu.
### Các thành phần chính của RL

1. **Agent (Tác nhân)**: Đây là thực thể học hỏi và đưa ra các quyết định.
2. **Environment (Môi trường)**: Đây là thế giới mà tác nhân tương tác với. Môi trường phản hồi lại các hành động của tác nhân.
3. **State (Trạng thái)**: Tình trạng hiện tại của môi trường. Tác nhân quan sát trạng thái này để đưa ra quyết định.
4. **Action (Hành động)**: Các hành động mà tác nhân có thể thực hiện.
5. **Reward (Phần thưởng)**: Phản hồi từ môi trường sau mỗi hành động. Mục tiêu của tác nhân là tối đa hóa phần thưởng tổng cộng qua thời gian.
### Quy trình hoạt động của RL

1. **Quan sát**: Agent quan sát trạng thái hiện tại của môi trường.
2. **Hành động**: Dựa trên trạng thái quan sát, agent chọn một hành động để thực hiện.
3. **Phản hồi**: Sau khi thực hiện hành động, môi trường cung cấp trạng thái mới và phần thưởng cho agent.
4. **Cập nhật**: Agent cập nhật chiến lược của mình dựa trên phần thưởng nhận được.
### Các thuật toán phổ biến trong RL

1. **Q-Learning**: Là một thuật toán học không theo chính sách, trong đó agent học giá trị của các cặp trạng thái-hành động.
2. **Deep Q-Network (DQN)**: Sử dụng mạng nơ-ron để xấp xỉ giá trị Q trong Q-Learning.
3. **Policy Gradient**: Học trực tiếp chiến lược (policy) thay vì giá trị Q, tối ưu hóa chiến lược để tối đa hóa phần thưởng.
4. **Actor-Critic**: Kết hợp cả hai phương pháp giá trị (value-based) và chính sách (policy-based).
### Ứng dụng của RL

- Chơi game (ví dụ: AlphaGo, Dota 2 AI)
- Robot học cách di chuyển và tương tác với môi trường
- Quản lý tài chính và giao dịch tự động
- Tối ưu hóa các hệ thống phức tạp, như mạng lưới cung cấp năng lượng
- 
Để minh họa cách Reinforcement Learning hoạt động, hãy xem xét một ví dụ cụ thể về việc huấn luyện một con robot để tìm đường ra khỏi một mê cung.
### Bài toán: Robot Tìm Đường Ra Khỏi Mê Cung

#### Môi trường

- Mê cung là một lưới ô vuông, trong đó mỗi ô có thể là trống, có chứa chướng ngại vật, hoặc là điểm đích.
#### Agent (Robot)

- Robot bắt đầu từ một vị trí ban đầu trong mê cung và cố gắng tìm đường đến điểm đích.
#### Trạng thái (State)

- Vị trí hiện tại của robot trong mê cung.
#### Hành động (Action)

- Robot có thể di chuyển lên, xuống, trái, hoặc phải.
#### Phần thưởng (Reward)

- Mỗi bước đi trừ đi 1 điểm.
- Nếu robot chạm vào chướng ngại vật, nó mất 10 điểm.
- Nếu robot đến được điểm đích, nó nhận được 100 điểm.

### Quy Trình Huấn Luyện

1. **Khởi tạo**: Robot bắt đầu ở một vị trí ngẫu nhiên trong mê cung.
    
2. **Quan sát**: Robot quan sát trạng thái hiện tại (vị trí của nó trong mê cung).
    
3. **Hành động**: Robot chọn một hành động dựa trên chiến lược hiện tại (ví dụ: di chuyển lên, xuống, trái, hoặc phải).
    
4. **Phản hồi**: Môi trường cập nhật trạng thái mới dựa trên hành động của robot và cung cấp phần thưởng tương ứng.
    
5. **Cập nhật**: Robot cập nhật chiến lược của mình dựa trên phần thưởng nhận được. Quá trình này lặp lại cho đến khi robot học được chiến lược tối ưu để thoát khỏi mê cung.
	[Video minh hoạ](https://www.youtube.com/watch?v=L_4BPjLBF4E)
### Ví Dụ Cụ Thể: Q-Learning

Giả sử chúng ta sử dụng thuật toán Q-Learning để huấn luyện robot.

1. **Bảng Q (Q-Table)**: Một bảng để lưu trữ giá trị Q cho mỗi cặp trạng thái-hành động.
    
    - Các hàng của bảng Q là các trạng thái (vị trí trong mê cung).
    - Các cột của bảng Q là các hành động (di chuyển lên, xuống, trái, phải).
2. **Khởi tạo Bảng Q**: Khởi tạo giá trị Q của tất cả các cặp trạng thái-hành động với một giá trị nhỏ ngẫu nhiên.
    
3. **Chọn Hành Động**: Chọn hành động dựa trên chính sách ε-greedy (ε là một giá trị nhỏ cho phép robot thỉnh thoảng chọn hành động ngẫu nhiên để thám hiểm).
    
4. **Cập Nhật Bảng Q**:
    
    - Thực hiện hành động và quan sát trạng thái mới và phần thưởng.
    - Cập nhật giá trị Q dựa trên công thức: $Q(s,a)←Q(s,a)+α[r+γmax⁡a′Q(s′,a′)−Q(s,a)]Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma \max_{a'} Q(s', a') - Q(s, a)]Q(s,a)←Q(s,a)+α[r+γa′max​Q(s′,a′)−Q(s,a)]$
        - sss: Trạng thái hiện tại
        - aaa: Hành động đã chọn
        - rrr: Phần thưởng nhận được
        - s′s's′: Trạng thái mới
        - a′a'a′: Hành động tiếp theo
        - α\alphaα: Tốc độ học
        - γ\gammaγ: Hệ số chiết khấu
5. **Lặp Lại**: Lặp lại quá trình trên cho đến khi giá trị Q của các cặp trạng thái-hành động hội tụ.
    
### Kết Quả

Sau khi huấn luyện đủ lâu, robot sẽ học được chiến lược tối ưu để thoát khỏi mê cung bằng cách tối đa hóa phần thưởng tổng cộng nhận được. Robot sẽ biết cách tránh chướng ngại vật và tìm đường ngắn nhất đến điểm đích.
### Ứng Dụng Thực Tế

- **AlphaGo**: Sử dụng Deep Q-Networks (DQN) để học cách chơi cờ vây và đánh bại các nhà vô địch thế giới.
- **Robotics**: Robot học cách di chuyển trong không gian thực tế mà không va chạm vào chướng ngại vật.
- **Tối Ưu Hóa Giao Thông**: Hệ thống giao thông thông minh học cách điều chỉnh đèn giao thông để giảm tắc nghẽn.