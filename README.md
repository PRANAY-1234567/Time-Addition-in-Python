# ⏰ Time Addition in Python (OOP)

## 📌 Description

This program demonstrates how to **add two time objects** using a class. It correctly handles overflow:

* Seconds → Minutes
* Minutes → Hours

---

## 🚀 Features

* `Time` class with hours, minutes, seconds
* Formatted display (`HH : MM : SS`)
* Accurate time addition with carry handling
* Returns a new object as result

---

## 🛠️ How It Works

1. Two objects are created:

   * `t1 = 10:25:45`
   * `t2 = 09:38:30`

2. Method `addition(x)`:

   * Adds seconds and converts extra into minutes
   * Adds minutes and converts extra into hours
   * Adds hours

3. Result is stored in `t3`

---

## 💻 Code

```python id="r4k9xp"
class Time:
    def __init__(self, hrs=0, min=0, sec=0):
        self.hrs = hrs
        self.min = min
        self.sec = sec

    def display(self):
        print(f"{self.hrs:02d} : {self.min:02d} : {self.sec:02d}")

    def addition(self, x):
        r = Time()

        # Add seconds
        r.sec = self.sec + x.sec
        r.min = r.sec // 60
        r.sec = r.sec % 60

        # Add minutes
        r.min = r.min + self.min + x.min
        r.hrs = r.min // 60
        r.min = r.min % 60

        # Add hours
        r.hrs = r.hrs + self.hrs + x.hrs

        return r


# Main program
t1 = Time(10, 25, 45)
t2 = Time(9, 38, 30)

t3 = t1.addition(t2)

t1.display()
t2.display()
t3.display()
```

---

## ▶️ Output

```id="m7q2zn"
10 : 25 : 45
09 : 38 : 30
20 : 04 : 15
```

---

## 🧠 Key Concept

* Objects can be **passed as arguments**
* Methods can **return objects**
* Carry logic:

  * `sec // 60` → convert to minutes
  * `min // 60` → convert to hours

---

## ⚠️ Improvement (Cleaner Logic)

Your logic works, but here’s a cleaner approach using total seconds:

```python id="p8x1sd"
def addition(self, x):
    total_sec = (self.hrs*3600 + self.min*60 + self.sec) + \
                (x.hrs*3600 + x.min*60 + x.sec)

    hrs = total_sec // 3600
    total_sec %= 3600
    min = total_sec // 60
    sec = total_sec % 60

    return Time(hrs, min, sec)
```

👉 Easier to understand and less error-prone.

---

## 📚 Concepts Used

* Class & Object
* Object as argument
* Returning object
* Arithmetic + carry handling

---

## 🎯 Use Case

* Time calculations
* Digital clock logic
* Embedded systems (timers, RTC concepts 👀 useful for your branch)

---

## 🔧 Future Improvements

* Add subtraction
* Validate input (sec < 60, min < 60)
* Add operator overloading (`+`)
* Build stopwatch/timer app

---

## 📄 License

Open-source and free to use.

<img width="744" height="698" alt="image" src="https://github.com/user-attachments/assets/87e3ce9c-b262-4571-98bb-4fb8d8f24007" />
