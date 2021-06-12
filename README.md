# Json and tabbed text to sql inserts converter

### Info
Pure javascript without any libraries.

### Demo
https://jurip0.github.io/json-and-tabbedtext-to-sql/

### Limitations

1. Parses only below json format
```
{ "TABLENAME" : [ TABLEOBJECTS ] }
```
2. Tabbed text input first line must be headers

### Examples
#### Inputs

>Json Input
```
{
            "User": [
                {
                    "id": 123,
                    "name": "name1",
                    "date": "2021-01-01"

                },
                {
                    "id": 321,
                    "name": "name2",
                    "date": "2021-01-01"

                }

            ],
            "User2": [
                {
                    "id": 3213,
                    "name": "name3"

                },
                {
                    "id": 32131,
                    "name": "name4"

                }

            ]

        }
```

> Tabbed text input
```
Id	User	Date
100	User1	2020-05-07 09:45:31.477
101	User2	2020-05-07 12:21:50.633
102	User3	2020-05-07 12:27:11.163`
```

#### Outputs

>From json output
```
CREATE #User (id INT,name TEXT,date DATETIME2);
INSERT INTO User (id,name,date) VALUES (123,'username1','2021-01-01');
INSERT INTO User (id,name,date) VALUES (321,'username2','2021-01-01');
```
>From tabbed text output
```
INSERT INTO [TABLENAME] (Id,User,Date) VALUES ('100','User1','2020-05-07 09:45:31.477');
```
