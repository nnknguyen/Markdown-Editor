```cpp
void enqueue(const T& data) {
    if (used_ == capacity_) {
        grow();
    }
    array_[back_] = data;
    back_= (back_ + 1) % capacity_;
    used_++;
}
void dequeue() {
    if (used_ > 0) {
        used_--;
        front_= front_ == capacity_-1 ? 0: front_+ 1;
    }
}
```
