3 things learned from using technology:
1. What do Django database backend do? (django.db.backends.postgresql , django.db.backends.mysql. ) 
	Consistent API for executing query despite the rdbms, optimization for executing query , database agnostic, migration and schema. it is available for several rdbms such as   postgresql , mysql , etc. Responsible for managing. connection and transaction such as when to close the connection and closing unused connection and re-using opened connection to the database. 
	
2. Thread and database connection in Django. 
	Because each thread maintains its own connection, your database must support at least as many simultaneous connections as you have worker threads.

3. Application in Django
	 As far as I know, For any given Django project ,  number of threads are at least as much as number of application in it. But in development server , new thread is created in each request , therefore creating new connection to the database. 

Django thread ашигласан байна. Ингэх нь мэдээж олон хэрэглэгчид зэрэг үйлчлэх боломжийг гаргаж өгнө. Мөн thread үүсгэж байгаа юм чинь буцааж хураах ёстой гэх мэт. Олон хэрэглэгчийг хэрхэн handle хийж байна вэ гэдэг нь тухайн framework-н ялгаа гарч ирж байна. 

Бааз дээрээ хичнээн зэрэг хандалт зөвшөөрөхийг зааж өгч болно. Үүнийг серверийнхээ түвшинд зааж өгөх үү эсвэл баазынхаа түвшинд зааж өгдөг үү?  Энэ өгүүлбэрийн утга нь thread бүр баазтай холбогдож чадах учираас backend нь хичнээн thread үүсгэж чадаж байна тэр хэмжээгээр бааз дээрээ хичнээн холболт зэрэг зөвшөөрч чадах тохиргоог хийх хэрэгтэй. Тэгэхдээ зарим thread нь бааз биш cache ашиглах бас боломжтой. 




