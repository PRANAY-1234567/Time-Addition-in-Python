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