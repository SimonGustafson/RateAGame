F�r att testk�ra hemsidan med alla dess funktioner beh�vs f�ljande program (steg 1-5)

0."sys.war" fr�n RateAGames Github
1. eclipse (https://www.eclipse.org/downloads/packages/release/2019-03/r/eclipse-ide-enterprise-java-developers)
2. tomcat (https://tomcat.apache.org/download-90.cgi)
3. postgresql (s�tt l�senord till "password" under installationen f�r att st�mma �verrens med koden, port default (5432)) (https://www.postgresql.org/download/)
4. postgresql jar, version PostgreSQL JDBC 4.2 Driver, 42.2.5, (https://jdbc.postgresql.org/download.html)
5. pgadmin 4 (https://www.pgadmin.org/download/) 
____________________________________________________________________________________
6. Packa upp tomcat-filen och placera postgresql jar (fr�n steg 4, inte 3) i mappen "lib"
7. Starta eclipse tryck p� "File" och sedan "Import", s�k efter "war" och tryck p� Next. Under War-file, tryck p� browse och hitta 
"sys.war", som finns p� RateAGames GitHub. Tryck p� V�lj Fil och sedan p� Finish
8. H�gerklicka p� det nu importerade projektet vid v�nster sida av eclipse och v�lj "Properties" l�ngst ner.
9. Hitta "Targeted Runtimes" och v�lj "New" -> Apache Tomcat v.9.0 -> Browse -> hitta och v�lj tomcat-mappen och tryck p� OK. 
10. H�gerklicka p� projektet och tryck p� "Build Path" -> "Configure Build Path" -> Add external JARS (h�ger sida)
11. Leta upp PostgreSQL JAR-filen och v�lj, tryck sedan p� apply and close
12. H�gerklicka p� projektet igen och tryck p� Configure -> Convert to Maven Project, tryck p� Finish p� rutan som kommer upp
Projektet �r nu redo att k�ras
13. Initialisera databasen: g� in i java resources -> src/java -> �ppna "sys" -> h�gerklicka p� DatabaseConnection och tryck p� "run as application"
14. H�gerklicka p� projektet och tryck p� "Run As" -> "Run on server", v�lj Tomcat v.9.0
15. G� in i valfri browser och skriv in "localhost:8080/sys/"
16. F�r att st�nga ner servern, tryck p� r�da kvadraten nere till h�ger i eclipse.

Ibland kan det beh�vs extra konfigurering i pgAdmin4 f�r att se v�rdena i databasen, om databasen inte kommer upp automatiskt n�r PgAdmin4 startas,
g�r f�ljande:
1. Starta PgAdmin4
2. Tryck p� Servers till v�nster
3. Om det inte finns n�got, g� till dashboard, tryck p� add server, l�gg till f�ljande:
4. Skriv "PostgreSQL 11" under "Name".
5. Under Connection-fliken skriv f�ljande v�rden
Host name/address: localhost
Port: 5432
Maintenance database: postgres
Username: postgres
Port: 5432
6. Spara

Om du redan har en postgres-databas och kan uppgifterna till denna, s� m�ste du �ndra detta i Java-filen "DatabaseLogin", i Eclipse.

Om n�got gick fel under n�got steg, kontakta RateAGame s� hj�lper vi till.