# CIS567-integrated-lab-1
Grade Scores averages and more for integrated lab
HOMEWORK_MAX = 800.0
QUIZZES_MAX = 400.0
MIDTERM_MAX = 150.0
FINAL_MAX = 200.0

status = input()
if status != "UG" and status != "G" and status != "DL":
    print("Error: student status must be UG, G or DL")
    exit()

inputs = input().split()
homework_points = float(inputs[0])
quiz_points = float(inputs[1])
midterm_points = float(inputs[2])
final_points = float(inputs[3])

homework_avg = (homework_points / HOMEWORK_MAX) * 100
quiz_avg = (quiz_points / QUIZZES_MAX) * 100
midterm_avg = (midterm_points / MIDTERM_MAX) * 100
final_avg = (final_points / FINAL_MAX) * 100

# Step 2
if homework_avg > 100:
    homework_avg = 100.0
if quiz_avg > 100:
    quiz_avg = 100.0
if midterm_avg > 100:
    midterm_avg = 100.0
if final_avg > 100:
    final_avg = 100.0

# Step 3 
if status == "UG":
    course_average = (
        homework_avg * 0.20
        + quiz_avg * 0.20
        + midterm_avg * 0.30
        + final_avg * 0.30
    )
elif status == "G":
    course_average = (
        homework_avg * 0.15
        + quiz_avg * 0.05
        + midterm_avg * 0.35
        + final_avg * 0.45
    )
else:  
    course_average = (
        homework_avg * 0.05
        + quiz_avg * 0.05
        + midterm_avg * 0.40
        + final_avg * 0.50
    )


print("Homework: {:.1f}%".format(homework_avg))
print("Quizzes: {:.1f}%".format(quiz_avg))
print("Midterm: {:.1f}%".format(midterm_avg))
print("Final Exam: {:.1f}%".format(final_avg))
print(f"{status} average: {course_average:.1f}%")

# Step 4: 
if course_average >= 90.0:
    letter_grade = "A"
elif course_average >= 80.0:
    letter_grade = "B"
elif course_average >= 70.0:
    letter_grade = "C"
elif course_average >= 60.0:
    letter_grade = "D"
else:
    letter_grade = "F"

print(f"Course grade: {letter_grade}")



