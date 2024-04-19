class Array:
    def __init__(self, size):
        self.size = size
        self.array = [None] * size

    def traverse(self):
        for i in range(self.size):
            print(self.array[i], end=' ')
        print()

    def insert(self, index, value):
        if index < 0 or index >= self.size:
            print("Index out of bounds")
            return
        self.array[index] = value

    def delete(self, index):
        if index < 0 or index >= self.size:
            print("Index out of bounds")
            return
        self.array[index] = None

    def update(self, index, value):
        if index < 0 or index >= self.size:
            print("Index out of bounds")
            return
        self.array[index] = value

    def bubble_sort(self):
        for i in range(self.size):
            for j in range(0, self.size - i - 1):
                if self.array[j] > self.array[j + 1]:
                    self.array[j], self.array[j + 1] = self.array[j + 1], self.array[j]

# Initialize array size
size = int(input("Enter the size of the array: "))
arr = Array(size)

while True:
    print("\n1. Insert element")
    print("2. Remove element")
    print("3. View array")
    print("4. Exit")

    choice = input("\nEnter your choice: ")

    if choice == '1':
        index = int(input("Enter the index to insert: "))
        value = int(input("Enter the value to insert: "))
        arr.insert(index, value)
    elif choice == '2':
        index = int(input("Enter the index to remove: "))
        arr.delete(index)
    elif choice == '3':
        print("Current Array:")
        arr.traverse()
    elif choice == '4':
        break
    else:
        print("Invalid choice. Please try again.")
