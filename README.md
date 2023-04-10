# Penggajian_Desmita

class Employee:
    def __init__(self, name, salary, grade, num_children, married):
        # Constructor untuk class Employee
        # Inisialisasi atribut name, salary, grade, num_children, dan married
        self.name = name
        self.salary = salary
        self.grade = grade
        self.num_children = num_children
        self.married = married

    def get_salary(self):
        # Method untuk menghitung total gaji karyawan

        # Hitung tunjangan golongan
        if self.grade == 1:
            allowance_grade = 0.05 * self.salary
        elif self.grade == 2:
            allowance_grade = 0.1 * self.salary
        elif self.grade == 3:
            allowance_grade = 0.15 * self.salary
        elif self.grade == 4:
            allowance_grade = 0.2 * self.salary
        else:
            allowance_grade = 0

        # Hitung tunjangan anak
        if self.num_children > 0:
            allowance_children = 0.02 * self.salary * self.num_children
        else:
            allowance_children = 0

        # Hitung tunjangan istri
        if self.married:
            allowance_spouse = 0.1 * self.salary
        else:
            allowance_spouse = 0

        # Hitung total gaji sebelum pajak
        total_salary = self.salary + allowance_grade + allowance_children + allowance_spouse

        # Hitung pajak
        if total_salary <= 5000000:
            tax = 0.05 * total_salary
        elif total_salary <= 10000000:
            tax = 0.1 * total_salary
        else:
            tax = 0.15 * total_salary

        # Hitung bonus
        if self.grade == 3 and self.num_children >= 3:
            bonus = 500000
        elif self.grade == 4 and self.num_children >= 2:
            bonus = 750000
        else:
            bonus = 0

        # Hitung total gaji setelah pajak dan bonus
        total_salary = total_salary - tax + bonus
        return total_salary

# Main program
# Minta user memasukkan data karyawan
name = input("Masukkan nama karyawan: ")
salary = int(input("Masukkan gaji karyawan: "))
grade = int(input("Masukkan golongan karyawan (1-4): "))
married = input("Apakah karyawan sudah menikah? (y/n): ").lower() == 'y'
num_children = int(input("Masukkan jumlah anak karyawan: "))


# Buat objek Employee
employee = Employee(name, salary, grade, num_children, married)

# Tampilkan total gaji karyawan
print("Total gaji karyawan:", employee.get_salary())

'''Pada program di atas, terdapat class Employee yang memiliki atribut name, salary, grade, num_children, dan married.
Atribut ini diinisialisasi melalui constructor __init__.
Class Employee juga memiliki method get_salary untuk menghitung total gaji karyawan.
Pada bagian yang ditandai dengan #-->, kita diminta untuk menambahkan minimal 2 item golongan (grade) dan 2 tingkatan bonus.
Saya menambahkan 2 item golongan baru yaitu grade 3 dan grade 4, serta menambahkan 2 tingkatan bonus yaitu bonus

'''

