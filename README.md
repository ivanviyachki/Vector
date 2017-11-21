# Vector
Homework


#include<iostream>
using namespace std;
	
class VectorError{};

class Vector {

	int capacity_;
	int size_;
	int* buffer_;

	
public:

	Vector(int capacity)
	: capacity_(capacity),size_(0),buffer_(new int[capacity])
	{}
	
	Vector(const Vector& other)
	: capacity_(other.capacity_), size_(other.size_), buffer_(new int[capacity_])
	{}
	
	~Vector()
	{
		delete [] buffer_;
	}
	
	int size() const
	{
			return size_;
	}

	bool empty() const
	{
		return size_ == 0;
	}
	
	int& operator[](int n)
	{	
		if(n>=0 && n<size_) return buffer_[n];
		throw VectorError();
	}
	
	const int& operator[](int n) const
	{
		if(n>=0 && n<size_) return buffer_[n];
		throw VectorError();
	}
	
	void clear()
	{
	 	size_ = 0;
	}
	
	int capacity() const
	{
			return capacity_;
	}
	
	int& front()
	{
		if(empty()) throw VectorError();
		else return buffer_[0];
	}
	
	const int& front() const
	{
		if(empty()) throw VectorError();
		else return buffer_[0];
	}
	
	int& back()
	{
		if(empty()) throw VectorError();
		else return buffer_[size_ - 1];
	}
	
	const	int& back() const
 	{
		if(empty()) throw VectorError();
		else return buffer_[size_ - 1];
	}
	
	void push_back(const int& value)
	{
		int last_element_index = size_-1;
		buffer_[++last_element_index] = value; // buffer_[size_] = value;
		size_++;
	}
	
	void pop_back()
	{
		if(empty()) throw VectorError();
		else size_--;
	}
	
};


int main(){
	
	
}
