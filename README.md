# Python-og-Pyret-funksjoner-student-gruppe
Funksjoner til oppgave 1 b, Oblig 3
# definere funksjon for å lage student
def lag_student(navn, student_id):
    return [navn, student_id]

# definere funksjon for å lage gruppe
def lag_gruppe(gruppe_navn):
    return [gruppe_navn, []]  # gruppe med navn og en tom liste for studenter

# Funksjon for å legge til student i gruppe
def legge_til_student(gruppe, student):
    gruppe[1].append(student)

# Funksjon for å finne ut hvilken gruppe en student tilhører
def finn_gruppe(student, grupper):
    for gruppe in grupper:
        if student in gruppe[1]:  # Sjekker studentlisten i gruppen
            return gruppe[0]  # returnerer gruppenavnet
    return None  # Returnerer None hvis studenten ikke finnes i noen gruppe

# Mock data
student1 = lag_student("Frida", "student1")
student2 = lag_student("Lisa", "student2")
student3 = lag_student("Lars", "student3")

gruppe1 = lag_gruppe("gruppe1")
gruppe2 = lag_gruppe("gruppe2")

legge_til_student(gruppe1, student1)
legge_til_student(gruppe2, student2)
legge_til_student(gruppe1, student3)

grupper = [gruppe1, gruppe2]

# Tester funksjon
resultat = finn_gruppe(student1, grupper)
print(f"{student1[0]} tilhører {resultat}")
