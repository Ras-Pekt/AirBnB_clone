## 0x00. AirBnB clone - The console
<img src="https://is5-ssl.mzstatic.com/image/thumb/Purple123/v4/fd/ac/b4/fdacb4f9-4c73-1ca6-5595-ef18f821ee62/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/246x0w.png">
<img src="https://image.shutterstock.com/image-illustration/clone-icon-illustration-creative-sign-260nw-1497218057.jpg">

# 0x00 AirBnB clone - The console

In this directory you will find a implementation of a AirBnB clone.
This first step involves the implementation of the Console. Commands included in the console for the management of the various objects are;
- create - creates a new instance
- show - prints the string representation of an instance
- destroy - deletes an instance
- all - prints all string representation of all instances
- update - updates an instance

### The console ###
* create your data model
* manage (create, update, destroy, etc) objects via a console / command interpreter
* store and persist objects to a file (JSON file)

### Command interpreter ###

Our command interpreter looks like a mini shell and allow us manage the objects of our project:

* Create a new object (ex: a new User or a new Place)
* Retrieve an object from a file, a database etc…
* Do operations on objects (count, compute stats, etc…)
* Update attributes of an object
* Destroy an object

### Objectives of project ###

* How to create a Python package
* How to create a command interpreter in Python using the cmd module
* What is Unit testing and how to implement it in a large project
* How to serialize and deserialize a Class
* How to write and read a JSON file
* How to manage datetime
* What is an UUID
* What is *args and how to use it
* What is **kwargs and how to use it
* How to handle named arguments in a function

### Content of Directory ###
* Models Folder: Classes of the project. BaseModel is the parent Class. The other classes (amenity, city, place, review, state, user) inherit from BaseModel and specify others attributes for itselfs.
* Tests Folder : Unittests for the project
* AUTHORS: Information about the authors
* console.py: Executable file for the console
* file.json: JSON file with all information of instances

---


## Examples of Usage

### Execution ###
```
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
```
### create ###
Create an instance and show us the id number
```
$ ./console.py 
(hbnb) create BaseModel
e37cf8df-351a-4df6-9d15-fd9331a5bfb2
(hbnb) 
```

### Show ###
Show the Class, object if the id is especified and its attributes
```
(hbnb) show BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2
[BaseModel] (e37cf8df-351a-4df6-9d15-fd9331a5bfb2) {'id': 'e37cf8df-351a-4df6-9d15-fd9331a5bfb2', 'created_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695895), 'updated_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695945)}
(hbnb) 
```
### all ###
shows all the instances
```
(hbnb) all BaseModel
["[BaseModel] (5c8ebd08-a708-4823-b9a2-29d58b87c063) {'id': '5c8ebd08-a708-4823-b9a2-29d58b87c063', 'created_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 926171), 'updated_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 926179)}", "[BaseModel] (e576e179-8bb6-4229-a8be-90585b0c1d01) {'id': 'e576e179-8bb6-4229-a8be-90585b0c1d01', 'created_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 896687), 'updated_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 896706)}", "[BaseModel] (0763761f-4534-4a02-8097-79a4ab935ecb) {'id': '0763761f-4534-4a02-8097-79a4ab935ecb', 'created_at': datetime.datetime(2020, 7, 1, 4, 8, 48, 451468), 'updated_at': datetime.datetime(2020, 7, 1, 4, 8, 48, 451881)}", "[BaseModel] (f794d1ba-6688-42b8-ae08-0b307125643a) {'id': 'f794d1ba-6688-42b8-ae08-0b307125643a', 'created_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 922410), 'updated_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 923071)}", "[BaseModel] (ef9b217c-b58c-4d5f-b797-0dbbed80dedd) {'id': 'ef9b217c-b58c-4d5f-b797-0dbbed80dedd', 'created_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 930489), 'updated_at': datetime.datetime(2020, 7, 1, 5, 4, 54, 930504)}", "[BaseModel] (e37cf8df-351a-4df6-9d15-fd9331a5bfb2) {'id': 'e37cf8df-351a-4df6-9d15-fd9331a5bfb2', 'created_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695895), 'updated_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695945)}", "[BaseModel] (82f3d1a2-c28d-4327-be5f-0bceb29b0eb9) {'id': '82f3d1a2-c28d-4327-be5f-0bceb29b0eb9', 'created_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 888932), 'updated_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 889340)}", "[BaseModel] (e029daa8-9083-4097-b2bd-a66fe4895532) {'id': 'e029daa8-9083-4097-b2bd-a66fe4895532', 'created_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 892554), 'updated_at': datetime.datetime(2020, 7, 1, 5, 5, 38, 892561)}"]
(hbnb) 
```
### update ###
update an instance
```
(hbnb) show BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2
[BaseModel] (e37cf8df-351a-4df6-9d15-fd9331a5bfb2) {'id': 'e37cf8df-351a-4df6-9d15-fd9331a5bfb2', 'created_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695895), 'updated_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695945)}
(hbnb) update BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2 first_name "CharlieMeco"
(hbnb) show BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2
[BaseModel] (e37cf8df-351a-4df6-9d15-fd9331a5bfb2) {'first_name': '"CharlieMeco"', 'id': 'e37cf8df-351a-4df6-9d15-fd9331a5bfb2', 'created_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695895), 'updated_at': datetime.datetime(2020, 7, 1, 18, 50, 15, 695945)}
(hbnb) 
```
### Destroy ###
Delete an instance
```
(hbnb) destroy BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2
(hbnb) show BaseModel e37cf8df-351a-4df6-9d15-fd9331a5bfb2
** no instance found **
(hbnb) 
```
---

## Installation

* Clone the repository.
* Open the /AirBnB_clone directory and execute console.py

### Setup

* You need Python interpreter.

---

## Resources

<a href=https://elgibbor.hashnode.dev/airbnb-clone-building-the-console-part-1-introduction>`article`</a><br>
<a href=http://pymotw.com/3/cmd>`cmd module`</a><br>

---


## Support

Feel free to contact us!

- GitHub at <a href="https://github.com/ven8462">`Lavender`</a>
- GitHub at <a href="https://github.com/Ras-Pekt">`Gituku`</a>
---

## License

Free Source Code
