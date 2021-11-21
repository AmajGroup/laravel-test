
Project Structure :

1- Create a Laravel project with a version upper than 8 .

2- Dockerize project without using Laravel Sail .

Use these containers :

***- PHP-FPM**

***- MySQL**

***- NginX**

3- Create a module with the name of **Policy**. ( Don’t use packages for modularizing project )

* This module should include all of needed files and folders. ( Models, Migration, Factory, Seeder , … )

4- Create a model &  migration considering these fields :

**- title ( String field )  ( Max 80 Characters, Min 8 Characters ) ( Required )**

**- date_uploaded ( Timestamp field ) ( Required )**

**- acknowledgement_required ( Values of this field could be Yes or No )**

**- file ( This is the path that file is saved ) ( JPG, PNG, PDF )**

**- file_type ( String )**

**- is_trashed ( Yes / No )**

*** Use best optimized field types for each one of them .**

*** Use SoftDelete as well.**

5- Create a Global Scope that returns records which ( is_trashed is Yes )

Webservices :

**1-  Index & Search**

**Description**: It is responsible for indexing also searching policies .

( Consider returning policies that are not deleted, with is_trashed = No )

**Method**: GET

**Url** : api/v1/policies/

**Response**: returns a collection of policies .

**Parameters** :

**q**: use this parameter to search through policies using their title,

If this field was null Just return all the policies

**Tests ( Feature ) :**

1- test that this webservice returns paginated records.

----------------------------------------------------------------------------------------------------------------------------------------

**2- Store :**

**Description** :  It is responsible for creating a Policy.

**Method** : POST

**Url** : api/v1/policies

**Response**: returns the created item with proper response format.

**Parameters**:

**- title**

**- acknowledgement_required**

**- file**

**Tests ( Feature ) :**

1- test that with a correct request body ( parameters ) this webservice works fine.

----------------------------------------------------------------------------------------------------------------------------------------

**3- Trash:**

**Description**:

It is responsible for trashing a policy, means setting is_trashed field to Yes.

**Method**: GET

**Url** : api/v1/policies/{policy_id}/trash

**Response** : returns the result ( success or false, with proper message )

**Tests ( Feature ) :**

1- test that this webservice can successfully trash a non_trashed policy .

----------------------------------------------------------------------------------------------------------------------------------------

**4- Delete**

**Description**: It is responsible for deleting a policy .

**Method**: DELETE

**URL** : api/v1/policies/{policy_id}

**Response**:

returns the result ( success or false, with proper message )

**Tests ( Feature ) :**

1- test that this webservice can successfully delete a  policy .

Notes :

* A policy first get trashed then get’s deleted.

* Use best practices that you know .

* Commit each task with proper message.

Fork this repository : https://github.com/AmajGroup/laravel-test

* Use validation, …

* Use proper formats for returning responses.

* Any question about the tasks, just Ask.
