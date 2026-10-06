# dtd_ithub
# Выполнение задания: Валидация XML через DTD

## 1. Содержимое файла `timetable.dtd`
```xml
<!ELEMENT timeTable (complexes, lessons)>
<!ELEMENT complexes (complex+)>
<!ELEMENT lessons (lesson+)>

<!ELEMENT complex (name, address)>
<!ATTLIST complex 
    code ID #REQUIRED>

<!ELEMENT name (#PCDATA)>
<!ELEMENT address (#PCDATA)>

<!ELEMENT lesson (date, time)>
<!ATTLIST lesson 
    no CDATA #REQUIRED
    complex IDREF #REQUIRED>

<!ELEMENT date (#PCDATA)>
<!ELEMENT time (#PCDATA)>
```

## 2. Содержимое XML-документа (`timetable.xml`)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE timeTable SYSTEM "timetable.dtd">

<timeTable>
    <complexes>
        <complex code="c_main">
            <name>Главный корпус</name>
            <address>ул. Университетская, д. 10</address>
        </complex>
        <complex code="c_sport">
            <name>Спортивный комплекс</name>
            <address>ул. Физкультурников, д. 5</address>
        </complex>
    </complexes>

    <lessons>
        <lesson no="1" complex="c_main">
            <date>2026-10-07</date>
            <time>09:00</time>
        </lesson>
        <lesson no="2" complex="c_sport">
            <date>2026-10-07</date>
            <time>10:45</time>
        </lesson>
    </lessons>
</timeTable>
```

