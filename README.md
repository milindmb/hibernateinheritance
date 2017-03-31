# hibernateinheritance
Representing inheritance of objects in database schema is always challange. Mapping java object hierarchy to tables in database requires separate tables to be created for each type of object, managing foreign key references to base object type etc.

Spring & Hibernate allows to map the objec hierarchy in single database table using @Inheritance annotation.

The project is  an example implementation of mapping directory contents ( files + folders) using sigle table but having separate Entity classes of DocumentContent and FolderContent. 

ContentNode ( the base object) is define as abstract class and carries @DiscriminatorColumn annotation which defines table column used to differentiate the extended types ( DocumentNode OR DirectoryNode). Extended classes has annotation @DiscriminatorValue which defined the value of @DiscriminatorColumn column for each type e.g. for DocumentNode @DiscriminatorValue has value="DOCUMENT" and DirectoryNode has @DiscriminatorValue as "Directory" 

Contents of directory ( Files/Folders) are again represented in same table with OneToMany and JoinTable annotation for the Set.




