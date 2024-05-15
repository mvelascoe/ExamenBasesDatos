

# EXAMEN BASES DE DATOS

#### Integrantes:

- Edwing Duvan Hernández Herrera
- Maritza Velasco Esteban

```sql
DELIMITER $$
DROP PROCEDURE IF EXISTS migracion $$
DELIMITER $$
CREATE PROCEDURE migracion()
BEGIN
INSERT INTO film_text (film_id, title, description)
SELECT id_pelicula, titulo, descripcion FROM pelicula;
END $$
DELIMITER ;
```

Obtener los nombres de todos los actores y las películas en las
que han actuado.

```sql
SELECT a.nombre, f.title
FROM actor AS a
INNER JOIN pelicula_actor AS pa ON a.id_actor = pa.id_actor
INNER JOIN pelicula AS p ON pa.id_pelicula = p.id_pelicula
INNER JOIN film_text AS f ON p.id_pelicula = f.film_id;

+-------------+-----------------------------+
| nombre      | title                       |
+-------------+-----------------------------+
| PENELOPE    | ACADEMY DINOSAUR            |
| CHRISTIAN   | ACADEMY DINOSAUR            |
| LUCILLE     | ACADEMY DINOSAUR            |
| SANDRA      | ACADEMY DINOSAUR            |
| JOHNNY      | ACADEMY DINOSAUR            |
| MENA        | ACADEMY DINOSAUR            |
| WARREN      | ACADEMY DINOSAUR            |
| OPRAH       | ACADEMY DINOSAUR            |
| ROCK        | ACADEMY DINOSAUR            |
| MARY        | ACADEMY DINOSAUR            |
| BOB         | ACE GOLDFINGER              |
| MINNIE      | ACE GOLDFINGER              |
| SEAN        | ACE GOLDFINGER              |
| CHRIS       | ACE GOLDFINGER              |
| NICK        | ADAPTATION HOLES            |
| BOB         | ADAPTATION HOLES            |
| CAMERON     | ADAPTATION HOLES            |
| RAY         | ADAPTATION HOLES            |
| JULIANNE    | ADAPTATION HOLES            |
| JODIE       | AFFAIR PREJUDICE            |
| SCARLETT    | AFFAIR PREJUDICE            |
| KENNETH     | AFFAIR PREJUDICE            |
| FAY         | AFFAIR PREJUDICE            |
| OPRAH       | AFFAIR PREJUDICE            |
| GARY        | AFRICAN EGG                 |
| DUSTIN      | AFRICAN EGG                 |
| MATTHEW     | AFRICAN EGG                 |
| MATTHEW     | AFRICAN EGG                 |
| THORA       | AFRICAN EGG                 |
| KIRSTEN     | AGENT TRUMAN                |
| SANDRA      | AGENT TRUMAN                |
| JAYNE       | AGENT TRUMAN                |
| WARREN      | AGENT TRUMAN                |
| MORGAN      | AGENT TRUMAN                |
| KENNETH     | AGENT TRUMAN                |
| REESE       | AGENT TRUMAN                |
| JIM         | AIRPLANE SIERRA             |
| RICHARD     | AIRPLANE SIERRA             |
| OPRAH       | AIRPLANE SIERRA             |
| MENA        | AIRPLANE SIERRA             |
| MICHAEL     | AIRPLANE SIERRA             |
| FAY         | AIRPORT POLLOCK             |
| GENE        | AIRPORT POLLOCK             |
| SUSAN       | AIRPORT POLLOCK             |
| LUCILLE     | AIRPORT POLLOCK             |
| CHRISTIAN   | ALABAMA DEVIL               |
| ELVIS       | ALABAMA DEVIL               |
| RIP         | ALABAMA DEVIL               |
| MENA        | ALABAMA DEVIL               |
| RIP         | ALABAMA DEVIL               |
| WARREN      | ALABAMA DEVIL               |
| GRETA       | ALABAMA DEVIL               |
| WILLIAM     | ALABAMA DEVIL               |
| MERYL       | ALABAMA DEVIL               |
| ALEC        | ALADDIN CALENDAR            |
| JUDY        | ALADDIN CALENDAR            |
| VAL         | ALADDIN CALENDAR            |
| RAY         | ALADDIN CALENDAR            |
| RENEE       | ALADDIN CALENDAR            |
| JADA        | ALADDIN CALENDAR            |
| GRETA       | ALADDIN CALENDAR            |
| ROCK        | ALADDIN CALENDAR            |
| JOHNNY      | ALAMO VIDEOTAPE             |
| SCARLETT    | ALAMO VIDEOTAPE             |
| SEAN        | ALAMO VIDEOTAPE             |
| MICHAEL     | ALAMO VIDEOTAPE             |
| VAL         | ALASKA PHANTOM              |
| BURT        | ALASKA PHANTOM              |
| SIDNEY      | ALASKA PHANTOM              |
| SYLVESTER   | ALASKA PHANTOM              |
| ALBERT      | ALASKA PHANTOM              |
| GENE        | ALASKA PHANTOM              |
| JEFF        | ALASKA PHANTOM              |
| CARY        | ALI FOREVER                 |
| CHRISTOPHER | ALI FOREVER                 |
| KENNETH     | ALI FOREVER                 |
| MORGAN      | ALI FOREVER                 |
| JON         | ALI FOREVER                 |
| WOODY       | ALICE FANTASIA              |
| MINNIE      | ALICE FANTASIA              |
| MORGAN      | ALICE FANTASIA              |
| ROCK        | ALICE FANTASIA              |
| BURT        | ALIEN CENTER                |
| KENNETH     | ALIEN CENTER                |
| SIDNEY      | ALIEN CENTER                |
| RENEE       | ALIEN CENTER                |
| HUMPHREY    | ALIEN CENTER                |
| MENA        | ALIEN CENTER                |
| KARL        | ALLEY EVOLUTION             |
| JUDE        | ALLEY EVOLUTION             |
| ALBERT      | ALLEY EVOLUTION             |
| GREGORY     | ALLEY EVOLUTION             |
| JOHN        | ALLEY EVOLUTION             |
| ED          | ALONE TRIP                  |
| KARL        | ALONE TRIP                  |
| UMA         | ALONE TRIP                  |
| WOODY       | ALONE TRIP                  |
| SPENCER     | ALONE TRIP                  |
| CHRIS       | ALONE TRIP                  |
| LAURENCE    | ALONE TRIP                  |
| RENEE       | ALONE TRIP                  |
| REESE       | ALTER VICTORY               |
| JADA        | ALTER VICTORY               |
| ANGELA      | ALTER VICTORY               |
| OPRAH       | ALTER VICTORY               |
| JOHNNY      | AMADEUS HOLY                |
| JULIA       | AMADEUS HOLY                |
| VAL         | AMADEUS HOLY                |
| KIRK        | AMADEUS HOLY                |
| JAMES       | AMADEUS HOLY                |
| PENELOPE    | AMADEUS HOLY                |
| CARMEN      | AMELIE HELLFIGHTERS         |
| WALTER      | AMELIE HELLFIGHTERS         |
| ED          | AMELIE HELLFIGHTERS         |
| EWAN        | AMELIE HELLFIGHTERS         |
| IAN         | AMELIE HELLFIGHTERS         |
| LAURA       | AMELIE HELLFIGHTERS         |
| KEVIN       | AMERICAN CIRCUS             |
| RIP         | AMERICAN CIRCUS             |
| SIDNEY      | AMERICAN CIRCUS             |
| WARREN      | AMERICAN CIRCUS             |
| FRANCES     | AMERICAN CIRCUS             |
| CARY        | AMISTAD MIDSUMMER           |
| DARYL       | AMISTAD MIDSUMMER           |
| SALMA       | AMISTAD MIDSUMMER           |
| SCARLETT    | AMISTAD MIDSUMMER           |
| PENELOPE    | ANACONDA CONFESSIONS        |
| JENNIFER    | ANACONDA CONFESSIONS        |
| ELVIS       | ANACONDA CONFESSIONS        |
| JAYNE       | ANACONDA CONFESSIONS        |
| HUMPHREY    | ANACONDA CONFESSIONS        |
| TOM         | ANALYZE HOOSIERS            |
| TOM         | ANALYZE HOOSIERS            |
| JESSICA     | ANALYZE HOOSIERS            |
| GRETA       | ANALYZE HOOSIERS            |
| ED          | ANALYZE HOOSIERS            |
| PENELOPE    | ANGELS LIFE                 |
| JENNIFER    | ANGELS LIFE                 |
| GRACE       | ANGELS LIFE                 |
| JULIA       | ANGELS LIFE                 |
| CHRISTOPHER | ANGELS LIFE                 |
| ED          | ANGELS LIFE                 |
| NICK        | ANGELS LIFE                 |
| LAURENCE    | ANGELS LIFE                 |
| RENEE       | ANGELS LIFE                 |
| ADAM        | ANNIE IDENTITY              |
| CATE        | ANNIE IDENTITY              |
| GRETA       | ANNIE IDENTITY              |
| GRACE       | ANONYMOUS HUMAN             |
| FAY         | ANONYMOUS HUMAN             |
| JIM         | ANONYMOUS HUMAN             |
| SUSAN       | ANONYMOUS HUMAN             |
| WHOOPI      | ANONYMOUS HUMAN             |
| EMILY       | ANONYMOUS HUMAN             |
| MERYL       | ANONYMOUS HUMAN             |
| MENA        | ANONYMOUS HUMAN             |
| ED          | ANONYMOUS HUMAN             |
| MILLA       | ANTHEM LUKE                 |
| OPRAH       | ANTHEM LUKE                 |
| BETTE       | ANTITRUST TOMATOES          |
| UMA         | ANTITRUST TOMATOES          |
| SIDNEY      | ANTITRUST TOMATOES          |
| SALMA       | ANTITRUST TOMATOES          |
| WILLIAM     | ANTITRUST TOMATOES          |
| RENEE       | ANTITRUST TOMATOES          |
| REESE       | ANTITRUST TOMATOES          |
| JOE         | ANYTHING SAVANNAH           |
| CHRISTOPHER | ANYTHING SAVANNAH           |
| LISA        | ANYTHING SAVANNAH           |
| NICK        | APACHE DIVINE               |
| CUBA        | APACHE DIVINE               |
| ANNE        | APACHE DIVINE               |
| HENRY       | APACHE DIVINE               |
| MAE         | APOCALYPSE FLAMINGOS        |
| VIVIEN      | APOCALYPSE FLAMINGOS        |
| OPRAH       | APOCALYPSE FLAMINGOS        |
| WILL        | APOCALYPSE FLAMINGOS        |
| RUSSELL     | APOCALYPSE FLAMINGOS        |
| MAE         | APOLLO TEEN                 |
| WOODY       | APOLLO TEEN                 |
| ED          | APOLLO TEEN                 |
| ALBERT      | APOLLO TEEN                 |
| OPRAH       | APOLLO TEEN                 |
| MENA        | APOLLO TEEN                 |
| JEFF        | APOLLO TEEN                 |
| DEBBIE      | APOLLO TEEN                 |
| KARL        | ARABIA DOGMA                |
| RIP         | ARABIA DOGMA                |
| JULIA       | ARABIA DOGMA                |
| JOHNNY      | ARABIA DOGMA                |
| JUDE        | ARABIA DOGMA                |
| SEAN        | ARABIA DOGMA                |
| BURT        | ARABIA DOGMA                |
| WALTER      | ARABIA DOGMA                |
| RUSSELL     | ARABIA DOGMA                |
| FRANCES     | ARABIA DOGMA                |
| GRETA       | ARABIA DOGMA                |
| LISA        | ARABIA DOGMA                |
| GRACE       | ARACHNOPHOBIA ROLLERCOASTER |
| JUDY        | ARACHNOPHOBIA ROLLERCOASTER |
| DARYL       | ARACHNOPHOBIA ROLLERCOASTER |
| MORGAN      | ARACHNOPHOBIA ROLLERCOASTER |
| CUBA        | ARACHNOPHOBIA ROLLERCOASTER |
| RITA        | ARACHNOPHOBIA ROLLERCOASTER |
| EWAN        | ARACHNOPHOBIA ROLLERCOASTER |
| HUMPHREY    | ARACHNOPHOBIA ROLLERCOASTER |
| JULIA       | ARGONAUTS TOWN              |
| GARY        | ARGONAUTS TOWN              |
| GENE        | ARGONAUTS TOWN              |
| DAN         | ARGONAUTS TOWN              |
| KEVIN       | ARGONAUTS TOWN              |
| KARL        | ARIZONA BANG                |
| RAY         | ARIZONA BANG                |
| RUSSELL     | ARIZONA BANG                |
| GRETA       | ARIZONA BANG                |
| PARKER      | ARK RIDGEMONT               |
| NICK        | ARK RIDGEMONT               |
| AUDREY      | ARK RIDGEMONT               |
| ANGELA      | ARMAGEDDON LOST             |
| JAMES       | ARMAGEDDON LOST             |
| PENELOPE    | ARMAGEDDON LOST             |
| CUBA        | ARMAGEDDON LOST             |
| KIM         | ARMAGEDDON LOST             |
| GENE        | ARMAGEDDON LOST             |
| GREGORY     | ARMAGEDDON LOST             |
| ED          | ARMY FLINTSTONES            |
| CARY        | ARMY FLINTSTONES            |
| MAE         | ARMY FLINTSTONES            |
| GENE        | ARMY FLINTSTONES            |
| PENELOPE    | ARMY FLINTSTONES            |
| MATTHEW     | ARMY FLINTSTONES            |
| RUSSELL     | ARMY FLINTSTONES            |
| CUBA        | ARSENIC INDEPENDENCE        |
| RITA        | ARSENIC INDEPENDENCE        |
| OPRAH       | ARSENIC INDEPENDENCE        |
| ED          | ARTIST COLDBLOODED          |
| SANDRA      | ARTIST COLDBLOODED          |
| KIRK        | ARTIST COLDBLOODED          |
| JAYNE       | ARTIST COLDBLOODED          |
| SIDNEY      | ARTIST COLDBLOODED          |
| RENEE       | ARTIST COLDBLOODED          |
| MERYL       | ARTIST COLDBLOODED          |
| WOODY       | ATLANTIS CAUSE              |
| AUDREY      | ATLANTIS CAUSE              |
| JULIANNE    | ATLANTIS CAUSE              |
| FRANCES     | ATLANTIS CAUSE              |
| GRETA       | ATLANTIS CAUSE              |
| CATE        | ATLANTIS CAUSE              |
| CHRIS       | ATLANTIS CAUSE              |
| HARVEY      | ATLANTIS CAUSE              |
| CUBA        | ATLANTIS CAUSE              |
| DAN         | ATTACKS HATE                |
| MILLA       | ATTACKS HATE                |
| GROUCHO     | ATTACKS HATE                |
| BURT        | ATTACKS HATE                |
| UMA         | ATTRACTION NEWTON           |
| RIP         | ATTRACTION NEWTON           |
| GARY        | ATTRACTION NEWTON           |
| CHRISTOPHER | ATTRACTION NEWTON           |
| DUSTIN      | AUTUMN CROW                 |
| ANGELA      | AUTUMN CROW                 |
| JAMES       | AUTUMN CROW                 |
| NICK        | BABY HALL                   |
| MATTHEW     | BABY HALL                   |
| CHARLIZE    | BABY HALL                   |
| DARYL       | BABY HALL                   |
| KEVIN       | BABY HALL                   |
| RIVER       | BABY HALL                   |
| MINNIE      | BABY HALL                   |
| VIVIEN      | BABY HALL                   |
| CHRISTIAN   | BACKLASH UNDEFEATED         |
| SPENCER     | BACKLASH UNDEFEATED         |
| CHRISTOPHER | BACKLASH UNDEFEATED         |
| SYLVESTER   | BACKLASH UNDEFEATED         |
| DAN         | BACKLASH UNDEFEATED         |
| KEVIN       | BACKLASH UNDEFEATED         |
| JANE        | BACKLASH UNDEFEATED         |
| BEN         | BADMAN DAWN                 |
| HARRISON    | BADMAN DAWN                 |
| CUBA        | BADMAN DAWN                 |
| WARREN      | BADMAN DAWN                 |
| GRETA       | BADMAN DAWN                 |
| OLYMPIA     | BADMAN DAWN                 |
| ALAN        | BADMAN DAWN                 |
| THORA       | BADMAN DAWN                 |
| MICHELLE    | BAKED CLEOPATRA             |
| PARKER      | BALLOON HOMEWARD            |
| MENA        | BALLOON HOMEWARD            |
| GARY        | BALLOON HOMEWARD            |
| RICHARD     | BALLOON HOMEWARD            |
| RENEE       | BALLOON HOMEWARD            |
| ROCK        | BALLOON HOMEWARD            |
| JUDY        | BALLROOM MOCKINGBIRD        |
| ADAM        | BALLROOM MOCKINGBIRD        |
| BEN         | BALLROOM MOCKINGBIRD        |
| DARYL       | BALLROOM MOCKINGBIRD        |
| HARRISON    | BALLROOM MOCKINGBIRD        |
| LUCILLE     | BALLROOM MOCKINGBIRD        |
| GENE        | BALLROOM MOCKINGBIRD        |
| BETTE       | BANG KWAI                   |
| SANDRA      | BANG KWAI                   |
| JULIA       | BANG KWAI                   |
| MICHELLE    | BANG KWAI                   |
| WALTER      | BANG KWAI                   |
| RUSSELL     | BANG KWAI                   |
| FAY         | BANG KWAI                   |
| JOHNNY      | BANGER PINOCCHIO            |
| LUCILLE     | BANGER PINOCCHIO            |
| DUSTIN      | BANGER PINOCCHIO            |
| JAYNE       | BANGER PINOCCHIO            |
| GENE        | BANGER PINOCCHIO            |
| AUDREY      | BANGER PINOCCHIO            |
| MARY        | BARBARELLA STREETCAR        |
| CUBA        | BARBARELLA STREETCAR        |
| NICK        | BARBARELLA STREETCAR        |
| ALAN        | BARBARELLA STREETCAR        |
| GENE        | BARBARELLA STREETCAR        |
| JENNIFER    | BAREFOOT MANCHURIAN         |
| ELVIS       | BAREFOOT MANCHURIAN         |
| MILLA       | BAREFOOT MANCHURIAN         |
| KIRK        | BAREFOOT MANCHURIAN         |
| DARYL       | BAREFOOT MANCHURIAN         |
| ED          | BAREFOOT MANCHURIAN         |
| MORGAN      | BAREFOOT MANCHURIAN         |
| WILL        | BAREFOOT MANCHURIAN         |
| JESSICA     | BASIC EASY                  |
| PENELOPE    | BASIC EASY                  |
| GRETA       | BASIC EASY                  |
| EWAN        | BASIC EASY                  |
| EMILY       | BASIC EASY                  |
| GROUCHO     | BASIC EASY                  |
| WOODY       | BEACH HEARTBREAKERS         |
| NICK        | BEACH HEARTBREAKERS         |
| MENA        | BEACH HEARTBREAKERS         |
| BEN         | BEACH HEARTBREAKERS         |
| GENE        | BEACH HEARTBREAKERS         |
| FRANCES     | BEACH HEARTBREAKERS         |
| HARVEY      | BEACH HEARTBREAKERS         |
| SCARLETT    | BEAR GRACELAND              |
| PENELOPE    | BEAR GRACELAND              |
| BEN         | BEAR GRACELAND              |
| BETTE       | BEAST HUNCHBACK             |
| JODIE       | BEAST HUNCHBACK             |
| ANGELINA    | BEAST HUNCHBACK             |
| KENNETH     | BEAST HUNCHBACK             |
| SUSAN       | BEAST HUNCHBACK             |
| CAMERON     | BEAUTY GREASE               |
| ED          | BEAUTY GREASE               |
| LUCILLE     | BEAUTY GREASE               |
| NICK        | BEAUTY GREASE               |
| MICHAEL     | BEAUTY GREASE               |
| JENNIFER    | BED HIGHBALL                |
| GINA        | BED HIGHBALL                |
| SUSAN       | BED HIGHBALL                |
| ALBERT      | BED HIGHBALL                |
| AUDREY      | BED HIGHBALL                |
| LUCILLE     | BEDAZZLED MARRIED           |
| GARY        | BEDAZZLED MARRIED           |
| DAN         | BEDAZZLED MARRIED           |
| PENELOPE    | BEDAZZLED MARRIED           |
| JAYNE       | BEDAZZLED MARRIED           |
| LAURENCE    | BEDAZZLED MARRIED           |
| REESE       | BEDAZZLED MARRIED           |
| SANDRA      | BEETHOVEN EXORCIST          |
| WARREN      | BEETHOVEN EXORCIST          |
| SCARLETT    | BEETHOVEN EXORCIST          |
| MINNIE      | BEETHOVEN EXORCIST          |
| VIVIEN      | BEETHOVEN EXORCIST          |
| BELA        | BEETHOVEN EXORCIST          |
| TIM         | BEHAVIOR RUNAWAY            |
| REESE       | BEHAVIOR RUNAWAY            |
| DARYL       | BEHAVIOR RUNAWAY            |
| RITA        | BEHAVIOR RUNAWAY            |
| ED          | BEHAVIOR RUNAWAY            |
| REESE       | BENEATH RUSH                |
| ANGELINA    | BENEATH RUSH                |
| GENE        | BENEATH RUSH                |
| CHRIS       | BENEATH RUSH                |
| SUSAN       | BENEATH RUSH                |
| JANE        | BENEATH RUSH                |
| VIVIEN      | BENEATH RUSH                |
| GRACE       | BERETS AGENT                |
| JULIA       | BERETS AGENT                |
| JESSICA     | BERETS AGENT                |
| JULIANNE    | BERETS AGENT                |
| CATE        | BERETS AGENT                |
| ANGELA      | BERETS AGENT                |
| IAN         | BERETS AGENT                |
| WILLIAM     | BERETS AGENT                |
| MERYL       | BERETS AGENT                |
| JULIA       | BERETS AGENT                |
| CHRISTIAN   | BETRAYED REAR               |
| ANGELINA    | BETRAYED REAR               |
| MORGAN      | BETRAYED REAR               |
| NICK        | BETRAYED REAR               |
| SANDRA      | BEVERLY OUTLAW              |
| JODIE       | BEVERLY OUTLAW              |
| RALPH       | BEVERLY OUTLAW              |
| JOHN        | BEVERLY OUTLAW              |
| BETTE       | BIKINI BORROWERS            |
| PENELOPE    | BIKINI BORROWERS            |
| GOLDIE      | BILKO ANONYMOUS             |
| ELLEN       | BILKO ANONYMOUS             |
| RUSSELL     | BILKO ANONYMOUS             |
| DUSTIN      | BILL OTHERS                 |
| MINNIE      | BILL OTHERS                 |
| CHRIS       | BILL OTHERS                 |
| RUSSELL     | BILL OTHERS                 |
| AL          | BILL OTHERS                 |
| LAURENCE    | BILL OTHERS                 |
| GOLDIE      | BINGO TALENTED              |
| CAMERON     | BINGO TALENTED              |
| CARY        | BINGO TALENTED              |
| JON         | BINGO TALENTED              |
| RENEE       | BINGO TALENTED              |
| JOE         | BIRCH ANTITRUST             |
| WOODY       | BIRCH ANTITRUST             |
| DARYL       | BIRCH ANTITRUST             |
| EWAN        | BIRCH ANTITRUST             |
| ALAN        | BIRCH ANTITRUST             |
| MATTHEW     | BIRCH ANTITRUST             |
| FAY         | BIRD INDEPENDENCE           |
| JAYNE       | BIRD INDEPENDENCE           |
| KENNETH     | BIRDCAGE CASPER             |
| KENNETH     | BIRDCAGE CASPER             |
| SALMA       | BIRDCAGE CASPER             |
| RENEE       | BIRDCAGE CASPER             |
| SANDRA      | BIRDS PERDITION             |
| GARY        | BIRDS PERDITION             |
| SYLVESTER   | BIRDS PERDITION             |
| WHOOPI      | BIRDS PERDITION             |
| SANDRA      | BLACKOUT PRIVATE            |
| CARY        | BLACKOUT PRIVATE            |
| CAMERON     | BLACKOUT PRIVATE            |
| KENNETH     | BLACKOUT PRIVATE            |
| MATTHEW     | BLACKOUT PRIVATE            |
| JENNIFER    | BLADE POLISH                |
| ALEC        | BLADE POLISH                |
| KEVIN       | BLADE POLISH                |
| RIVER       | BLADE POLISH                |
| ANGELA      | BLADE POLISH                |
| FRED        | BLANKET BEVERLY             |
| ALAN        | BLANKET BEVERLY             |
| BURT        | BLANKET BEVERLY             |
| THORA       | BLANKET BEVERLY             |
| BURT        | BLINDNESS GUN               |
| CHRIS       | BLINDNESS GUN               |
| ADAM        | BLINDNESS GUN               |
| CATE        | BLOOD ARGONAUTS             |
| ADAM        | BLOOD ARGONAUTS             |
| LAURA       | BLOOD ARGONAUTS             |
| CUBA        | BLOOD ARGONAUTS             |
| CAMERON     | BLUES INSTINCT              |
| GROUCHO     | BLUES INSTINCT              |
| SALMA       | BLUES INSTINCT              |
| MATTHEW     | BLUES INSTINCT              |
| DAN         | BOILED DARES                |
| TIM         | BOILED DARES                |
| NICK        | BOILED DARES                |
| PENELOPE    | BOILED DARES                |
| JIM         | BOILED DARES                |
| MORGAN      | BOILED DARES                |
| GREGORY     | BOILED DARES                |
| JULIA       | BOILED DARES                |
| JOHNNY      | BONNIE HOLOCAUST            |
| JULIA       | BONNIE HOLOCAUST            |
| HENRY       | BONNIE HOLOCAUST            |
| MINNIE      | BONNIE HOLOCAUST            |
| SUSAN       | BONNIE HOLOCAUST            |
| FRANCES     | BONNIE HOLOCAUST            |
| FAY         | BONNIE HOLOCAUST            |
| OPRAH       | BONNIE HOLOCAUST            |
| ED          | BONNIE HOLOCAUST            |
| KEVIN       | BOOGIE AMELIE               |
| JODIE       | BOOGIE AMELIE               |
| GROUCHO     | BOOGIE AMELIE               |
| NICK        | BOOGIE AMELIE               |
| GENE        | BOOGIE AMELIE               |
| MERYL       | BOOGIE AMELIE               |
| ED          | BOONDOCK BALLROOM           |
| JENNIFER    | BOONDOCK BALLROOM           |
| UMA         | BOONDOCK BALLROOM           |
| FRED        | BOONDOCK BALLROOM           |
| KIRSTEN     | BOONDOCK BALLROOM           |
| SANDRA      | BOONDOCK BALLROOM           |
| DAN         | BOONDOCK BALLROOM           |
| RAY         | BOONDOCK BALLROOM           |
| KENNETH     | BOONDOCK BALLROOM           |
| CHRIS       | BOONDOCK BALLROOM           |
| WARREN      | BOONDOCK BALLROOM           |
| HUMPHREY    | BOONDOCK BALLROOM           |
| AUDREY      | BOONDOCK BALLROOM           |
| KIRSTEN     | BORN SPINAL                 |
| SISSY       | BORN SPINAL                 |
| NICK        | BORN SPINAL                 |
| DUSTIN      | BORN SPINAL                 |
| RAY         | BORN SPINAL                 |
| KENNETH     | BORN SPINAL                 |
| DAN         | BORN SPINAL                 |
| RITA        | BORN SPINAL                 |
| MERYL       | BORN SPINAL                 |
| CUBA        | BORROWERS BEDAZZLED         |
| ELVIS       | BORROWERS BEDAZZLED         |
| KIRK        | BORROWERS BEDAZZLED         |
| SCARLETT    | BORROWERS BEDAZZLED         |
| DARYL       | BORROWERS BEDAZZLED         |
| HARVEY      | BORROWERS BEDAZZLED         |
| JON         | BORROWERS BEDAZZLED         |
| RIP         | BOULEVARD MOB               |
| AUDREY      | BOULEVARD MOB               |
| KIRSTEN     | BOULEVARD MOB               |
| MORGAN      | BOULEVARD MOB               |
| DAN         | BOULEVARD MOB               |
| EWAN        | BOULEVARD MOB               |
| ANGELA      | BOULEVARD MOB               |
| HARVEY      | BOULEVARD MOB               |
| KARL        | BOUND CHEAPER               |
| CUBA        | BOUND CHEAPER               |
| KARL        | BOWFINGER GABLES            |
| CARMEN      | BOWFINGER GABLES            |
| MICHELLE    | BOWFINGER GABLES            |
| MINNIE      | BOWFINGER GABLES            |
| WILL        | BOWFINGER GABLES            |
| RIP         | BRANNIGAN SUNRISE           |
| KENNETH     | BRANNIGAN SUNRISE           |
| NICK        | BRAVEHEART HUMAN            |
| KIRSTEN     | BRAVEHEART HUMAN            |
| JANE        | BRAVEHEART HUMAN            |
| JAYNE       | BRAVEHEART HUMAN            |
| ANGELINA    | BREAKFAST GOLDFINGER        |
| RUSSELL     | BREAKFAST GOLDFINGER        |
| AL          | BREAKFAST GOLDFINGER        |
| MICHAEL     | BREAKFAST GOLDFINGER        |
| JULIA       | BREAKFAST GOLDFINGER        |
| GRACE       | BREAKING HOME               |
| HELEN       | BREAKING HOME               |
| WOODY       | BREAKING HOME               |
| CARMEN      | BREAKING HOME               |
| FRANCES     | BREAKING HOME               |
| MORGAN      | BREAKING HOME               |
| ANGELA      | BRIDE INTRIGUE              |
| CAMERON     | BRIGHT ENCOUNTERS           |
| ALBERT      | BRIGHT ENCOUNTERS           |
| RENEE       | BRIGHT ENCOUNTERS           |
| MERYL       | BRIGHT ENCOUNTERS           |
| FRANCES     | BRINGING HYSTERICAL         |
| ANGELA      | BRINGING HYSTERICAL         |
| JODIE       | BROOKLYN DESERT             |
| JAYNE       | BROOKLYN DESERT             |
| SEAN        | BROOKLYN DESERT             |
| ALBERT      | BROOKLYN DESERT             |
| GROUCHO     | BROOKLYN DESERT             |
| FRED        | BROTHERHOOD BLANKET         |
| FRANCES     | BROTHERHOOD BLANKET         |
| JUDE        | BROTHERHOOD BLANKET         |
| JAYNE       | BROTHERHOOD BLANKET         |
| DARYL       | BROTHERHOOD BLANKET         |
| VIVIEN      | BUBBLE GROSSE               |
| MENA        | BUBBLE GROSSE               |
| ROCK        | BUBBLE GROSSE               |
| RIP         | BUCKET BROTHERHOOD          |
| TIM         | BUCKET BROTHERHOOD          |
| GARY        | BUCKET BROTHERHOOD          |
| CHARLIZE    | BUCKET BROTHERHOOD          |
| KIRSTEN     | BUCKET BROTHERHOOD          |
| BURT        | BUCKET BROTHERHOOD          |
| WOODY       | BUGSY SONG                  |
| KIRSTEN     | BUGSY SONG                  |
| NICK        | BULL SHAWSHANK              |
| SANDRA      | BULL SHAWSHANK              |
| ALEC        | BULL SHAWSHANK              |
| KIRK        | BULL SHAWSHANK              |
| DAN         | BULL SHAWSHANK              |
| JULIANNE    | BULL SHAWSHANK              |
| ANGELA      | BULL SHAWSHANK              |
| JAYNE       | BULL SHAWSHANK              |
| PENELOPE    | BULWORTH COMMANDMENTS       |
| ANGELA      | BULWORTH COMMANDMENTS       |
| SCARLETT    | BULWORTH COMMANDMENTS       |
| ALAN        | BULWORTH COMMANDMENTS       |
| KARL        | BUNCH MINDS                 |
| WOODY       | BUNCH MINDS                 |
| JOHNNY      | BUNCH MINDS                 |
| CHRIS       | BUNCH MINDS                 |
| GRETA       | BUNCH MINDS                 |
| EWAN        | BUNCH MINDS                 |
| JADA        | BUNCH MINDS                 |
| LAURENCE    | BUNCH MINDS                 |
| CUBA        | BUTCH PANTHER               |
| CARMEN      | BUTCH PANTHER               |
| GROUCHO     | BUTCH PANTHER               |
| NICK        | BUTTERFLY CHOCOLAT          |
| MENA        | BUTTERFLY CHOCOLAT          |
| KIM         | BUTTERFLY CHOCOLAT          |
| LISA        | BUTTERFLY CHOCOLAT          |
| ED          | BUTTERFLY CHOCOLAT          |
| BURT        | BUTTERFLY CHOCOLAT          |
| MARY        | BUTTERFLY CHOCOLAT          |
| UMA         | CABIN FLASH                 |
| ALEC        | CABIN FLASH                 |
| BEN         | CABIN FLASH                 |
| RENEE       | CABIN FLASH                 |
| ED          | CADDYSHACK JEDI             |
| ELVIS       | CADDYSHACK JEDI             |
| TOM         | CADDYSHACK JEDI             |
| NATALIE     | CADDYSHACK JEDI             |
| KENNETH     | CADDYSHACK JEDI             |
| MERYL       | CADDYSHACK JEDI             |
| ROCK        | CADDYSHACK JEDI             |
| BETTE       | CALENDAR GUNFIGHT           |
| CAMERON     | CALENDAR GUNFIGHT           |
| TIM         | CALENDAR GUNFIGHT           |
| MILLA       | CALENDAR GUNFIGHT           |
| GARY        | CALENDAR GUNFIGHT           |
| GINA        | CALENDAR GUNFIGHT           |
| GRETA       | CALENDAR GUNFIGHT           |
| WHOOPI      | CALENDAR GUNFIGHT           |
| SCARLETT    | CALIFORNIA BIRDS            |
| RUSSELL     | CALIFORNIA BIRDS            |
| JUDE        | CAMELOT VACATION            |
| ALBERT      | CAMELOT VACATION            |
| MATTHEW     | CAMPUS REMEMBER             |
| REESE       | CAMPUS REMEMBER             |
| WILL        | CAMPUS REMEMBER             |
| SANDRA      | CANDIDATE PERDITION         |
| SIDNEY      | CANDIDATE PERDITION         |
| MORGAN      | CANDIDATE PERDITION         |
| THORA       | CANDIDATE PERDITION         |
| SANDRA      | CANDLES GRAPES              |
| REESE       | CANDLES GRAPES              |
| ANGELA      | CANDLES GRAPES              |
| MILLA       | CANDLES GRAPES              |
| CHARLIZE    | CANDLES GRAPES              |
| ALBERT      | CANDLES GRAPES              |
| JOHN        | CANDLES GRAPES              |
| ZERO        | CANYON STOCK                |
| VAL         | CANYON STOCK                |
| RALPH       | CANYON STOCK                |
| SPENCER     | CANYON STOCK                |
| MATTHEW     | CANYON STOCK                |
| RUSSELL     | CANYON STOCK                |
| HELEN       | CAPER MOTIONS               |
| AUDREY      | CAPER MOTIONS               |
| VAL         | CAPER MOTIONS               |
| CHRISTIAN   | CAPER MOTIONS               |
| KEVIN       | CAPER MOTIONS               |
| CATE        | CAPER MOTIONS               |
| BURT        | CAPER MOTIONS               |
| BEN         | CARIBBEAN LIBERTY           |
| ELLEN       | CARIBBEAN LIBERTY           |
| CHRIS       | CARIBBEAN LIBERTY           |
| SUSAN       | CARIBBEAN LIBERTY           |
| JANE        | CARIBBEAN LIBERTY           |
| KIM         | CARIBBEAN LIBERTY           |
| HARVEY      | CARIBBEAN LIBERTY           |
| LAURENCE    | CARIBBEAN LIBERTY           |
| FRED        | CAROL TEXAS                 |
| GARY        | CAROL TEXAS                 |
| DUSTIN      | CAROL TEXAS                 |
| BEN         | CAROL TEXAS                 |
| VIVIEN      | CAROL TEXAS                 |
| OPRAH       | CAROL TEXAS                 |
| THORA       | CAROL TEXAS                 |
| VAL         | CARRIE BUNCH                |
| MENA        | CARRIE BUNCH                |
| JUDE        | CARRIE BUNCH                |
| ANGELINA    | CARRIE BUNCH                |
| KENNETH     | CARRIE BUNCH                |
| GRETA       | CARRIE BUNCH                |
| BELA        | CARRIE BUNCH                |
| KIRSTEN     | CASABLANCA SUPER            |
| WALTER      | CASABLANCA SUPER            |
| ANGELA      | CASABLANCA SUPER            |
| REESE       | CASABLANCA SUPER            |
| HELEN       | CASPER DRAGONFLY            |
| RAY         | CASPER DRAGONFLY            |
| RALPH       | CASPER DRAGONFLY            |
| ELLEN       | CASPER DRAGONFLY            |
| WALTER      | CASPER DRAGONFLY            |
| CUBA        | CASSIDY WYOMING             |
| SANDRA      | CASSIDY WYOMING             |
| AUDREY      | CASSIDY WYOMING             |
| ANGELA      | CASSIDY WYOMING             |
| LUCILLE     | CASSIDY WYOMING             |
| ANGELA      | CASSIDY WYOMING             |
| MARY        | CASSIDY WYOMING             |
| CAMERON     | CASUALTIES ENCINO           |
| MENA        | CASUALTIES ENCINO           |
| DARYL       | CASUALTIES ENCINO           |
| GROUCHO     | CASUALTIES ENCINO           |
| SUSAN       | CASUALTIES ENCINO           |
| HELEN       | CAT CONEHEADS               |
| ANGELA      | CAT CONEHEADS               |
| LAURA       | CAT CONEHEADS               |
| RENEE       | CAT CONEHEADS               |
| JOHNNY      | CATCH AMISTAD               |
| CHRISTIAN   | CATCH AMISTAD               |
| KENNETH     | CATCH AMISTAD               |
| DAN         | CATCH AMISTAD               |
| IAN         | CATCH AMISTAD               |
| PENELOPE    | CAUSE DATE                  |
| DUSTIN      | CAUSE DATE                  |
| JAYNE       | CAUSE DATE                  |
| WILLIAM     | CAUSE DATE                  |
| JAYNE       | CAUSE DATE                  |
| REESE       | CAUSE DATE                  |
| DUSTIN      | CELEBRITY HORN              |
| MATTHEW     | CELEBRITY HORN              |
| ANGELA      | CELEBRITY HORN              |
| JAYNE       | CELEBRITY HORN              |
| ALEC        | CENTER DINOSAUR             |
| FAY         | CENTER DINOSAUR             |
| GEOFFREY    | CENTER DINOSAUR             |
| ED          | CENTER DINOSAUR             |
| NICK        | CHAINSAW UPTOWN             |
| GENE        | CHAINSAW UPTOWN             |
| ALEC        | CHAMBER ITALIAN             |
| HENRY       | CHAMBER ITALIAN             |
| RIP         | CHAMBER ITALIAN             |
| GINA        | CHAMBER ITALIAN             |
| ADAM        | CHAMBER ITALIAN             |
| RICHARD     | CHAMBER ITALIAN             |
| EMILY       | CHAMBER ITALIAN             |
| FRANCES     | CHAMPION FLATLINERS         |
| JUDE        | CHAMPION FLATLINERS         |
| CAMERON     | CHAMPION FLATLINERS         |
| GENE        | CHAMPION FLATLINERS         |
| MILLA       | CHANCE RESURRECTION         |
| CHRISTIAN   | CHANCE RESURRECTION         |
| BEN         | CHANCE RESURRECTION         |
| WHOOPI      | CHANCE RESURRECTION         |
| ANGELA      | CHANCE RESURRECTION         |
| MERYL       | CHANCE RESURRECTION         |
| TIM         | CHAPLIN LICENSE             |
| PENELOPE    | CHAPLIN LICENSE             |
| GROUCHO     | CHAPLIN LICENSE             |
| GINA        | CHAPLIN LICENSE             |
| CUBA        | CHAPLIN LICENSE             |
| MINNIE      | CHAPLIN LICENSE             |
| GREG        | CHARADE DUFFEL              |
| KIRSTEN     | CHARADE DUFFEL              |
| WARREN      | CHARADE DUFFEL              |
| GINA        | CHARIOTS CONSPIRACY         |
| MICHAEL     | CHARIOTS CONSPIRACY         |
| TOM         | CHASING FIGHT               |
| JADA        | CHASING FIGHT               |
| FAY         | CHASING FIGHT               |
| RUSSELL     | CHASING FIGHT               |
| MENA        | CHASING FIGHT               |
| PENELOPE    | CHEAPER CLYDE               |
| LUCILLE     | CHEAPER CLYDE               |
| MAE         | CHICAGO NORTH               |
| CUBA        | CHICAGO NORTH               |
| LIZA        | CHICAGO NORTH               |
| KEVIN       | CHICAGO NORTH               |
| RIVER       | CHICAGO NORTH               |
| MERYL       | CHICAGO NORTH               |
| BURT        | CHICAGO NORTH               |
| JAYNE       | CHICAGO NORTH               |
| KIRSTEN     | CHICKEN HELLFIGHTERS        |
| HENRY       | CHICKEN HELLFIGHTERS        |
| MARY        | CHILL LUCK                  |
| BURT        | CHILL LUCK                  |
| WOODY       | CHILL LUCK                  |
| MEG         | CHILL LUCK                  |
| WARREN      | CHILL LUCK                  |
| UMA         | CHINATOWN GLADIATOR         |
| DAN         | CHINATOWN GLADIATOR         |
| BOB         | CHINATOWN GLADIATOR         |
| JUDE        | CHINATOWN GLADIATOR         |
| JESSICA     | CHINATOWN GLADIATOR         |
| SEAN        | CHINATOWN GLADIATOR         |
| PENELOPE    | CHINATOWN GLADIATOR         |
| GEOFFREY    | CHINATOWN GLADIATOR         |
| JEFF        | CHINATOWN GLADIATOR         |
| JAYNE       | CHINATOWN GLADIATOR         |
| NICK        | CHISUM BEHAVIOR             |
| GENE        | CHISUM BEHAVIOR             |
| FAY         | CHISUM BEHAVIOR             |
| JULIA       | CHISUM BEHAVIOR             |
| JOHNNY      | CHITTY LOCK                 |
| LUCILLE     | CHITTY LOCK                 |
| ELVIS       | CHITTY LOCK                 |
| SISSY       | CHITTY LOCK                 |
| VAL         | CHITTY LOCK                 |
| SUSAN       | CHITTY LOCK                 |
| RUSSELL     | CHITTY LOCK                 |
| AL          | CHITTY LOCK                 |
| NICK        | CHITTY LOCK                 |
| OLYMPIA     | CHITTY LOCK                 |
| LISA        | CHITTY LOCK                 |
| HUMPHREY    | CHITTY LOCK                 |
| ROCK        | CHITTY LOCK                 |
| JOE         | CHOCOLAT HARRY              |
| RIP         | CHOCOLAT HARRY              |
| KIRK        | CHOCOLAT HARRY              |
| JANE        | CHOCOLAT HARRY              |
| REESE       | CHOCOLAT HARRY              |
| JOE         | CHOCOLATE DUCK              |
| CAMERON     | CHOCOLATE DUCK              |
| GARY        | CHOCOLATE DUCK              |
| MINNIE      | CHOCOLATE DUCK              |
| JULIANNE    | CHOCOLATE DUCK              |
| HUMPHREY    | CHOCOLATE DUCK              |
| GROUCHO     | CHOCOLATE DUCK              |
| PENELOPE    | CHRISTMAS MOONSHINE         |
| EMILY       | CHRISTMAS MOONSHINE         |
| THORA       | CHRISTMAS MOONSHINE         |
| JULIA       | CIDER DESIRE                |
| JODIE       | CIDER DESIRE                |
| FRANCES     | CIDER DESIRE                |
| PENELOPE    | CIDER DESIRE                |
| JON         | CIDER DESIRE                |
| ANNE        | CINCINATTI WHISPERER        |
| RUSSELL     | CINCINATTI WHISPERER        |
| CUBA        | CINCINATTI WHISPERER        |
| JULIANNE    | CINCINATTI WHISPERER        |
| BOB         | CIRCUS YOUTH                |
| MATTHEW     | CIRCUS YOUTH                |
| KEVIN       | CITIZEN SHREK               |
| GARY        | CITIZEN SHREK               |
| JUDE        | CITIZEN SHREK               |
| CARY        | CITIZEN SHREK               |
| KENNETH     | CITIZEN SHREK               |
| RUSSELL     | CITIZEN SHREK               |
| BEN         | CITIZEN SHREK               |
| IAN         | CITIZEN SHREK               |
| UMA         | CLASH FREDDY                |
| VIVIEN      | CLASH FREDDY                |
| HELEN       | CLASH FREDDY                |
| MILLA       | CLASH FREDDY                |
| LIZA        | CLASH FREDDY                |
| KIM         | CLASH FREDDY                |
| ALAN        | CLASH FREDDY                |
| KARL        | CLEOPATRA DEVIL             |
| FRED        | CLEOPATRA DEVIL             |
| EWAN        | CLEOPATRA DEVIL             |
| KIM         | CLEOPATRA DEVIL             |
| FAY         | CLEOPATRA DEVIL             |
| WILLIAM     | CLEOPATRA DEVIL             |
| JOHN        | CLEOPATRA DEVIL             |
| PENELOPE    | CLERKS ANGELS               |
| SUSAN       | CLERKS ANGELS               |
| ADAM        | CLERKS ANGELS               |
| BELA        | CLERKS ANGELS               |
| SPENCER     | CLOCKWORK PARADISE          |
| SYLVESTER   | CLOCKWORK PARADISE          |
| SALMA       | CLOCKWORK PARADISE          |
| KEVIN       | CLOCKWORK PARADISE          |
| LUCILLE     | CLOCKWORK PARADISE          |
| MATTHEW     | CLONES PINOCCHIO            |
| ANGELA      | CLONES PINOCCHIO            |
| SIDNEY      | CLONES PINOCCHIO            |
| SALMA       | CLONES PINOCCHIO            |
| MERYL       | CLONES PINOCCHIO            |
| KIRSTEN     | CLOSER BANG                 |
| JODIE       | CLOSER BANG                 |
| RUSSELL     | CLOSER BANG                 |
| GRETA       | CLOSER BANG                 |
| ED          | CLOSER BANG                 |
| JULIA       | CLOSER BANG                 |
| TOM         | CLUB GRAFFITI               |
| MORGAN      | CLUB GRAFFITI               |
| LISA        | CLUB GRAFFITI               |
| DEBBIE      | CLUB GRAFFITI               |
| KIRK        | CLUE GRAIL                  |
| RIP         | CLUE GRAIL                  |
| SPENCER     | CLUE GRAIL                  |
| LIZA        | CLUE GRAIL                  |
| GENE        | CLUE GRAIL                  |
| MERYL       | CLUE GRAIL                  |
| UMA         | CLUELESS BUCKET             |
| CHARLIZE    | CLUELESS BUCKET             |
| GINA        | CLUELESS BUCKET             |
| CAMERON     | CLUELESS BUCKET             |
| MORGAN      | CLUELESS BUCKET             |
| ADAM        | CLUELESS BUCKET             |
| ALAN        | CLUELESS BUCKET             |
| JON         | CLUELESS BUCKET             |
| SISSY       | CLYDE THEORY                |
| JOHNNY      | CLYDE THEORY                |
| GREG        | CLYDE THEORY                |
| MERYL       | CLYDE THEORY                |
| BETTE       | COAST RAINBOW               |
| CAMERON     | COAST RAINBOW               |
| SISSY       | COAST RAINBOW               |
| REESE       | COAST RAINBOW               |
| FRANCES     | COAST RAINBOW               |
| ANGELA      | COAST RAINBOW               |
| OPRAH       | COAST RAINBOW               |
| LISA        | COAST RAINBOW               |
| BURT        | COAST RAINBOW               |
| REESE       | COAST RAINBOW               |
| BETTE       | COLDBLOODED DARLING         |
| LUCILLE     | COLDBLOODED DARLING         |
| BEN         | COLDBLOODED DARLING         |
| GINA        | COLDBLOODED DARLING         |
| PENELOPE    | COLOR PHILADELPHIA          |
| GROUCHO     | COLOR PHILADELPHIA          |
| SALMA       | COLOR PHILADELPHIA          |
| DARYL       | COLOR PHILADELPHIA          |
| CHRISTOPHER | COLOR PHILADELPHIA          |
| OLYMPIA     | COLOR PHILADELPHIA          |
| JOHN        | COLOR PHILADELPHIA          |
| CAMERON     | COMA HEAD                   |
| RENEE       | COMA HEAD                   |
| GEOFFREY    | COMA HEAD                   |
| GOLDIE      | COMANCHEROS ENEMY           |
| CATE        | COMANCHEROS ENEMY           |
| JAYNE       | COMANCHEROS ENEMY           |
| MICHAEL     | COMANCHEROS ENEMY           |
| RENEE       | COMANCHEROS ENEMY           |
| RUSSELL     | COMFORTS RUSH               |
| MERYL       | COMFORTS RUSH               |
| HUMPHREY    | COMFORTS RUSH               |
| HUMPHREY    | COMFORTS RUSH               |
| BELA        | COMFORTS RUSH               |
| GRACE       | COMMAND DARLING             |
| BURT        | COMMAND DARLING             |
| KENNETH     | COMMAND DARLING             |
| LIZA        | COMMAND DARLING             |
| RITA        | COMMAND DARLING             |
| EWAN        | COMMAND DARLING             |
| GEOFFREY    | COMMAND DARLING             |
| MERYL       | COMMAND DARLING             |
| JOHNNY      | COMMANDMENTS EXPRESS        |
| BURT        | COMMANDMENTS EXPRESS        |
| WARREN      | COMMANDMENTS EXPRESS        |
| CUBA        | COMMANDMENTS EXPRESS        |
| JOHNNY      | CONEHEADS SMOOCHY           |
| DAN         | CONEHEADS SMOOCHY           |
| JULIA       | CONEHEADS SMOOCHY           |
| ALEC        | CONEHEADS SMOOCHY           |
| AUDREY      | CONEHEADS SMOOCHY           |
| JULIA       | CONEHEADS SMOOCHY           |
| GINA        | CONEHEADS SMOOCHY           |
| WARREN      | CONEHEADS SMOOCHY           |
| RICHARD     | CONEHEADS SMOOCHY           |
| GRACE       | CONFESSIONS MAGUIRE         |
| RUSSELL     | CONFESSIONS MAGUIRE         |
| WARREN      | CONFESSIONS MAGUIRE         |
| AUDREY      | CONFESSIONS MAGUIRE         |
| PARKER      | CONFIDENTIAL INTERVIEW      |
| SYLVESTER   | CONFIDENTIAL INTERVIEW      |
| CHRISTIAN   | CONFUSED CANDLES            |
| RALPH       | CONFUSED CANDLES            |
| JAMES       | CONFUSED CANDLES            |
| ALBERT      | CONFUSED CANDLES            |
| RIVER       | CONFUSED CANDLES            |
| GENE        | CONFUSED CANDLES            |
| TOM         | CONGENIALITY QUEST          |
| NICK        | CONGENIALITY QUEST          |
| CHRISTOPHER | CONGENIALITY QUEST          |
| KARL        | CONNECTICUT TRAMP           |
| FRED        | CONNECTICUT TRAMP           |
| JOHNNY      | CONNECTICUT TRAMP           |
| HENRY       | CONNECTICUT TRAMP           |
| MEG         | CONNECTICUT TRAMP           |
| ALBERT      | CONNECTICUT TRAMP           |
| VIVIEN      | CONNECTICUT TRAMP           |
| CAMERON     | CONNECTION MICROCOSMOS      |
| NATALIE     | CONNECTION MICROCOSMOS      |
| SCARLETT    | CONNECTION MICROCOSMOS      |
| RENEE       | CONNECTION MICROCOSMOS      |
| FAY         | CONNECTION MICROCOSMOS      |
| RUSSELL     | CONNECTION MICROCOSMOS      |
| VIVIEN      | CONNECTION MICROCOSMOS      |
| MATTHEW     | CONQUERER NUTS              |
| KIRSTEN     | CONQUERER NUTS              |
| KEVIN       | CONQUERER NUTS              |
| HENRY       | CONQUERER NUTS              |
| CAMERON     | CONQUERER NUTS              |
| JOHN        | CONQUERER NUTS              |
| KIRK        | CONSPIRACY SPIRIT           |
| MINNIE      | CONSPIRACY SPIRIT           |
| CHRISTOPHER | CONSPIRACY SPIRIT           |
| MENA        | CONSPIRACY SPIRIT           |
| MENA        | CONTACT ANONYMOUS           |
| CHRISTOPHER | CONTACT ANONYMOUS           |
| MORGAN      | CONTACT ANONYMOUS           |
| EWAN        | CONTACT ANONYMOUS           |
| OLYMPIA     | CONTACT ANONYMOUS           |
| BOB         | CONTROL ANTHEM              |
| AUDREY      | CONTROL ANTHEM              |
| CHARLIZE    | CONTROL ANTHEM              |
| DUSTIN      | CONVERSATION DOWNHILL       |
| CHRIS       | CONVERSATION DOWNHILL       |
| GRETA       | CONVERSATION DOWNHILL       |
| PENELOPE    | CORE SUIT                   |
| PENELOPE    | CORE SUIT                   |
| ANGELA      | CORE SUIT                   |
| MENA        | CORE SUIT                   |
| ED          | COWBOY DOOM                 |
| MILLA       | COWBOY DOOM                 |
| JULIANNE    | COWBOY DOOM                 |
| WHOOPI      | COWBOY DOOM                 |
| GREGORY     | COWBOY DOOM                 |
| RIP         | CRAFT OUTFIELD              |
| HENRY       | CRAFT OUTFIELD              |
| SCARLETT    | CRAFT OUTFIELD              |
| LIZA        | CRAFT OUTFIELD              |
| JADA        | CRAFT OUTFIELD              |
| MARY        | CRAFT OUTFIELD              |
| VIVIEN      | CRANES RESERVOIR            |
| REESE       | CRANES RESERVOIR            |
| ANGELINA    | CRANES RESERVOIR            |
| CHARLIZE    | CRANES RESERVOIR            |
| LAURA       | CRANES RESERVOIR            |
| JULIA       | CRANES RESERVOIR            |
| SISSY       | CRAZY HOME                  |
| WOODY       | CRAZY HOME                  |
| MEG         | CRAZY HOME                  |
| RUSSELL     | CRAZY HOME                  |
| MORGAN      | CRAZY HOME                  |
| ALBERT      | CRAZY HOME                  |
| CATE        | CRAZY HOME                  |
| RUSSELL     | CRAZY HOME                  |
| VIVIEN      | CRAZY HOME                  |
| HARVEY      | CRAZY HOME                  |
| WILL        | CRAZY HOME                  |
| ALAN        | CRAZY HOME                  |
| GENE        | CRAZY HOME                  |
| SUSAN       | CREATURES SHAKESPEARE       |
| GROUCHO     | CREATURES SHAKESPEARE       |
| REESE       | CREATURES SHAKESPEARE       |
| CHRISTOPHER | CREEPERS KANE               |
| SYLVESTER   | CREEPERS KANE               |
| RENEE       | CREEPERS KANE               |
| SCARLETT    | CREEPERS KANE               |
| JAYNE       | CREEPERS KANE               |
| WILLIAM     | CREEPERS KANE               |
| JOE         | CROOKED FROGMEN             |
| CHRISTIAN   | CROOKED FROGMEN             |
| CATE        | CROOKED FROGMEN             |
| ALBERT      | CROOKED FROGMEN             |
| LAURENCE    | CROOKED FROGMEN             |
| WILLIAM     | CROOKED FROGMEN             |
| JUDE        | CROSSING DIVORCE            |
| MILLA       | CROSSING DIVORCE            |
| BETTE       | CROSSROADS CASUALTIES       |
| KENNETH     | CROSSROADS CASUALTIES       |
| KENNETH     | CROSSROADS CASUALTIES       |
| FRANCES     | CROSSROADS CASUALTIES       |
| ED          | CROSSROADS CASUALTIES       |
| RUSSELL     | CROSSROADS CASUALTIES       |
| MERYL       | CROSSROADS CASUALTIES       |
| ED          | CROSSROADS CASUALTIES       |
| CAMERON     | CROW GREASE                 |
| JODIE       | CROW GREASE                 |
| SCARLETT    | CROW GREASE                 |
| CHRIS       | CROW GREASE                 |
| WALTER      | CROW GREASE                 |
| GROUCHO     | CROW GREASE                 |
| CAMERON     | CROW GREASE                 |
| MORGAN      | CROW GREASE                 |
| FRANCES     | CROW GREASE                 |
| LISA        | CROW GREASE                 |
| MATTHEW     | CROWDS TELEMARK             |
| ANNE        | CROWDS TELEMARK             |
| JEFF        | CROWDS TELEMARK             |
| MATTHEW     | CROWDS TELEMARK             |
| GREG        | CRUELTY UNFORGIVEN          |
| WILL        | CRUELTY UNFORGIVEN          |
| TIM         | CRUSADE HONEY               |
| FAY         | CRUSADE HONEY               |
| RAY         | CRUSADE HONEY               |
| SEAN        | CRUSADE HONEY               |
| MEG         | CRUSADE HONEY               |
| MATTHEW     | CRUSADE HONEY               |
| RENEE       | CRUSADE HONEY               |
| ALBERT      | CRUSADE HONEY               |
| LISA        | CRUSADE HONEY               |
| REESE       | CRYSTAL BREAKING            |
| JAYNE       | CRYSTAL BREAKING            |
| PENELOPE    | CRYSTAL BREAKING            |
| LIZA        | CRYSTAL BREAKING            |
| FAY         | CRYSTAL BREAKING            |
| HELEN       | CUPBOARD SINNERS            |
| CAMERON     | CUPBOARD SINNERS            |
| TIM         | CUPBOARD SINNERS            |
| CHRISTIAN   | CUPBOARD SINNERS            |
| SPENCER     | CUPBOARD SINNERS            |
| MATTHEW     | CUPBOARD SINNERS            |
| FRANCES     | CUPBOARD SINNERS            |
| JADA        | CUPBOARD SINNERS            |
| JOE         | CURTAIN VIDEOTAPE           |
| WALTER      | CURTAIN VIDEOTAPE           |
| EWAN        | CURTAIN VIDEOTAPE           |
| HELEN       | CYCLONE FAMILY              |
| RIP         | CYCLONE FAMILY              |
| JUDY        | CYCLONE FAMILY              |
| JOHNNY      | DADDY PITTSBURGH            |
| KENNETH     | DADDY PITTSBURGH            |
| MICHELLE    | DADDY PITTSBURGH            |
| KEVIN       | DADDY PITTSBURGH            |
| DARYL       | DADDY PITTSBURGH            |
| JOHNNY      | DAISY MENAGERIE             |
| UMA         | DAISY MENAGERIE             |
| GOLDIE      | DAISY MENAGERIE             |
| JODIE       | DAISY MENAGERIE             |
| CARMEN      | DAISY MENAGERIE             |
| MILLA       | DAISY MENAGERIE             |
| MINNIE      | DAISY MENAGERIE             |
| JOE         | DALMATIONS SWEDEN           |
| KEVIN       | DALMATIONS SWEDEN           |
| VAL         | DALMATIONS SWEDEN           |
| GROUCHO     | DALMATIONS SWEDEN           |
| ALBERT      | DALMATIONS SWEDEN           |
| AL          | DALMATIONS SWEDEN           |
| MATTHEW     | DANCES NONE                 |
| ZERO        | DANCES NONE                 |
| RIP         | DANCES NONE                 |
| MAE         | DANCES NONE                 |
| WALTER      | DANCES NONE                 |
| KENNETH     | DANCING FEVER               |
| MATTHEW     | DANCING FEVER               |
| JANE        | DANCING FEVER               |
| JAYNE       | DANCING FEVER               |
| LAURA       | DANCING FEVER               |
| ROCK        | DANCING FEVER               |
| ANNE        | DANGEROUS UPTOWN            |
| MARY        | DANGEROUS UPTOWN            |
| RALPH       | DANGEROUS UPTOWN            |
| SPENCER     | DANGEROUS UPTOWN            |
| KIRSTEN     | DANGEROUS UPTOWN            |
| DARYL       | DANGEROUS UPTOWN            |
| CATE        | DANGEROUS UPTOWN            |
| ALBERT      | DANGEROUS UPTOWN            |
| KARL        | DARES PLUTO                 |
| BOB         | DARES PLUTO                 |
| CAMERON     | DARES PLUTO                 |
| WARREN      | DARES PLUTO                 |
| PENELOPE    | DARES PLUTO                 |
| GRETA       | DARES PLUTO                 |
| MERYL       | DARES PLUTO                 |
| LAURA       | DARES PLUTO                 |
| WILL        | DARES PLUTO                 |
| JULIA       | DARES PLUTO                 |
| GENE        | DARKNESS WAR                |
| GINA        | DARKNESS WAR                |
| DUSTIN      | DARKO DORADO                |
| MORGAN      | DARKO DORADO                |
| RICHARD     | DARKO DORADO                |
| GRETA       | DARKO DORADO                |
| FRANCES     | DARLING BREAKING            |
| JAYNE       | DARLING BREAKING            |
| BOB         | DARN FORRESTER              |
| SANDRA      | DARN FORRESTER              |
| JODIE       | DARN FORRESTER              |
| RALPH       | DARN FORRESTER              |
| CHARLIZE    | DARN FORRESTER              |
| SEAN        | DARN FORRESTER              |
| CHRIS       | DARN FORRESTER              |
| CATE        | DARN FORRESTER              |
| MENA        | DARN FORRESTER              |
| KARL        | DATE SPEED                  |
| KEVIN       | DATE SPEED                  |
| JUDE        | DATE SPEED                  |
| RIP         | DATE SPEED                  |
| MILLA       | DAUGHTER MADIGAN            |
| ED          | DAUGHTER MADIGAN            |
| LUCILLE     | DAUGHTER MADIGAN            |
| JOHN        | DAUGHTER MADIGAN            |
| RIP         | DAWN POND                   |
| SCARLETT    | DAWN POND                   |
| MATTHEW     | DAWN POND                   |
| VIVIEN      | DAWN POND                   |
| GROUCHO     | DAWN POND                   |
| MERYL       | DAWN POND                   |
| KARL        | DAY UNFAITHFUL              |
| MINNIE      | DAY UNFAITHFUL              |
| GREG        | DAY UNFAITHFUL              |
| ANGELA      | DAY UNFAITHFUL              |
| JULIA       | DAY UNFAITHFUL              |
| GRACE       | DAZED PUNK                  |
| BOB         | DAZED PUNK                  |
| BEN         | DAZED PUNK                  |
| GEOFFREY    | DAZED PUNK                  |
| BEN         | DAZED PUNK                  |
| GRETA       | DAZED PUNK                  |
| GRACE       | DECEIVER BETRAYED           |
| FRED        | DECEIVER BETRAYED           |
| MORGAN      | DECEIVER BETRAYED           |
| ALBERT      | DECEIVER BETRAYED           |
| TIM         | DEEP CRUSADE                |
| REESE       | DEEP CRUSADE                |
| SCARLETT    | DEEP CRUSADE                |
| WARREN      | DEEP CRUSADE                |
| GENE        | DEEP CRUSADE                |
| OLYMPIA     | DEEP CRUSADE                |
| GREGORY     | DEEP CRUSADE                |
| GINA        | DEER VIRGINIAN              |
| LIZA        | DEER VIRGINIAN              |
| IAN         | DEER VIRGINIAN              |
| FRED        | DELIVERANCE MULHOLLAND      |
| MATTHEW     | DELIVERANCE MULHOLLAND      |
| HUMPHREY    | DELIVERANCE MULHOLLAND      |
| GOLDIE      | DESERT POSEIDON             |
| HENRY       | DESERT POSEIDON             |
| BURT        | DESERT POSEIDON             |
| LIZA        | DESERT POSEIDON             |
| RENEE       | DESERT POSEIDON             |
| TOM         | DESIRE ALIEN                |
| JOHNNY      | DESIRE ALIEN                |
| ANGELINA    | DESIRE ALIEN                |
| JULIANNE    | DESIRE ALIEN                |
| CATE        | DESIRE ALIEN                |
| LAURA       | DESIRE ALIEN                |
| ROCK        | DESIRE ALIEN                |
| CARY        | DESPERATE TRAINSPOTTING     |
| RENEE       | DESPERATE TRAINSPOTTING     |
| MORGAN      | DESPERATE TRAINSPOTTING     |
| RENEE       | DESPERATE TRAINSPOTTING     |
| GRACE       | DESTINATION JERK            |
| RIP         | DESTINATION JERK            |
| CAMERON     | DESTINATION JERK            |
| NICK        | DESTINY SATURDAY            |
| SANDRA      | DESTINY SATURDAY            |
| KEVIN       | DESTINY SATURDAY            |
| ALEC        | DESTINY SATURDAY            |
| DAN         | DESTINY SATURDAY            |
| MARY        | DESTINY SATURDAY            |
| EMILY       | DESTINY SATURDAY            |
| MICHELLE    | DETAILS PACKER              |
| SALMA       | DETAILS PACKER              |
| KENNETH     | DETECTIVE VISION            |
| ANGELA      | DETECTIVE VISION            |
| JULIA       | DETECTIVE VISION            |
| MARY        | DEVIL DESIRE                |
| KIRSTEN     | DEVIL DESIRE                |
| GROUCHO     | DEVIL DESIRE                |
| ED          | DEVIL DESIRE                |
| EWAN        | DEVIL DESIRE                |
| JODIE       | DIARY PANIC                 |
| MARY        | DIARY PANIC                 |
| MAE         | DIARY PANIC                 |
| DARYL       | DIARY PANIC                 |
| LUCILLE     | DINOSAUR SECRETARY          |
| BURT        | DINOSAUR SECRETARY          |
| JAYNE       | DINOSAUR SECRETARY          |
| RUSSELL     | DINOSAUR SECRETARY          |
| PENELOPE    | DINOSAUR SECRETARY          |
| MINNIE      | DINOSAUR SECRETARY          |
| VIVIEN      | DIRTY ACE                   |
| SCARLETT    | DIRTY ACE                   |
| RIVER       | DIRTY ACE                   |
| GEOFFREY    | DIRTY ACE                   |
| MERYL       | DIRTY ACE                   |
| JOHNNY      | DISCIPLE MOTHER             |
| JULIA       | DISCIPLE MOTHER             |
| ADAM        | DISCIPLE MOTHER             |
| PENELOPE    | DISCIPLE MOTHER             |
| EWAN        | DISCIPLE MOTHER             |
| JAYNE       | DISCIPLE MOTHER             |
| MATTHEW     | DISCIPLE MOTHER             |
| ANGELINA    | DISTURBING SCARFACE         |
| KENNETH     | DISTURBING SCARFACE         |
| JULIANNE    | DISTURBING SCARFACE         |
| AUDREY      | DISTURBING SCARFACE         |
| SANDRA      | DIVIDE MONSTER              |
| CHRISTIAN   | DIVIDE MONSTER              |
| HENRY       | DIVIDE MONSTER              |
| CHRISTIAN   | DIVIDE MONSTER              |
| ALAN        | DIVIDE MONSTER              |
| GENE        | DIVIDE MONSTER              |
| CHRISTIAN   | DIVINE RESURRECTION         |
| CUBA        | DIVINE RESURRECTION         |
| HELEN       | DIVINE RESURRECTION         |
| DAN         | DIVINE RESURRECTION         |
| KENNETH     | DIVINE RESURRECTION         |
| CHRISTIAN   | DIVORCE SHINING             |
| SEAN        | DIVORCE SHINING             |
| MORGAN      | DIVORCE SHINING             |
| WILL        | DIVORCE SHINING             |
| GENE        | DIVORCE SHINING             |
| JULIA       | DIVORCE SHINING             |
| JAMES       | DOCTOR GRAIL                |
| PENELOPE    | DOCTOR GRAIL                |
| SALMA       | DOCTOR GRAIL                |
| ALBERT      | DOCTOR GRAIL                |
| CATE        | DOCTOR GRAIL                |
| JON         | DOCTOR GRAIL                |
| KIRK        | DOGMA FAMILY                |
| HENRY       | DOGMA FAMILY                |
| GROUCHO     | DOGMA FAMILY                |
| SIDNEY      | DOGMA FAMILY                |
| GINA        | DOGMA FAMILY                |
| RIVER       | DOGMA FAMILY                |
| CHRISTOPHER | DOGMA FAMILY                |
| CARY        | DOLLS RAGE                  |
| VIVIEN      | DONNIE ALLEY                |
| RIP         | DONNIE ALLEY                |
| TOM         | DONNIE ALLEY                |
| DUSTIN      | DONNIE ALLEY                |
| GROUCHO     | DONNIE ALLEY                |
| VIVIEN      | DONNIE ALLEY                |
| WILL        | DONNIE ALLEY                |
| CAMERON     | DOOM DANCING                |
| NICK        | DOOM DANCING                |
| CHRISTIAN   | DOOM DANCING                |
| JESSICA     | DOOM DANCING                |
| MAE         | DOOM DANCING                |
| WOODY       | DOOM DANCING                |
| WARREN      | DOOM DANCING                |
| CHRIS       | DOOM DANCING                |
| KARL        | DOORS PRESIDENT             |
| LUCILLE     | DOORS PRESIDENT             |
| NATALIE     | DOORS PRESIDENT             |
| CHRISTIAN   | DOORS PRESIDENT             |
| SYLVESTER   | DOORS PRESIDENT             |
| GENE        | DOORS PRESIDENT             |
| ED          | DOORS PRESIDENT             |
| KIM         | DOORS PRESIDENT             |
| REESE       | DOORS PRESIDENT             |
| AUDREY      | DORADO NOTTING              |
| JESSICA     | DORADO NOTTING              |
| GENE        | DORADO NOTTING              |
| FAY         | DORADO NOTTING              |
| KEVIN       | DOUBLE WRATH                |
| BURT        | DOUBLE WRATH                |
| FRANCES     | DOUBLE WRATH                |
| GARY        | DOUBLE WRATH                |
| CARY        | DOUBLE WRATH                |
| DARYL       | DOUBLE WRATH                |
| HARRISON    | DOUBLE WRATH                |
| JULIANNE    | DOUBLE WRATH                |
| HARRISON    | DOUBTFIRE LABYRINTH         |
| RENEE       | DOUBTFIRE LABYRINTH         |
| JULIANNE    | DOUBTFIRE LABYRINTH         |
| SCARLETT    | DOUBTFIRE LABYRINTH         |
| KENNETH     | DOUBTFIRE LABYRINTH         |
| WOODY       | DOWNHILL ENOUGH             |
| BEN         | DOWNHILL ENOUGH             |
| DARYL       | DOWNHILL ENOUGH             |
| HARVEY      | DOWNHILL ENOUGH             |
| NATALIE     | DOZEN LION                  |
| CAMERON     | DOZEN LION                  |
| JADA        | DOZEN LION                  |
| BEN         | DOZEN LION                  |
| LAURA       | DOZEN LION                  |
| KENNETH     | DOZEN LION                  |
| NICK        | DRACULA CRYSTAL             |
| JODIE       | DRACULA CRYSTAL             |
| CARMEN      | DRACULA CRYSTAL             |
| CAMERON     | DRACULA CRYSTAL             |
| MICHELLE    | DRACULA CRYSTAL             |
| SEAN        | DRACULA CRYSTAL             |
| BEN         | DRACULA CRYSTAL             |
| GREG        | DRACULA CRYSTAL             |
| MORGAN      | DRACULA CRYSTAL             |
| DARYL       | DRACULA CRYSTAL             |
| MORGAN      | DRACULA CRYSTAL             |
| IAN         | DRACULA CRYSTAL             |
| REESE       | DRACULA CRYSTAL             |
| ANNE        | DRAGON SQUAD                |
| SPENCER     | DRAGON SQUAD                |
| JIM         | DRAGON SQUAD                |
| SPENCER     | DRAGON SQUAD                |
| SUSAN       | DRAGON SQUAD                |
| ALBERT      | DRAGON SQUAD                |
| GENE        | DRAGON SQUAD                |
| ED          | DRAGON SQUAD                |
| CHRISTIAN   | DRAGONFLY STRANGERS         |
| ANGELINA    | DRAGONFLY STRANGERS         |
| FAY         | DRAGONFLY STRANGERS         |
| MILLA       | DREAM PICKUP                |
| JODIE       | DREAM PICKUP                |
| HUMPHREY    | DREAM PICKUP                |
| JON         | DREAM PICKUP                |
| VIVIEN      | DRIFTER COMMANDMENTS        |
| KIRSTEN     | DRIFTER COMMANDMENTS        |
| VAL         | DRIFTER COMMANDMENTS        |
| HENRY       | DRIFTER COMMANDMENTS        |
| SPENCER     | DRIFTER COMMANDMENTS        |
| AL          | DRIFTER COMMANDMENTS        |
| AUDREY      | DRIFTER COMMANDMENTS        |
| UMA         | DRIVER ANNIE                |
| SANDRA      | DRIVER ANNIE                |
| PARKER      | DRIVER ANNIE                |
| CHRISTIAN   | DRIVER ANNIE                |
| CHARLIZE    | DRIVER ANNIE                |
| MORGAN      | DRIVER ANNIE                |
| MORGAN      | DRIVER ANNIE                |
| FAY         | DRIVER ANNIE                |
| MATTHEW     | DRIVING POLISH              |
| VIVIEN      | DRIVING POLISH              |
| RIP         | DRIVING POLISH              |
| SUSAN       | DRIVING POLISH              |
| PENELOPE    | DRIVING POLISH              |
| NICK        | DRIVING POLISH              |
| WILL        | DRIVING POLISH              |
| BETTE       | DROP WATERFRONT             |
| CAMERON     | DROP WATERFRONT             |
| JUDY        | DROP WATERFRONT             |
| MENA        | DROP WATERFRONT             |
| JESSICA     | DROP WATERFRONT             |
| MEG         | DROP WATERFRONT             |
| FRANCES     | DROP WATERFRONT             |
| ED          | DROP WATERFRONT             |
| VIVIEN      | DRUMS DYNAMITE              |
| JUDE        | DRUMS DYNAMITE              |
| MORGAN      | DRUMS DYNAMITE              |
| LUCILLE     | DRUMS DYNAMITE              |
| WHOOPI      | DRUMS DYNAMITE              |
| JEFF        | DRUMS DYNAMITE              |
| REESE       | DRUMS DYNAMITE              |
| WOODY       | DUCK RACER                  |
| PENELOPE    | DUCK RACER                  |
| SANDRA      | DUDE BLINDNESS              |
| VAL         | DUDE BLINDNESS              |
| GROUCHO     | DUDE BLINDNESS              |
| RALPH       | DUDE BLINDNESS              |
| SCARLETT    | DUDE BLINDNESS              |
| SCARLETT    | DUDE BLINDNESS              |
| ANGELA      | DUDE BLINDNESS              |
| CARY        | DUFFEL APOCALYPSE           |
| GROUCHO     | DUFFEL APOCALYPSE           |
| EWAN        | DUFFEL APOCALYPSE           |
| SANDRA      | DUMBO LUST                  |
| HENRY       | DUMBO LUST                  |
| MAE         | DUMBO LUST                  |
| RALPH       | DUMBO LUST                  |
| SEAN        | DUMBO LUST                  |
| ED          | DUMBO LUST                  |
| EWAN        | DUMBO LUST                  |
| FAY         | DUMBO LUST                  |
| MARY        | DUMBO LUST                  |
| MATTHEW     | DURHAM PANKY                |
| WOODY       | DURHAM PANKY                |
| MILLA       | DURHAM PANKY                |
| BEN         | DURHAM PANKY                |
| SUSAN       | DURHAM PANKY                |
| SCARLETT    | DURHAM PANKY                |
| FRANCES     | DURHAM PANKY                |
| MORGAN      | DURHAM PANKY                |
| FAY         | DURHAM PANKY                |
| MARY        | DWARFS ALTER                |
| GROUCHO     | DYING MAKER                 |
| MICHAEL     | DYING MAKER                 |
| BOB         | DYNAMITE TARZAN             |
| CHARLIZE    | DYNAMITE TARZAN             |
| JULIANNE    | DYNAMITE TARZAN             |
| EWAN        | DYNAMITE TARZAN             |
| CUBA        | DYNAMITE TARZAN             |
| FRED        | EAGLES PANKY                |
| FRANCES     | EAGLES PANKY                |
| JUDE        | EAGLES PANKY                |
| MAE         | EAGLES PANKY                |
| SCARLETT    | EAGLES PANKY                |
| CHRIS       | EAGLES PANKY                |
| DAN         | EARLY HOME                  |
| MENA        | EARLY HOME                  |
| SCARLETT    | EARLY HOME                  |
| BEN         | EARLY HOME                  |
| WALTER      | EARLY HOME                  |
| MORGAN      | EARLY HOME                  |
| FRED        | EARRING INSTINCT            |
| LUCILLE     | EARRING INSTINCT            |
| MAE         | EARRING INSTINCT            |
| RITA        | EARRING INSTINCT            |
| HARVEY      | EARRING INSTINCT            |
| KENNETH     | EARTH VISION                |
| RICHARD     | EARTH VISION                |
| JAYNE       | EARTH VISION                |
| FRED        | EASY GLADIATOR              |
| MATTHEW     | EASY GLADIATOR              |
| ED          | EASY GLADIATOR              |
| JAYNE       | EDGE KISSING                |
| ANGELA      | EDGE KISSING                |
| CUBA        | EDGE KISSING                |
| JULIA       | EFFECT GLADIATOR            |
| ALEC        | EFFECT GLADIATOR            |
| NICK        | EFFECT GLADIATOR            |
| JULIA       | EFFECT GLADIATOR            |
| RENEE       | EFFECT GLADIATOR            |
| OLYMPIA     | EFFECT GLADIATOR            |
| LISA        | EFFECT GLADIATOR            |
| LUCILLE     | EGG IGBY                    |
| TOM         | EGG IGBY                    |
| NATALIE     | EGG IGBY                    |
| MERYL       | EGG IGBY                    |
| OPRAH       | EGG IGBY                    |
| CUBA        | EGYPT TENENBAUMS            |
| GARY        | EGYPT TENENBAUMS            |
| KENNETH     | EGYPT TENENBAUMS            |
| SUSAN       | EGYPT TENENBAUMS            |
| CHRIS       | EGYPT TENENBAUMS            |
| KIRK        | ELEMENT FREDDY              |
| ANGELA      | ELEMENT FREDDY              |
| MERYL       | ELEMENT FREDDY              |
| BELA        | ELEMENT FREDDY              |
| PENELOPE    | ELEPHANT TROJAN             |
| CAMERON     | ELEPHANT TROJAN             |
| VAL         | ELEPHANT TROJAN             |
| GINA        | ELEPHANT TROJAN             |
| HARRISON    | ELEPHANT TROJAN             |
| CAMERON     | ELF MURDER                  |
| WARREN      | ELF MURDER                  |
| GENE        | ELF MURDER                  |
| ALBERT      | ELF MURDER                  |
| AUDREY      | ELF MURDER                  |
| DAN         | ELIZABETH SHANE             |
| BEN         | ELIZABETH SHANE             |
| OPRAH       | ELIZABETH SHANE             |
| CUBA        | EMPIRE MALKOVICH            |
| FRED        | EMPIRE MALKOVICH            |
| HELEN       | EMPIRE MALKOVICH            |
| DAN         | EMPIRE MALKOVICH            |
| RAY         | EMPIRE MALKOVICH            |
| RALPH       | EMPIRE MALKOVICH            |
| ELLEN       | EMPIRE MALKOVICH            |
| SIDNEY      | EMPIRE MALKOVICH            |
| RICHARD     | EMPIRE MALKOVICH            |
| ZERO        | ENCINO ELF                  |
| KIRSTEN     | ENCINO ELF                  |
| BEN         | ENCINO ELF                  |
| JAMES       | ENCINO ELF                  |
| SYLVESTER   | ENCINO ELF                  |
| HARVEY      | ENCINO ELF                  |
| ALEC        | ENCOUNTERS CURTAIN          |
| ANNE        | ENCOUNTERS CURTAIN          |
| EWAN        | ENCOUNTERS CURTAIN          |
| MERYL       | ENCOUNTERS CURTAIN          |
| ZERO        | ENDING CROWDS               |
| BURT        | ENDING CROWDS               |
| MARY        | ENDING CROWDS               |
| SIDNEY      | ENDING CROWDS               |
| CHRISTOPHER | ENDING CROWDS               |
| VIVIEN      | ENEMY ODDS                  |
| LIZA        | ENEMY ODDS                  |
| EWAN        | ENEMY ODDS                  |
| BELA        | ENEMY ODDS                  |
| MENA        | ENGLISH BULWORTH            |
| PENELOPE    | ENGLISH BULWORTH            |
| MATTHEW     | ENGLISH BULWORTH            |
| JAYNE       | ENGLISH BULWORTH            |
| FAY         | ENGLISH BULWORTH            |
| JOHNNY      | ENOUGH RAGING               |
| SANDRA      | ENOUGH RAGING               |
| SEAN        | ENOUGH RAGING               |
| JULIANNE    | ENOUGH RAGING               |
| KEVIN       | ENOUGH RAGING               |
| RICHARD     | ENOUGH RAGING               |
| AL          | ENOUGH RAGING               |
| MATTHEW     | ENOUGH RAGING               |
| MICHAEL     | ENOUGH RAGING               |
| FRED        | ENTRAPMENT SATISFACTION     |
| WOODY       | ENTRAPMENT SATISFACTION     |
| FRANCES     | ENTRAPMENT SATISFACTION     |
| PENELOPE    | ENTRAPMENT SATISFACTION     |
| JOHNNY      | ESCAPE METROPOLIS           |
| NATALIE     | ESCAPE METROPOLIS           |
| FRANCES     | ESCAPE METROPOLIS           |
| ED          | ESCAPE METROPOLIS           |
| ED          | EVE RESURRECTION            |
| SUSAN       | EVE RESURRECTION            |
| SCARLETT    | EVE RESURRECTION            |
| KENNETH     | EVE RESURRECTION            |
| GENE        | EVE RESURRECTION            |
| ROCK        | EVE RESURRECTION            |
| GOLDIE      | EVERYONE CRAFT              |
| MICHELLE    | EVERYONE CRAFT              |
| WOODY       | EVERYONE CRAFT              |
| JAMES       | EVERYONE CRAFT              |
| MINNIE      | EVERYONE CRAFT              |
| ELVIS       | EVOLUTION ALTER             |
| RAY         | EVOLUTION ALTER             |
| ANGELA      | EVOLUTION ALTER             |
| GRETA       | EVOLUTION ALTER             |
| ED          | EVOLUTION ALTER             |
| BURT        | EVOLUTION ALTER             |
| GRACE       | EXCITEMENT EVE              |
| VIVIEN      | EXCITEMENT EVE              |
| SANDRA      | EXCITEMENT EVE              |
| PENELOPE    | EXCITEMENT EVE              |
| KENNETH     | EXCITEMENT EVE              |
| GINA        | EXCITEMENT EVE              |
| SUSAN       | EXCITEMENT EVE              |
| MORGAN      | EXCITEMENT EVE              |
| GOLDIE      | EXORCIST STING              |
| ANGELA      | EXORCIST STING              |
| KIM         | EXORCIST STING              |
| VIVIEN      | EXORCIST STING              |
| GREGORY     | EXORCIST STING              |
| ELVIS       | EXPECATIONS NATURAL         |
| DARYL       | EXPECATIONS NATURAL         |
| LAURENCE    | EXPECATIONS NATURAL         |
| FRANCES     | EXPENDABLE STALLION         |
| DUSTIN      | EXPENDABLE STALLION         |
| JAYNE       | EXPENDABLE STALLION         |
| FAY         | EXPENDABLE STALLION         |
| ALEC        | EXPRESS LONELY              |
| PARKER      | EXPRESS LONELY              |
| RIP         | EXPRESS LONELY              |
| SEAN        | EXPRESS LONELY              |
| MINNIE      | EXPRESS LONELY              |
| ALBERT      | EXPRESS LONELY              |
| OLYMPIA     | EXPRESS LONELY              |
| GREGORY     | EXPRESS LONELY              |
| HENRY       | EXTRAORDINARY CONQUERER     |
| MINNIE      | EXTRAORDINARY CONQUERER     |
| CHRIS       | EXTRAORDINARY CONQUERER     |
| LIZA        | EXTRAORDINARY CONQUERER     |
| FAY         | EXTRAORDINARY CONQUERER     |
| NICK        | EXTRAORDINARY CONQUERER     |
| RENEE       | EXTRAORDINARY CONQUERER     |
| DAN         | EYES DRIVING                |
| RENEE       | EYES DRIVING                |
| FAY         | EYES DRIVING                |
| MICHAEL     | EYES DRIVING                |
| JAYNE       | EYES DRIVING                |
| SISSY       | FACTORY DRAGON              |
| HENRY       | FACTORY DRAGON              |
| MAE         | FACTORY DRAGON              |
| CATE        | FACTORY DRAGON              |
| MERYL       | FACTORY DRAGON              |
| MENA        | FACTORY DRAGON              |
| MARY        | FALCON VOLUME               |
| KENNETH     | FALCON VOLUME               |
| SALMA       | FALCON VOLUME               |
| ED          | FALCON VOLUME               |
| SANDRA      | FAMILY SWEET                |
| PENELOPE    | FAMILY SWEET                |
| BURT        | FAMILY SWEET                |
| GROUCHO     | FAMILY SWEET                |
| DARYL       | FAMILY SWEET                |
| FAY         | FAMILY SWEET                |
| KENNETH     | FAMILY SWEET                |
| MATTHEW     | FAMILY SWEET                |
| DEBBIE      | FAMILY SWEET                |
| WARREN      | FANTASIA PARK               |
| HARRISON    | FANTASIA PARK               |
| GROUCHO     | FANTASIA PARK               |
| NATALIE     | FANTASY TROOPERS            |
| GREG        | FANTASY TROOPERS            |
| SEAN        | FANTASY TROOPERS            |
| IAN         | FANTASY TROOPERS            |
| GRETA       | FANTASY TROOPERS            |
| CHRISTOPHER | FANTASY TROOPERS            |
| JON         | FANTASY TROOPERS            |
| BELA        | FANTASY TROOPERS            |
| MARY        | FANTASY TROOPERS            |
| MICHELLE    | FARGO GANDHI                |
| SCARLETT    | FARGO GANDHI                |
| KENNETH     | FARGO GANDHI                |
| MORGAN      | FARGO GANDHI                |
| CHRISTOPHER | FARGO GANDHI                |
| MILLA       | FATAL HAUNTED               |
| JODIE       | FATAL HAUNTED               |
| ANGELA      | FATAL HAUNTED               |
| MORGAN      | FATAL HAUNTED               |
| FAY         | FATAL HAUNTED               |
| WILL        | FATAL HAUNTED               |
| MILLA       | FEATHERS METAL              |
| NATALIE     | FEATHERS METAL              |
| CHRISTIAN   | FEATHERS METAL              |
| KENNETH     | FEATHERS METAL              |
| WOODY       | FEATHERS METAL              |
| CHARLIZE    | FEATHERS METAL              |
| SCARLETT    | FEATHERS METAL              |
| JAYNE       | FEATHERS METAL              |
| NICK        | FEATHERS METAL              |
| MENA        | FELLOWSHIP AUTUMN           |
| FAY         | FELLOWSHIP AUTUMN           |
| DAN         | FELLOWSHIP AUTUMN           |
| CHRISTIAN   | FELLOWSHIP AUTUMN           |
| RAY         | FELLOWSHIP AUTUMN           |
| SALMA       | FELLOWSHIP AUTUMN           |
| CHRISTOPHER | FELLOWSHIP AUTUMN           |
| SISSY       | FERRIS MOTHER               |
| TIM         | FEUD FROGMEN                |
| TOM         | FEUD FROGMEN                |
| PENELOPE    | FEUD FROGMEN                |
| MARY        | FEUD FROGMEN                |
| HELEN       | FEVER EMPIRE                |
| FAY         | FEVER EMPIRE                |
| AUDREY      | FEVER EMPIRE                |
| KEVIN       | FICTION CHRISTMAS           |
| ALEC        | FICTION CHRISTMAS           |
| CUBA        | FICTION CHRISTMAS           |
| ADAM        | FICTION CHRISTMAS           |
| LISA        | FICTION CHRISTMAS           |
| MATTHEW     | FICTION CHRISTMAS           |
| ROCK        | FICTION CHRISTMAS           |
| MARY        | FICTION CHRISTMAS           |
| TIM         | FIDDLER LOST                |
| FRANCES     | FIDDLER LOST                |
| JAMES       | FIDDLER LOST                |
| SPENCER     | FIDDLER LOST                |
| DARYL       | FIDDLER LOST                |
| MEG         | FIDDLER LOST                |
| RUSSELL     | FIDDLER LOST                |
| SCARLETT    | FIDDLER LOST                |
| CATE        | FIDDLER LOST                |
| ANGELA      | FIDDLER LOST                |
| IAN         | FIDDLER LOST                |
| HELEN       | FIDELITY DEVIL              |
| PENELOPE    | FIDELITY DEVIL              |
| ALAN        | FIDELITY DEVIL              |
| RUSSELL     | FIDELITY DEVIL              |
| NICK        | FIGHT JAWBREAKER            |
| ALBERT      | FIGHT JAWBREAKER            |
| MERYL       | FIGHT JAWBREAKER            |
| FRANCES     | FINDING ANACONDA            |
| RIP         | FINDING ANACONDA            |
| MATTHEW     | FINDING ANACONDA            |
| SIDNEY      | FINDING ANACONDA            |
| CUBA        | FINDING ANACONDA            |
| JOHNNY      | FIRE WOLVES                 |
| CHRISTIAN   | FIRE WOLVES                 |
| WOODY       | FIRE WOLVES                 |
| RENEE       | FIRE WOLVES                 |
| RIVER       | FIRE WOLVES                 |
| VAL         | FIREBALL PHILADELPHIA       |
| JUDE        | FIREBALL PHILADELPHIA       |
| ADAM        | FIREBALL PHILADELPHIA       |
| JAMES       | FIREBALL PHILADELPHIA       |
| FRANCES     | FIREBALL PHILADELPHIA       |
| SANDRA      | FIREHOUSE VIETNAM           |
| MATTHEW     | FIREHOUSE VIETNAM           |
| FAY         | FIREHOUSE VIETNAM           |
| BEN         | FIREHOUSE VIETNAM           |
| OLYMPIA     | FIREHOUSE VIETNAM           |
| PARKER      | FISH OPUS                   |
| LAURENCE    | FISH OPUS                   |
| GOLDIE      | FLAMINGOS CONNECTICUT       |
| TOM         | FLAMINGOS CONNECTICUT       |
| FAY         | FLAMINGOS CONNECTICUT       |
| KENNETH     | FLAMINGOS CONNECTICUT       |
| GENE        | FLAMINGOS CONNECTICUT       |
| JANE        | FLAMINGOS CONNECTICUT       |
| RITA        | FLAMINGOS CONNECTICUT       |
| ALBERT      | FLAMINGOS CONNECTICUT       |
| JON         | FLAMINGOS CONNECTICUT       |
| NICK        | FLASH WARS                  |
| MATTHEW     | FLASH WARS                  |
| DAN         | FLASH WARS                  |
| KIRSTEN     | FLASH WARS                  |
| SANDRA      | FLASH WARS                  |
| MILLA       | FLASH WARS                  |
| GRETA       | FLASH WARS                  |
| NICK        | FLATLINERS KILLER           |
| GARY        | FLATLINERS KILLER           |
| KENNETH     | FLATLINERS KILLER           |
| JIM         | FLATLINERS KILLER           |
| RUSSELL     | FLATLINERS KILLER           |
| MORGAN      | FLATLINERS KILLER           |
| SCARLETT    | FLATLINERS KILLER           |
| MENA        | FLATLINERS KILLER           |
| ROCK        | FLATLINERS KILLER           |
| ALBERT      | FLINTSTONES HAPPINESS       |
| HUMPHREY    | FLINTSTONES HAPPINESS       |
| DEBBIE      | FLINTSTONES HAPPINESS       |
| BELA        | FLINTSTONES HAPPINESS       |
| RIP         | FLOATS GARDEN               |
| SEAN        | FLOATS GARDEN               |
| ELLEN       | FLOATS GARDEN               |
| JIM         | FLOATS GARDEN               |
| CAMERON     | FLOATS GARDEN               |
| CUBA        | FLYING HOOK                 |
| JOHNNY      | FLYING HOOK                 |
| WALTER      | FLYING HOOK                 |
| CATE        | FLYING HOOK                 |
| GRETA       | FLYING HOOK                 |
| GRETA       | FLYING HOOK                 |
| NICK        | FLYING HOOK                 |
| KENNETH     | FLYING HOOK                 |
| RIP         | FOOL MOCKINGBIRD            |
| NATALIE     | FOOL MOCKINGBIRD            |
| JADA        | FOREVER CANDIDATE           |
| ED          | FORREST SONS                |
| RIP         | FORREST SONS                |
| DARYL       | FORREST SONS                |
| WALTER      | FORREST SONS                |
| MARY        | FORREST SONS                |
| KIRK        | FORRESTER COMANCHEROS       |
| REESE       | FORRESTER COMANCHEROS       |
| SEAN        | FORRESTER COMANCHEROS       |
| RIP         | FORWARD TEMPLE              |
| SEAN        | FORWARD TEMPLE              |
| GREG        | FORWARD TEMPLE              |
| SCARLETT    | FRANKENSTEIN STRANGER       |
| BEN         | FRANKENSTEIN STRANGER       |
| TOM         | FREAKY POCUS                |
| MATTHEW     | FREAKY POCUS                |
| SIDNEY      | FREAKY POCUS                |
| KEVIN       | FREAKY POCUS                |
| FAY         | FREAKY POCUS                |
| JULIA       | FREDDY STORM                |
| HENRY       | FREDDY STORM                |
| WALTER      | FREDDY STORM                |
| CAMERON     | FREEDOM CLEOPATRA           |
| ALEC        | FREEDOM CLEOPATRA           |
| TOM         | FREEDOM CLEOPATRA           |
| RAY         | FREEDOM CLEOPATRA           |
| CHRISTOPHER | FREEDOM CLEOPATRA           |
| ED          | FRENCH HOLIDAY              |
| AUDREY      | FRENCH HOLIDAY              |
| JODIE       | FRENCH HOLIDAY              |
| DAN         | FRENCH HOLIDAY              |
| CATE        | FRENCH HOLIDAY              |
| WILL        | FRENCH HOLIDAY              |
| HUMPHREY    | FRENCH HOLIDAY              |
| UMA         | FRIDA SLIPPER               |
| JAYNE       | FRIDA SLIPPER               |
| MINNIE      | FRIDA SLIPPER               |
| KENNETH     | FRIDA SLIPPER               |
| RENEE       | FRIDA SLIPPER               |
| TOM         | FRISCO FORREST              |
| ANGELA      | FRISCO FORREST              |
| KIRSTEN     | FRISCO FORREST              |
| GINA        | FRISCO FORREST              |
| DAN         | FRISCO FORREST              |
| LIZA        | FRISCO FORREST              |
| ALBERT      | FRISCO FORREST              |
| RICHARD     | FRISCO FORREST              |
| ROCK        | FRISCO FORREST              |
| BEN         | FROGMEN BREAKING            |
| ELLEN       | FROGMEN BREAKING            |
| MORGAN      | FROGMEN BREAKING            |
| RIVER       | FROGMEN BREAKING            |
| RUSSELL     | FROGMEN BREAKING            |
| LAURENCE    | FROGMEN BREAKING            |
| JOHNNY      | FRONTIER CABIN              |
| RIP         | FRONTIER CABIN              |
| FAY         | FRONTIER CABIN              |
| JUDE        | FRONTIER CABIN              |
| BEN         | FRONTIER CABIN              |
| HARVEY      | FRONTIER CABIN              |
| ED          | FROST HEAD                  |
| CARMEN      | FROST HEAD                  |
| RALPH       | FROST HEAD                  |
| GENE        | FROST HEAD                  |
| CATE        | FROST HEAD                  |
| FAY         | FROST HEAD                  |
| LAURENCE    | FROST HEAD                  |
| CUBA        | FUGITIVE MAGUIRE            |
| ALEC        | FUGITIVE MAGUIRE            |
| MARY        | FUGITIVE MAGUIRE            |
| RALPH       | FUGITIVE MAGUIRE            |
| CHARLIZE    | FUGITIVE MAGUIRE            |
| MEG         | FUGITIVE MAGUIRE            |
| RICHARD     | FUGITIVE MAGUIRE            |
| EMILY       | FUGITIVE MAGUIRE            |
| GEOFFREY    | FUGITIVE MAGUIRE            |
| LAURA       | FUGITIVE MAGUIRE            |
| OLYMPIA     | FUGITIVE MAGUIRE            |
| MICHELLE    | FULL FLATLINERS             |
| CARY        | FULL FLATLINERS             |
| RALPH       | FULL FLATLINERS             |
| SUSAN       | FULL FLATLINERS             |
| SCARLETT    | FULL FLATLINERS             |
| LAURA       | FULL FLATLINERS             |
| KARL        | FURY MURDER                 |
| KIRK        | FURY MURDER                 |
| WOODY       | FURY MURDER                 |
| LAURA       | FURY MURDER                 |
| FRED        | GABLES METROPOLIS           |
| RIP         | GABLES METROPOLIS           |
| FRANCES     | GABLES METROPOLIS           |
| RAY         | GABLES METROPOLIS           |
| GROUCHO     | GABLES METROPOLIS           |
| CATE        | GABLES METROPOLIS           |
| ADAM        | GABLES METROPOLIS           |
| GROUCHO     | GABLES METROPOLIS           |
| UMA         | GALAXY SWEETHEARTS          |
| DEBBIE      | GALAXY SWEETHEARTS          |
| THORA       | GALAXY SWEETHEARTS          |
| JULIA       | GAMES BOWFINGER             |
| ANGELA      | GAMES BOWFINGER             |
| RIP         | GAMES BOWFINGER             |
| BURT        | GAMES BOWFINGER             |
| MATTHEW     | GAMES BOWFINGER             |
| FRANCES     | GAMES BOWFINGER             |
| HUMPHREY    | GAMES BOWFINGER             |
| MARY        | GAMES BOWFINGER             |
| ZERO        | GANDHI KWAI                 |
| LUCILLE     | GANDHI KWAI                 |
| ANNE        | GANDHI KWAI                 |
| PENELOPE    | GANDHI KWAI                 |
| ANGELINA    | GANDHI KWAI                 |
| MEG         | GANDHI KWAI                 |
| GINA        | GANDHI KWAI                 |
| DARYL       | GANDHI KWAI                 |
| ELVIS       | GANGS PRIDE                 |
| FRANCES     | GANGS PRIDE                 |
| FAY         | GANGS PRIDE                 |
| KENNETH     | GANGS PRIDE                 |
| MARY        | GARDEN ISLAND               |
| WARREN      | GARDEN ISLAND               |
| JADA        | GARDEN ISLAND               |
| GRACE       | GASLIGHT CRUSADE            |
| JULIA       | GASLIGHT CRUSADE            |
| WALTER      | GASLIGHT CRUSADE            |
| RICHARD     | GASLIGHT CRUSADE            |
| FAY         | GASLIGHT CRUSADE            |
| MICHAEL     | GATHERING CALENDAR          |
| BURT        | GATHERING CALENDAR          |
| MERYL       | GATHERING CALENDAR          |
| TOM         | GENTLEMEN STAGE             |
| DARYL       | GENTLEMEN STAGE             |
| MORGAN      | GENTLEMEN STAGE             |
| LIZA        | GENTLEMEN STAGE             |
| RITA        | GENTLEMEN STAGE             |
| GRETA       | GENTLEMEN STAGE             |
| HARVEY      | GENTLEMEN STAGE             |
| ED          | GENTLEMEN STAGE             |
| DAN         | GHOST GROUNDHOG             |
| KENNETH     | GHOST GROUNDHOG             |
| KEVIN       | GHOST GROUNDHOG             |
| RUSSELL     | GHOST GROUNDHOG             |
| RENEE       | GHOST GROUNDHOG             |
| JENNIFER    | GHOSTBUSTERS ELF            |
| MATTHEW     | GIANT TROOPERS              |
| NICK        | GILBERT PELICAN             |
| SANDRA      | GILBERT PELICAN             |
| RIP         | GILBERT PELICAN             |
| RITA        | GILBERT PELICAN             |
| WOODY       | GILMORE BOILED              |
| MENA        | GILMORE BOILED              |
| MEG         | GILMORE BOILED              |
| CATE        | GILMORE BOILED              |
| MENA        | GILMORE BOILED              |
| BURT        | GILMORE BOILED              |
| JULIA       | GLADIATOR WESTWARD          |
| KIRK        | GLADIATOR WESTWARD          |
| ADAM        | GLADIATOR WESTWARD          |
| CAMERON     | GLADIATOR WESTWARD          |
| IAN         | GLADIATOR WESTWARD          |
| JAYNE       | GLADIATOR WESTWARD          |
| MATTHEW     | GLASS DYING                 |
| SUSAN       | GLASS DYING                 |
| AL          | GLASS DYING                 |
| MICHAEL     | GLASS DYING                 |
| PENELOPE    | GLEAMING JAWBREAKER         |
| MARY        | GLEAMING JAWBREAKER         |
| ALBERT      | GLEAMING JAWBREAKER         |
| RIVER       | GLEAMING JAWBREAKER         |
| IAN         | GLEAMING JAWBREAKER         |
| NICK        | GLEAMING JAWBREAKER         |
| JOHN        | GLEAMING JAWBREAKER         |
| JAYNE       | GLEAMING JAWBREAKER         |
| CHRISTIAN   | GLORY TRACY                 |
| ADAM        | GLORY TRACY                 |
| RALPH       | GLORY TRACY                 |
| RUSSELL     | GLORY TRACY                 |
| WILLIAM     | GLORY TRACY                 |
| DEBBIE      | GLORY TRACY                 |
| SEAN        | GO PURPLE                   |
| SALMA       | GO PURPLE                   |
| GENE        | GO PURPLE                   |
| ZERO        | GODFATHER DIARY             |
| GREG        | GODFATHER DIARY             |
| RITA        | GODFATHER DIARY             |
| ED          | GODFATHER DIARY             |
| LAURA       | GODFATHER DIARY             |
| REESE       | GODFATHER DIARY             |
| GROUCHO     | GOLD RIVER                  |
| RUSSELL     | GOLD RIVER                  |
| CHRISTIAN   | GOLDFINGER SENSIBILITY      |
| LUCILLE     | GOLDFINGER SENSIBILITY      |
| KEVIN       | GOLDFINGER SENSIBILITY      |
| NICK        | GOLDFINGER SENSIBILITY      |
| SANDRA      | GOLDMINE TYCOON             |
| MAE         | GOLDMINE TYCOON             |
| ALBERT      | GOLDMINE TYCOON             |
| DARYL       | GOLDMINE TYCOON             |
| GEOFFREY    | GOLDMINE TYCOON             |
| HUMPHREY    | GOLDMINE TYCOON             |
| JOHN        | GOLDMINE TYCOON             |
| SISSY       | GONE TROUBLE                |
| RICHARD     | GONE TROUBLE                |
| EMILY       | GONE TROUBLE                |
| CHRIS       | GONE TROUBLE                |
| GROUCHO     | GONE TROUBLE                |
| NICK        | GOODFELLAS SALUTE           |
| JOHNNY      | GOODFELLAS SALUTE           |
| ELVIS       | GOODFELLAS SALUTE           |
| BEN         | GOODFELLAS SALUTE           |
| GINA        | GOODFELLAS SALUTE           |
| SUSAN       | GOODFELLAS SALUTE           |
| FRANCES     | GOODFELLAS SALUTE           |
| REESE       | GOODFELLAS SALUTE           |
| VIVIEN      | GORGEOUS BINGO              |
| SANDRA      | GORGEOUS BINGO              |
| MEG         | GORGEOUS BINGO              |
| FRANCES     | GORGEOUS BINGO              |
| WHOOPI      | GORGEOUS BINGO              |
| GEOFFREY    | GORGEOUS BINGO              |
| REESE       | GORGEOUS BINGO              |
| ANGELA      | GOSFORD DONNIE              |
| JADA        | GOSFORD DONNIE              |
| HUMPHREY    | GOSFORD DONNIE              |
| NATALIE     | GRACELAND DYNAMITE          |
| CHRISTIAN   | GRACELAND DYNAMITE          |
| BURT        | GRACELAND DYNAMITE          |
| SIDNEY      | GRACELAND DYNAMITE          |
| ALBERT      | GRACELAND DYNAMITE          |
| KENNETH     | GRACELAND DYNAMITE          |
| EWAN        | GRADUATE LORD               |
| WHOOPI      | GRADUATE LORD               |
| JOHNNY      | GRAFFITI LOVE               |
| CHRISTIAN   | GRAFFITI LOVE               |
| KENNETH     | GRAFFITI LOVE               |
| GARY        | GRAFFITI LOVE               |
| SEAN        | GRAFFITI LOVE               |
| AUDREY      | GRAFFITI LOVE               |
| JOHNNY      | GRAIL FRANKENSTEIN          |
| JAYNE       | GRAIL FRANKENSTEIN          |
| DARYL       | GRAIL FRANKENSTEIN          |
| GRETA       | GRAIL FRANKENSTEIN          |
| AL          | GRAIL FRANKENSTEIN          |
| CARMEN      | GRAPES FURY                 |
| HENRY       | GRAPES FURY                 |
| MARY        | GRAPES FURY                 |
| LUCILLE     | GRAPES FURY                 |
| BURT        | GRAPES FURY                 |
| KIRK        | GREASE YOUTH                |
| SIDNEY      | GREASE YOUTH                |
| ADAM        | GREASE YOUTH                |
| HELEN       | GREATEST NORTH              |
| RIP         | GREATEST NORTH              |
| MATTHEW     | GREATEST NORTH              |
| WARREN      | GREATEST NORTH              |
| CUBA        | GREATEST NORTH              |
| GREGORY     | GREATEST NORTH              |
| JENNIFER    | GREEDY ROOTS                |
| GARY        | GREEDY ROOTS                |
| WARREN      | GREEDY ROOTS                |
| HARRISON    | GREEDY ROOTS                |
| FAY         | GREEDY ROOTS                |
| ALAN        | GREEDY ROOTS                |
| RENEE       | GREEDY ROOTS                |
| MARY        | GREEDY ROOTS                |
| SISSY       | GREEK EVERYONE              |
| BURT        | GREEK EVERYONE              |
| RIP         | GREEK EVERYONE              |
| CATE        | GREEK EVERYONE              |
| UMA         | GRINCH MASSAGE              |
| BURT        | GRINCH MASSAGE              |
| KIRSTEN     | GRINCH MASSAGE              |
| JIM         | GRINCH MASSAGE              |
| WARREN      | GRINCH MASSAGE              |
| MATTHEW     | GRINCH MASSAGE              |
| CAMERON     | GRIT CLOCKWORK              |
| KEVIN       | GRIT CLOCKWORK              |
| GEOFFREY    | GRIT CLOCKWORK              |
| JOHNNY      | GROOVE FICTION              |
| JODIE       | GROOVE FICTION              |
| DAN         | GROOVE FICTION              |
| MINNIE      | GROOVE FICTION              |
| HARRISON    | GROOVE FICTION              |
| JANE        | GROOVE FICTION              |
| IAN         | GROOVE FICTION              |
| SEAN        | GROSSE WONDERFUL            |
| DAN         | GROSSE WONDERFUL            |
| CUBA        | GROSSE WONDERFUL            |
| ALBERT      | GROSSE WONDERFUL            |
| UMA         | GROUNDHOG UNCUT             |
| JULIA       | GROUNDHOG UNCUT             |
| JAYNE       | GROUNDHOG UNCUT             |
| ADAM        | GROUNDHOG UNCUT             |
| SEAN        | GROUNDHOG UNCUT             |
| RICHARD     | GROUNDHOG UNCUT             |
| GROUCHO     | GROUNDHOG UNCUT             |
| DAN         | GUMP DATE                   |
| MENA        | GUMP DATE                   |
| RIP         | GUMP DATE                   |
| GENE        | GUMP DATE                   |
| RIVER       | GUMP DATE                   |
| JAYNE       | GUMP DATE                   |
| BURT        | GUN BONNIE                  |
| GROUCHO     | GUN BONNIE                  |
| IAN         | GUN BONNIE                  |
| WILL        | GUN BONNIE                  |
| MATTHEW     | GUN BONNIE                  |
| CARMEN      | GUNFIGHT MOON               |
| GINA        | GUNFIGHT MOON               |
| KEVIN       | GUNFIGHT MOON               |
| RUSSELL     | GUNFIGHT MOON               |
| AUDREY      | GUNFIGHTER MUSSOLINI        |
| JUDY        | GUNFIGHTER MUSSOLINI        |
| SCARLETT    | GUNFIGHTER MUSSOLINI        |
| RUSSELL     | GUNFIGHTER MUSSOLINI        |
| RIP         | GUYS FALCON                 |
| BURT        | GUYS FALCON                 |
| RICHARD     | GUYS FALCON                 |
| MORGAN      | GUYS FALCON                 |
| RUSSELL     | GUYS FALCON                 |
| ANNE        | HALF OUTFIELD               |
| GREG        | HALF OUTFIELD               |
| SEAN        | HALF OUTFIELD               |
| HARRISON    | HALF OUTFIELD               |
| DARYL       | HALF OUTFIELD               |
| DEBBIE      | HALF OUTFIELD               |
| JOHNNY      | HALL CASSIDY                |
| RIP         | HALL CASSIDY                |
| CAMERON     | HALL CASSIDY                |
| GINA        | HALL CASSIDY                |
| JAYNE       | HALL CASSIDY                |
| ED          | HALLOWEEN NUTS              |
| AUDREY      | HALLOWEEN NUTS              |
| JUDE        | HALLOWEEN NUTS              |
| JAYNE       | HALLOWEEN NUTS              |
| GROUCHO     | HALLOWEEN NUTS              |
| SYLVESTER   | HALLOWEEN NUTS              |
| ANGELA      | HALLOWEEN NUTS              |
| JOHNNY      | HAMLET WISDOM               |
| PENELOPE    | HAMLET WISDOM               |
| WARREN      | HAMLET WISDOM               |
| FAY         | HAMLET WISDOM               |
| CHRISTOPHER | HAMLET WISDOM               |
| ZERO        | HANDICAP BOONDOCK           |
| GARY        | HANDICAP BOONDOCK           |
| RENEE       | HANDICAP BOONDOCK           |
| ALBERT      | HANDICAP BOONDOCK           |
| CATE        | HANDICAP BOONDOCK           |
| AL          | HANDICAP BOONDOCK           |
| MARY        | HANDICAP BOONDOCK           |
| MATTHEW     | HANGING DEEP                |
| JOHNNY      | HANGING DEEP                |
| RIP         | HANGING DEEP                |
| KENNETH     | HANGING DEEP                |
| ANGELA      | HANGING DEEP                |
| MERYL       | HANGING DEEP                |
| ROCK        | HANGING DEEP                |
| RICHARD     | HANKY OCTOBER               |
| OLYMPIA     | HANKY OCTOBER               |
| LISA        | HANKY OCTOBER               |
| JENNIFER    | HANOVER GALAXY              |
| KIRSTEN     | HANOVER GALAXY              |
| JULIA       | HANOVER GALAXY              |
| JAYNE       | HANOVER GALAXY              |
| ANGELA      | HANOVER GALAXY              |
| SCARLETT    | HANOVER GALAXY              |
| KENNETH     | HANOVER GALAXY              |
| NICK        | HAPPINESS UNITED            |
| ADAM        | HAPPINESS UNITED            |
| GROUCHO     | HAPPINESS UNITED            |
| CUBA        | HAPPINESS UNITED            |
| MERYL       | HAPPINESS UNITED            |
| KARL        | HARDLY ROBBERS              |
| ANNE        | HARDLY ROBBERS              |
| GRETA       | HARDLY ROBBERS              |
| TIM         | HAROLD FRENCH               |
| NATALIE     | HAROLD FRENCH               |
| PENELOPE    | HAROLD FRENCH               |
| ED          | HAROLD FRENCH               |
| HARVEY      | HAROLD FRENCH               |
| JON         | HAROLD FRENCH               |
| GENE        | HAROLD FRENCH               |
| KENNETH     | HARPER DYING                |
| KIM         | HARPER DYING                |
| ALBERT      | HARPER DYING                |
| FAY         | HARPER DYING                |
| FAY         | HARRY IDAHO                 |
| CAMERON     | HARRY IDAHO                 |
| MORGAN      | HARRY IDAHO                 |
| LUCILLE     | HARRY IDAHO                 |
| MATTHEW     | HARRY IDAHO                 |
| JAYNE       | HARRY IDAHO                 |
| BOB         | HATE HANDICAP               |
| KEVIN       | HATE HANDICAP               |
| RIVER       | HATE HANDICAP               |
| CAMERON     | HAUNTED ANTITRUST           |
| SEAN        | HAUNTED ANTITRUST           |
| FAY         | HAUNTED ANTITRUST           |
| ALAN        | HAUNTED ANTITRUST           |
| WILLIAM     | HAUNTED ANTITRUST           |
| JAYNE       | HAUNTING PIANIST            |
| CHARLIZE    | HAUNTING PIANIST            |
| SEAN        | HAUNTING PIANIST            |
| GRETA       | HAUNTING PIANIST            |
| MARY        | HAUNTING PIANIST            |
| REESE       | HAWK CHILL                  |
| PARKER      | HAWK CHILL                  |
| ANNE        | HAWK CHILL                  |
| CARMEN      | HAWK CHILL                  |
| CAMERON     | HAWK CHILL                  |
| CATE        | HAWK CHILL                  |
| IAN         | HAWK CHILL                  |
| GARY        | HEAD STRANGER               |
| JESSICA     | HEAD STRANGER               |
| GINA        | HEARTBREAKERS BRIGHT        |
| KIM         | HEARTBREAKERS BRIGHT        |
| OPRAH       | HEARTBREAKERS BRIGHT        |
| CHRISTOPHER | HEARTBREAKERS BRIGHT        |
| MATTHEW     | HEARTBREAKERS BRIGHT        |
| BURT        | HEAVEN FREEDOM              |
| KIRK        | HEAVEN FREEDOM              |
| CHARLIZE    | HEAVEN FREEDOM              |
| ADAM        | HEAVEN FREEDOM              |
| RICHARD     | HEAVEN FREEDOM              |
| MORGAN      | HEAVEN FREEDOM              |
| ALBERT      | HEAVEN FREEDOM              |
| FAY         | HEAVEN FREEDOM              |
| OPRAH       | HEAVEN FREEDOM              |
| GREGORY     | HEAVEN FREEDOM              |
| JOHNNY      | HEAVENLY GUN                |
| KEVIN       | HEAVENLY GUN                |
| SPENCER     | HEAVENLY GUN                |
| KEVIN       | HEAVENLY GUN                |
| MICHAEL     | HEAVENLY GUN                |
| AUDREY      | HEAVENLY GUN                |
| BEN         | HEAVYWEIGHTS BEAST          |
| DAN         | HEAVYWEIGHTS BEAST          |
| WARREN      | HEAVYWEIGHTS BEAST          |
| ROCK        | HEAVYWEIGHTS BEAST          |
| BURT        | HEAVYWEIGHTS BEAST          |
| JAYNE       | HEDWIG ALTER                |
| JAMES       | HEDWIG ALTER                |
| GENE        | HEDWIG ALTER                |
| DEBBIE      | HEDWIG ALTER                |
| GRACE       | HELLFIGHTERS SIERRA         |
| CUBA        | HELLFIGHTERS SIERRA         |
| SANDRA      | HELLFIGHTERS SIERRA         |
| MICHELLE    | HELLFIGHTERS SIERRA         |
| JAMES       | HELLFIGHTERS SIERRA         |
| JIM         | HELLFIGHTERS SIERRA         |
| SPENCER     | HELLFIGHTERS SIERRA         |
| CAMERON     | HELLFIGHTERS SIERRA         |
| PENELOPE    | HELLFIGHTERS SIERRA         |
| ALBERT      | HELLFIGHTERS SIERRA         |
| ED          | HELLFIGHTERS SIERRA         |
| HARVEY      | HELLFIGHTERS SIERRA         |
| VIVIEN      | HIGH ENCINO                 |
| JULIA       | HIGH ENCINO                 |
| GOLDIE      | HIGH ENCINO                 |
| MILLA       | HIGH ENCINO                 |
| OPRAH       | HIGH ENCINO                 |
| ED          | HIGH ENCINO                 |
| MERYL       | HIGH ENCINO                 |
| KARL        | HIGHBALL POTTER             |
| REESE       | HIGHBALL POTTER             |
| CHRISTOPHER | HIGHBALL POTTER             |
| GRETA       | HIGHBALL POTTER             |
| MENA        | HIGHBALL POTTER             |
| VIVIEN      | HILLS NEIGHBORS             |
| NATALIE     | HILLS NEIGHBORS             |
| DAN         | HILLS NEIGHBORS             |
| CHRISTIAN   | HILLS NEIGHBORS             |
| JON         | HILLS NEIGHBORS             |
| RENEE       | HILLS NEIGHBORS             |
| VIVIEN      | HOBBIT ALIEN                |
| ELVIS       | HOBBIT ALIEN                |
| DUSTIN      | HOBBIT ALIEN                |
| WALTER      | HOBBIT ALIEN                |
| WARREN      | HOBBIT ALIEN                |
| DARYL       | HOBBIT ALIEN                |
| LAURA       | HOBBIT ALIEN                |
| REESE       | HOBBIT ALIEN                |
| SANDRA      | HOCUS FRIDA                 |
| FRANCES     | HOCUS FRIDA                 |
| THORA       | HOCUS FRIDA                 |
| KARL        | HOLES BRANNIGAN             |
| KEVIN       | HOLES BRANNIGAN             |
| NICK        | HOLES BRANNIGAN             |
| NATALIE     | HOLES BRANNIGAN             |
| GARY        | HOLES BRANNIGAN             |
| DARYL       | HOLES BRANNIGAN             |
| MORGAN      | HOLES BRANNIGAN             |
| DAN         | HOLES BRANNIGAN             |
| ED          | HOLES BRANNIGAN             |
| MATTHEW     | HOLES BRANNIGAN             |
| GREGORY     | HOLES BRANNIGAN             |
| DAN         | HOLIDAY GAMES               |
| MINNIE      | HOLIDAY GAMES               |
| SPENCER     | HOLIDAY GAMES               |
| MERYL       | HOLIDAY GAMES               |
| AL          | HOLIDAY GAMES               |
| DEBBIE      | HOLIDAY GAMES               |
| EMILY       | HOLLOW JEOPARDY             |
| JULIA       | HOLLOW JEOPARDY             |
| ANNE        | HOLLYWOOD ANONYMOUS         |
| HENRY       | HOLLYWOOD ANONYMOUS         |
| CHRISTIAN   | HOLLYWOOD ANONYMOUS         |
| RENEE       | HOLLYWOOD ANONYMOUS         |
| GROUCHO     | HOLLYWOOD ANONYMOUS         |
| BELA        | HOLLYWOOD ANONYMOUS         |
| CARMEN      | HOLOCAUST HIGHBALL          |
| MARY        | HOLOCAUST HIGHBALL          |
| DARYL       | HOLOCAUST HIGHBALL          |
| PENELOPE    | HOLOCAUST HIGHBALL          |
| WILLIAM     | HOLOCAUST HIGHBALL          |
| GOLDIE      | HOLY TADPOLE                |
| MORGAN      | HOLY TADPOLE                |
| HARVEY      | HOLY TADPOLE                |
| KIRSTEN     | HOME PITY                   |
| BURT        | HOME PITY                   |
| CHRISTIAN   | HOME PITY                   |
| NICK        | HOME PITY                   |
| AUDREY      | HOME PITY                   |
| JOHN        | HOME PITY                   |
| UMA         | HOMEWARD CIDER              |
| TIM         | HOMEWARD CIDER              |
| BURT        | HOMEWARD CIDER              |
| ELLEN       | HOMEWARD CIDER              |
| ALBERT      | HOMEWARD CIDER              |
| IAN         | HOMEWARD CIDER              |
| MICHAEL     | HOMEWARD CIDER              |
| BOB         | HOMICIDE PEACH              |
| FRANCES     | HOMICIDE PEACH              |
| JAYNE       | HOMICIDE PEACH              |
| GROUCHO     | HOMICIDE PEACH              |
| MAE         | HOMICIDE PEACH              |
| KENNETH     | HOMICIDE PEACH              |
| HARRISON    | HOMICIDE PEACH              |
| ALBERT      | HOMICIDE PEACH              |
| ZERO        | HONEY TIES                  |
| KIRSTEN     | HONEY TIES                  |
| JULIANNE    | HONEY TIES                  |
| ALBERT      | HONEY TIES                  |
| ALBERT      | HONEY TIES                  |
| ELVIS       | HOOK CHARIOTS               |
| MAE         | HOOK CHARIOTS               |
| GENE        | HOOK CHARIOTS               |
| GINA        | HOOK CHARIOTS               |
| SISSY       | HOOSIERS BIRDCAGE           |
| TIM         | HOOSIERS BIRDCAGE           |
| GOLDIE      | HOOSIERS BIRDCAGE           |
| DARYL       | HOOSIERS BIRDCAGE           |
| WALTER      | HOOSIERS BIRDCAGE           |
| DARYL       | HOOSIERS BIRDCAGE           |
| GRETA       | HOOSIERS BIRDCAGE           |
| FAY         | HOOSIERS BIRDCAGE           |
| GRETA       | HOOSIERS BIRDCAGE           |
| HUMPHREY    | HOOSIERS BIRDCAGE           |
| GREG        | HOPE TOOTSIE                |
| RENEE       | HOPE TOOTSIE                |
| JANE        | HOPE TOOTSIE                |
| JULIA       | HOPE TOOTSIE                |
| ZERO        | HORN WORKING                |
| ANNE        | HORN WORKING                |
| CHRISTIAN   | HORN WORKING                |
| SEAN        | HORN WORKING                |
| MORGAN      | HORN WORKING                |
| JAYNE       | HORN WORKING                |
| WILL        | HORN WORKING                |
| GENE        | HORN WORKING                |
| JOE         | HORROR REIGN                |
| NICK        | HORROR REIGN                |
| MARY        | HORROR REIGN                |
| CHRISTOPHER | HORROR REIGN                |
| KENNETH     | HORROR REIGN                |
| SANDRA      | HOTEL HAPPINESS             |
| RIP         | HOTEL HAPPINESS             |
| SUSAN       | HOTEL HAPPINESS             |
| RENEE       | HOTEL HAPPINESS             |
| ALEC        | HOURS RAGE                  |
| HENRY       | HOURS RAGE                  |
| BURT        | HOURS RAGE                  |
| RALPH       | HOURS RAGE                  |
| KIRSTEN     | HOURS RAGE                  |
| JANE        | HOURS RAGE                  |
| NATALIE     | HOUSE DYNAMITE              |
| JUDE        | HOUSE DYNAMITE              |
| MEG         | HOUSE DYNAMITE              |
| MATTHEW     | HOUSE DYNAMITE              |
| VIVIEN      | HOUSE DYNAMITE              |
| AL          | HOUSE DYNAMITE              |
| MATTHEW     | HOUSE DYNAMITE              |
| DEBBIE      | HOUSE DYNAMITE              |
| MICHAEL     | HOUSE DYNAMITE              |
| PENELOPE    | HUMAN GRAFFITI              |
| FRED        | HUMAN GRAFFITI              |
| AUDREY      | HUMAN GRAFFITI              |
| WILL        | HUMAN GRAFFITI              |
| GROUCHO     | HUNCHBACK IMPOSSIBLE        |
| WILLIAM     | HUNCHBACK IMPOSSIBLE        |
| MERYL       | HUNGER ROOF                 |
| ED          | HUNTER ALTER                |
| JON         | HUNTER ALTER                |
| JEFF        | HUNTER ALTER                |
| RENEE       | HUNTER ALTER                |
| CARY        | HUNTING MUSKETEERS          |
| SEAN        | HUNTING MUSKETEERS          |
| JULIANNE    | HUNTING MUSKETEERS          |
| MICHAEL     | HUNTING MUSKETEERS          |
| WILLIAM     | HUNTING MUSKETEERS          |
| KIRSTEN     | HURRICANE AFFAIR            |
| RUSSELL     | HURRICANE AFFAIR            |
| FAY         | HURRICANE AFFAIR            |
| ALEC        | HUSTLER PARTY               |
| ANGELINA    | HUSTLER PARTY               |
| MINNIE      | HUSTLER PARTY               |
| CHRISTOPHER | HUSTLER PARTY               |
| CUBA        | HYDE DOCTOR                 |
| LUCILLE     | HYDE DOCTOR                 |
| JAYNE       | HYDE DOCTOR                 |
| BURT        | HYDE DOCTOR                 |
| ELLEN       | HYDE DOCTOR                 |
| GINA        | HYDE DOCTOR                 |
| BURT        | HYSTERICAL GRAIL            |
| MINNIE      | HYSTERICAL GRAIL            |
| CHARLIZE    | HYSTERICAL GRAIL            |
| MEG         | HYSTERICAL GRAIL            |
| WALTER      | HYSTERICAL GRAIL            |
| JULIANNE    | HYSTERICAL GRAIL            |
| MORGAN      | HYSTERICAL GRAIL            |
| LUCILLE     | HYSTERICAL GRAIL            |
| JAYNE       | HYSTERICAL GRAIL            |
| MENA        | ICE CROSSING                |
| JUDE        | ICE CROSSING                |
| CHRISTOPHER | ICE CROSSING                |
| EWAN        | ICE CROSSING                |
| JAYNE       | ICE CROSSING                |
| OLYMPIA     | ICE CROSSING                |
| TOM         | IDAHO LOVE                  |
| PARKER      | IDAHO LOVE                  |
| RAY         | IDAHO LOVE                  |
| FAY         | IDAHO LOVE                  |
| HUMPHREY    | IDAHO LOVE                  |
| MICHAEL     | IDAHO LOVE                  |
| SANDRA      | IDENTITY LOVER              |
| ALEC        | IDENTITY LOVER              |
| LIZA        | IDENTITY LOVER              |
| SCARLETT    | IDENTITY LOVER              |
| TOM         | IDOLS SNATCHERS             |
| ADAM        | IDOLS SNATCHERS             |
| SEAN        | IDOLS SNATCHERS             |
| RUSSELL     | IDOLS SNATCHERS             |
| ALBERT      | IDOLS SNATCHERS             |
| JANE        | IDOLS SNATCHERS             |
| OLYMPIA     | IDOLS SNATCHERS             |
| MARY        | IDOLS SNATCHERS             |
| BETTE       | IGBY MAKER                  |
| SEAN        | IGBY MAKER                  |
| DAN         | IGBY MAKER                  |
| GEOFFREY    | IGBY MAKER                  |
| MICHAEL     | IGBY MAKER                  |
| KENNETH     | ILLUSION AMELIE             |
| GENE        | ILLUSION AMELIE             |
| MORGAN      | ILLUSION AMELIE             |
| DARYL       | ILLUSION AMELIE             |
| GRETA       | ILLUSION AMELIE             |
| RICHARD     | ILLUSION AMELIE             |
| HUMPHREY    | ILLUSION AMELIE             |
| ED          | IMAGE PRINCESS              |
| ZERO        | IMAGE PRINCESS              |
| FRED        | IMAGE PRINCESS              |
| BURT        | IMAGE PRINCESS              |
| MICHELLE    | IMAGE PRINCESS              |
| SCARLETT    | IMAGE PRINCESS              |
| WOODY       | IMAGE PRINCESS              |
| KIRSTEN     | IMAGE PRINCESS              |
| ELLEN       | IMAGE PRINCESS              |
| GRETA       | IMAGE PRINCESS              |
| LUCILLE     | IMAGE PRINCESS              |
| VIVIEN      | IMPACT ALADDIN              |
| GINA        | IMPACT ALADDIN              |
| WARREN      | IMPACT ALADDIN              |
| FRED        | IMPOSSIBLE PREJUDICE        |
| RITA        | IMPOSSIBLE PREJUDICE        |
| CHRIS       | IMPOSSIBLE PREJUDICE        |
| UMA         | INCH JET                    |
| FRED        | INCH JET                    |
| GOLDIE      | INCH JET                    |
| PARKER      | INCH JET                    |
| MATTHEW     | INCH JET                    |
| KARL        | INDEPENDENCE HOTEL          |
| HELEN       | INDEPENDENCE HOTEL          |
| DAN         | INDEPENDENCE HOTEL          |
| JAYNE       | INDEPENDENCE HOTEL          |
| GROUCHO     | INDEPENDENCE HOTEL          |
| KENNETH     | INDEPENDENCE HOTEL          |
| GROUCHO     | INDEPENDENCE HOTEL          |
| RIVER       | INDEPENDENCE HOTEL          |
| KIM         | INDEPENDENCE HOTEL          |
| NICK        | INDIAN LOVE                 |
| MATTHEW     | INDIAN LOVE                 |
| TOM         | INDIAN LOVE                 |
| CARY        | INDIAN LOVE                 |
| SCARLETT    | INDIAN LOVE                 |
| GINA        | INDIAN LOVE                 |
| RITA        | INDIAN LOVE                 |
| RUSSELL     | INDIAN LOVE                 |
| JON         | INDIAN LOVE                 |
| GENE        | INDIAN LOVE                 |
| RENEE       | INFORMER DOUBLE             |
| KEVIN       | INFORMER DOUBLE             |
| IAN         | INFORMER DOUBLE             |
| DAN         | INNOCENT USUAL              |
| CHRISTIAN   | INNOCENT USUAL              |
| JAMES       | INNOCENT USUAL              |
| GARY        | INSECTS STONE               |
| MINNIE      | INSECTS STONE               |
| JON         | INSECTS STONE               |
| GREGORY     | INSECTS STONE               |
| DAN         | INSIDER ARIZONA             |
| JULIA       | INSIDER ARIZONA             |
| ALEC        | INSIDER ARIZONA             |
| KIRK        | INSIDER ARIZONA             |
| DAN         | INSIDER ARIZONA             |
| CATE        | INSIDER ARIZONA             |
| FAY         | INSIDER ARIZONA             |
| BURT        | INSIDER ARIZONA             |
| THORA       | INSIDER ARIZONA             |
| JENNIFER    | INSTINCT AIRPORT            |
| GRACE       | INSTINCT AIRPORT            |
| CAMERON     | INSTINCT AIRPORT            |
| JOHNNY      | INSTINCT AIRPORT            |
| REESE       | INSTINCT AIRPORT            |
| PARKER      | INSTINCT AIRPORT            |
| PENELOPE    | INSTINCT AIRPORT            |
| SYLVESTER   | INSTINCT AIRPORT            |
| RICHARD     | INSTINCT AIRPORT            |
| GEOFFREY    | INSTINCT AIRPORT            |
| ED          | INSTINCT AIRPORT            |
| ANGELINA    | INTENTIONS EMPIRE           |
| MARY        | INTENTIONS EMPIRE           |
| MENA        | INTERVIEW LIAISONS          |
| JAYNE       | INTERVIEW LIAISONS          |
| SCARLETT    | INTERVIEW LIAISONS          |
| JOHN        | INTERVIEW LIAISONS          |
| THORA       | INTERVIEW LIAISONS          |
| BURT        | INTOLERABLE INTENTIONS      |
| JOHNNY      | INTOLERABLE INTENTIONS      |
| KENNETH     | INTOLERABLE INTENTIONS      |
| MICHELLE    | INTOLERABLE INTENTIONS      |
| MEG         | INTOLERABLE INTENTIONS      |
| OLYMPIA     | INTOLERABLE INTENTIONS      |
| VAL         | INTRIGUE WORST              |
| REESE       | INTRIGUE WORST              |
| GARY        | INTRIGUE WORST              |
| GINA        | INTRIGUE WORST              |
| CATE        | INTRIGUE WORST              |
| MERYL       | INTRIGUE WORST              |
| FAY         | INTRIGUE WORST              |
| WOODY       | INVASION CYCLONE            |
| RENEE       | INVASION CYCLONE            |
| SCARLETT    | INVASION CYCLONE            |
| FRANCES     | INVASION CYCLONE            |
| EMILY       | INVASION CYCLONE            |
| JAYNE       | INVASION CYCLONE            |
| ED          | INVASION CYCLONE            |
| HELEN       | IRON MOON                   |
| ANNE        | IRON MOON                   |
| RAY         | IRON MOON                   |
| GROUCHO     | IRON MOON                   |
| FRANCES     | IRON MOON                   |
| CHRIS       | IRON MOON                   |
| HARVEY      | IRON MOON                   |
| HUMPHREY    | IRON MOON                   |
| KIRSTEN     | ISHTAR ROCKETEER            |
| SALMA       | ISHTAR ROCKETEER            |
| JADA        | ISHTAR ROCKETEER            |
| JOHN        | ISHTAR ROCKETEER            |
| RAY         | ISLAND EXORCIST             |
| ANGELA      | ISLAND EXORCIST             |
| DARYL       | ISLAND EXORCIST             |
| VIVIEN      | ITALIAN AFRICAN             |
| AUDREY      | ITALIAN AFRICAN             |
| BOB         | JACKET FRISCO               |
| MILLA       | JACKET FRISCO               |
| MAE         | JACKET FRISCO               |
| CHARLIZE    | JACKET FRISCO               |
| ELLEN       | JACKET FRISCO               |
| KENNETH     | JACKET FRISCO               |
| ANGELA      | JACKET FRISCO               |
| VIVIEN      | JACKET FRISCO               |
| AL          | JACKET FRISCO               |
| BELA        | JACKET FRISCO               |
| CARMEN      | JADE BUNCH                  |
| DAN         | JADE BUNCH                  |
| ANGELINA    | JADE BUNCH                  |
| CAMERON     | JADE BUNCH                  |
| ED          | JADE BUNCH                  |
| MERYL       | JADE BUNCH                  |
| RENEE       | JADE BUNCH                  |
| THORA       | JADE BUNCH                  |
| VIVIEN      | JAPANESE RUN                |
| ANGELA      | JAPANESE RUN                |
| RALPH       | JAPANESE RUN                |
| MINNIE      | JAPANESE RUN                |
| KENNETH     | JAPANESE RUN                |
| JIM         | JAPANESE RUN                |
| KIM         | JAPANESE RUN                |
| BEN         | JAPANESE RUN                |
| JOHN        | JAPANESE RUN                |
| GOLDIE      | JASON TRAP                  |
| NATALIE     | JASON TRAP                  |
| ANGELA      | JASON TRAP                  |
| BEN         | JASON TRAP                  |
| MINNIE      | JASON TRAP                  |
| CHRISTIAN   | JAWBREAKER BROOKLYN         |
| JULIA       | JAWBREAKER BROOKLYN         |
| VAL         | JAWBREAKER BROOKLYN         |
| CHRISTIAN   | JAWBREAKER BROOKLYN         |
| JESSICA     | JAWBREAKER BROOKLYN         |
| HELEN       | JAWS HARRY                  |
| LUCILLE     | JAWS HARRY                  |
| PARKER      | JAWS HARRY                  |
| MINNIE      | JAWS HARRY                  |
| GRETA       | JAWS HARRY                  |
| JAMES       | JEDI BENEATH                |
| LIZA        | JEDI BENEATH                |
| JULIANNE    | JEDI BENEATH                |
| JANE        | JEDI BENEATH                |
| ED          | JEEPERS WEDDING             |
| CHRISTIAN   | JEEPERS WEDDING             |
| WOODY       | JEEPERS WEDDING             |
| CHRISTOPHER | JEEPERS WEDDING             |
| JULIANNE    | JEEPERS WEDDING             |
| MINNIE      | JEEPERS WEDDING             |
| NICK        | JEKYLL FROGMEN              |
| DAN         | JEKYLL FROGMEN              |
| JADA        | JEKYLL FROGMEN              |
| ALEC        | JEOPARDY ENCINO             |
| GREG        | JEOPARDY ENCINO             |
| GEOFFREY    | JEOPARDY ENCINO             |
| JULIA       | JEOPARDY ENCINO             |
| MARY        | JEOPARDY ENCINO             |
| ELVIS       | JERICHO MULAN               |
| VIVIEN      | JERICHO MULAN               |
| WILLIAM     | JERICHO MULAN               |
| LISA        | JERICHO MULAN               |
| DAN         | JERK PAYCHECK               |
| BURT        | JERK PAYCHECK               |
| REESE       | JERK PAYCHECK               |
| JULIA       | JERK PAYCHECK               |
| MILLA       | JERK PAYCHECK               |
| RITA        | JERK PAYCHECK               |
| CHRIS       | JERK PAYCHECK               |
| BELA        | JERK PAYCHECK               |
| NICK        | JERSEY SASSY                |
| ZERO        | JERSEY SASSY                |
| VAL         | JERSEY SASSY                |
| FAY         | JERSEY SASSY                |
| WALTER      | JERSEY SASSY                |
| CATE        | JERSEY SASSY                |
| ED          | JERSEY SASSY                |
| RIVER       | JERSEY SASSY                |
| JOHN        | JERSEY SASSY                |
| FAY         | JET NEIGHBORS               |
| GREG        | JET NEIGHBORS               |
| GENE        | JET NEIGHBORS               |
| MINNIE      | JET NEIGHBORS               |
| HUMPHREY    | JET NEIGHBORS               |
| MERYL       | JET NEIGHBORS               |
| KIM         | JINGLE SAGEBRUSH            |
| GROUCHO     | JINGLE SAGEBRUSH            |
| ALEC        | JOON NORTHWEST              |
| CHARLIZE    | JOON NORTHWEST              |
| MILLA       | JUGGLER HARDLY              |
| PENELOPE    | JUGGLER HARDLY              |
| CAMERON     | JUGGLER HARDLY              |
| PENELOPE    | JUGGLER HARDLY              |
| SALMA       | JUGGLER HARDLY              |
| MORGAN      | JUGGLER HARDLY              |
| EWAN        | JUGGLER HARDLY              |
| MERYL       | JUGGLER HARDLY              |
| ED          | JUGGLER HARDLY              |
| JENNIFER    | JUMANJI BLADE               |
| BOB         | JUMANJI BLADE               |
| NICK        | JUMANJI BLADE               |
| GARY        | JUMANJI BLADE               |
| MENA        | JUMANJI BLADE               |
| JIM         | JUMANJI BLADE               |
| ELVIS       | JUMPING WRATH               |
| SANDRA      | JUMPING WRATH               |
| ANGELA      | JUMPING WRATH               |
| JAMES       | JUMPING WRATH               |
| SUSAN       | JUMPING WRATH               |
| SALMA       | JUMPING WRATH               |
| CATE        | JUMPING WRATH               |
| ALAN        | JUMPING WRATH               |
| LUCILLE     | JUNGLE CLOSER               |
| MENA        | JUNGLE CLOSER               |
| BURT        | JUNGLE CLOSER               |
| DAN         | JUNGLE CLOSER               |
| HUMPHREY    | JUNGLE CLOSER               |
| CUBA        | JUNGLE CLOSER               |
| AUDREY      | KANE EXORCIST               |
| BURT        | KANE EXORCIST               |
| HENRY       | KANE EXORCIST               |
| CHRISTOPHER | KANE EXORCIST               |
| GROUCHO     | KANE EXORCIST               |
| JOHNNY      | KARATE MOON                 |
| SUSAN       | KARATE MOON                 |
| JULIANNE    | KARATE MOON                 |
| JANE        | KARATE MOON                 |
| JADA        | KARATE MOON                 |
| KIM         | KARATE MOON                 |
| MICHAEL     | KARATE MOON                 |
| JAYNE       | KARATE MOON                 |
| VIVIEN      | KENTUCKIAN GIANT            |
| ELVIS       | KENTUCKIAN GIANT            |
| WARREN      | KENTUCKIAN GIANT            |
| RUSSELL     | KENTUCKIAN GIANT            |
| ANGELA      | KICK SAVANNAH               |
| JESSICA     | KICK SAVANNAH               |
| GRETA       | KICK SAVANNAH               |
| LAURENCE    | KICK SAVANNAH               |
| ALAN        | KICK SAVANNAH               |
| MICHAEL     | KICK SAVANNAH               |
| KIRSTEN     | KILL BROTHERHOOD            |
| RIP         | KILL BROTHERHOOD            |
| WOODY       | KILL BROTHERHOOD            |
| ALBERT      | KILL BROTHERHOOD            |
| RIVER       | KILL BROTHERHOOD            |
| BURT        | KILLER INNOCENT             |
| ANGELINA    | KILLER INNOCENT             |
| DARYL       | KILLER INNOCENT             |
| WHOOPI      | KILLER INNOCENT             |
| MERYL       | KILLER INNOCENT             |
| PENELOPE    | KING EVOLUTION              |
| LUCILLE     | KING EVOLUTION              |
| BURT        | KING EVOLUTION              |
| CUBA        | KING EVOLUTION              |
| RENEE       | KING EVOLUTION              |
| MARY        | KING EVOLUTION              |
| CUBA        | KISS GLORY                  |
| HELEN       | KISS GLORY                  |
| JULIA       | KISS GLORY                  |
| TOM         | KISS GLORY                  |
| GROUCHO     | KISS GLORY                  |
| OPRAH       | KISS GLORY                  |
| HUMPHREY    | KISS GLORY                  |
| TOM         | KISSING DOLLS               |
| JADA        | KISSING DOLLS               |
| GEOFFREY    | KISSING DOLLS               |
| CUBA        | KNOCK WARLOCK               |
| WOODY       | KNOCK WARLOCK               |
| AUDREY      | KNOCK WARLOCK               |
| TOM         | KNOCK WARLOCK               |
| REESE       | KNOCK WARLOCK               |
| JUDE        | KNOCK WARLOCK               |
| JOHNNY      | KRAMER CHOCOLATE            |
| BETTE       | KRAMER CHOCOLATE            |
| FRED        | KRAMER CHOCOLATE            |
| JULIA       | KRAMER CHOCOLATE            |
| REESE       | KRAMER CHOCOLATE            |
| MILLA       | KRAMER CHOCOLATE            |
| WOODY       | KRAMER CHOCOLATE            |
| JULIANNE    | KRAMER CHOCOLATE            |
| NATALIE     | KWAI HOMEWARD               |
| MICHELLE    | KWAI HOMEWARD               |
| JADA        | KWAI HOMEWARD               |
| ANGELA      | KWAI HOMEWARD               |
| FAY         | KWAI HOMEWARD               |
| TOM         | LABYRINTH LEAGUE            |
| GROUCHO     | LABYRINTH LEAGUE            |
| SCARLETT    | LABYRINTH LEAGUE            |
| KIRSTEN     | LABYRINTH LEAGUE            |
| GROUCHO     | LABYRINTH LEAGUE            |
| KENNETH     | LABYRINTH LEAGUE            |
| PENELOPE    | LADY STAGE                  |
| FRANCES     | LADY STAGE                  |
| ANNE        | LADY STAGE                  |
| RAY         | LADY STAGE                  |
| PENELOPE    | LADY STAGE                  |
| HARRISON    | LADY STAGE                  |
| JEFF        | LADY STAGE                  |
| ROCK        | LADY STAGE                  |
| KIRSTEN     | LADYBUGS ARMAGEDDON         |
| WARREN      | LADYBUGS ARMAGEDDON         |
| GRETA       | LADYBUGS ARMAGEDDON         |
| MATTHEW     | LADYBUGS ARMAGEDDON         |
| WOODY       | LAMBS CINCINATTI            |
| VAL         | LAMBS CINCINATTI            |
| REESE       | LAMBS CINCINATTI            |
| JULIA       | LAMBS CINCINATTI            |
| MENA        | LAMBS CINCINATTI            |
| CHRISTIAN   | LAMBS CINCINATTI            |
| BURT        | LAMBS CINCINATTI            |
| SCARLETT    | LAMBS CINCINATTI            |
| WALTER      | LAMBS CINCINATTI            |
| CAMERON     | LAMBS CINCINATTI            |
| LUCILLE     | LAMBS CINCINATTI            |
| FAY         | LAMBS CINCINATTI            |
| JAYNE       | LAMBS CINCINATTI            |
| MENA        | LAMBS CINCINATTI            |
| JULIA       | LAMBS CINCINATTI            |
| PENELOPE    | LANGUAGE COWBOY             |
| BETTE       | LANGUAGE COWBOY             |
| CHRISTOPHER | LANGUAGE COWBOY             |
| WARREN      | LANGUAGE COWBOY             |
| WHOOPI      | LANGUAGE COWBOY             |
| CUBA        | LANGUAGE COWBOY             |
| JOE         | LAWLESS VISION              |
| BOB         | LAWLESS VISION              |
| PENELOPE    | LAWLESS VISION              |
| MICHAEL     | LAWLESS VISION              |
| CHRISTOPHER | LAWRENCE LOVE               |
| SUSAN       | LAWRENCE LOVE               |
| JESSICA     | LEAGUE HELLFIGHTERS         |
| KIRSTEN     | LEAGUE HELLFIGHTERS         |
| KENNETH     | LEAGUE HELLFIGHTERS         |
| JIM         | LEAGUE HELLFIGHTERS         |
| ALBERT      | LEAGUE HELLFIGHTERS         |
| CUBA        | LEAGUE HELLFIGHTERS         |
| KARL        | LEATHERNECKS DWARFS         |
| UMA         | LEATHERNECKS DWARFS         |
| BOB         | LEATHERNECKS DWARFS         |
| SPENCER     | LEATHERNECKS DWARFS         |
| SUSAN       | LEATHERNECKS DWARFS         |
| PENELOPE    | LEATHERNECKS DWARFS         |
| IAN         | LEATHERNECKS DWARFS         |
| JOE         | LEBOWSKI SOLDIERS           |
| RICHARD     | LEBOWSKI SOLDIERS           |
| ALBERT      | LEBOWSKI SOLDIERS           |
| UMA         | LEGALLY SECRETARY           |
| HELEN       | LEGALLY SECRETARY           |
| CAMERON     | LEGALLY SECRETARY           |
| CARMEN      | LEGALLY SECRETARY           |
| JANE        | LEGALLY SECRETARY           |
| BELA        | LEGALLY SECRETARY           |
| TOM         | LEGEND JEDI                 |
| ANGELA      | LEGEND JEDI                 |
| PENELOPE    | LEGEND JEDI                 |
| CATE        | LEGEND JEDI                 |
| BETTE       | LESSON CLEOPATRA            |
| CARMEN      | LESSON CLEOPATRA            |
| CAMERON     | LESSON CLEOPATRA            |
| ANGELA      | LESSON CLEOPATRA            |
| KENNETH     | LESSON CLEOPATRA            |
| WALTER      | LESSON CLEOPATRA            |
| WARREN      | LESSON CLEOPATRA            |
| CUBA        | LESSON CLEOPATRA            |
| LIZA        | LESSON CLEOPATRA            |
| JON         | LESSON CLEOPATRA            |
| LISA        | LESSON CLEOPATRA            |
| ROCK        | LESSON CLEOPATRA            |
| NICK        | LIAISONS SWEET              |
| MENA        | LIAISONS SWEET              |
| CHRISTIAN   | LIAISONS SWEET              |
| MEG         | LIAISONS SWEET              |
| FAY         | LIAISONS SWEET              |
| MICHAEL     | LIAISONS SWEET              |
| BETTE       | LIBERTY MAGNIFICENT         |
| ALEC        | LIBERTY MAGNIFICENT         |
| CHRISTIAN   | LIBERTY MAGNIFICENT         |
| BEN         | LIBERTY MAGNIFICENT         |
| GREG        | LIBERTY MAGNIFICENT         |
| WILL        | LIBERTY MAGNIFICENT         |
| CUBA        | LIBERTY MAGNIFICENT         |
| NATALIE     | LICENSE WEEKEND             |
| GROUCHO     | LICENSE WEEKEND             |
| GREG        | LICENSE WEEKEND             |
| SEAN        | LICENSE WEEKEND             |
| GINA        | LICENSE WEEKEND             |
| DARYL       | LICENSE WEEKEND             |
| RUSSELL     | LICENSE WEEKEND             |
| JAYNE       | LICENSE WEEKEND             |
| HELEN       | LIES TREATMENT              |
| JOHNNY      | LIES TREATMENT              |
| DAN         | LIES TREATMENT              |
| KENNETH     | LIES TREATMENT              |
| WALTER      | LIES TREATMENT              |
| WARREN      | LIES TREATMENT              |
| JON         | LIES TREATMENT              |
| CHRISTIAN   | LIFE TWISTED                |
| UMA         | LIFE TWISTED                |
| MINNIE      | LIFE TWISTED                |
| DARYL       | LIFE TWISTED                |
| CHRISTOPHER | LIFE TWISTED                |
| GENE        | LIFE TWISTED                |
| MATTHEW     | LIFE TWISTED                |
| REESE       | LIFE TWISTED                |
| MATTHEW     | LIGHTS DEER                 |
| TIM         | LIGHTS DEER                 |
| UMA         | LION UNCUT                  |
| PENELOPE    | LION UNCUT                  |
| BELA        | LION UNCUT                  |
| AUDREY      | LOATHING LEGALLY            |
| GARY        | LOATHING LEGALLY            |
| SUSAN       | LOATHING LEGALLY            |
| MORGAN      | LOATHING LEGALLY            |
| GRETA       | LOATHING LEGALLY            |
| WALTER      | LOCK REAR                   |
| HARVEY      | LOCK REAR                   |
| LUCILLE     | LOLA AGENT                  |
| TOM         | LOLA AGENT                  |
| SCARLETT    | LOLA AGENT                  |
| WOODY       | LOLA AGENT                  |
| KIM         | LOLA AGENT                  |
| GEOFFREY    | LOLA AGENT                  |
| UMA         | LOLITA WORLD                |
| RIP         | LONELY ELEPHANT             |
| VAL         | LONELY ELEPHANT             |
| KENNETH     | LONELY ELEPHANT             |
| BEN         | LONELY ELEPHANT             |
| JAMES       | LONELY ELEPHANT             |
| CHARLIZE    | LONELY ELEPHANT             |
| SEAN        | LONELY ELEPHANT             |
| WALTER      | LONELY ELEPHANT             |
| EWAN        | LONELY ELEPHANT             |
| GROUCHO     | LONELY ELEPHANT             |
| ALAN        | LONELY ELEPHANT             |
| ROCK        | LONELY ELEPHANT             |
| CHRISTIAN   | LORD ARIZONA                |
| KIRSTEN     | LORD ARIZONA                |
| GROUCHO     | LORD ARIZONA                |
| SIDNEY      | LORD ARIZONA                |
| JULIANNE    | LORD ARIZONA                |
| MORGAN      | LORD ARIZONA                |
| LUCILLE     | LOSE INCH                   |
| HARRISON    | LOSE INCH                   |
| MERYL       | LOSE INCH                   |
| REESE       | LOSE INCH                   |
| MATTHEW     | LOSER HUSTLER               |
| ZERO        | LOSER HUSTLER               |
| WOODY       | LOSER HUSTLER               |
| ADAM        | LOSER HUSTLER               |
| VIVIEN      | LOSER HUSTLER               |
| KIRK        | LOST BIRD                   |
| KENNETH     | LOST BIRD                   |
| CUBA        | LOST BIRD                   |
| HENRY       | LOUISIANA HARRY             |
| GINA        | LOUISIANA HARRY             |
| JAYNE       | LOUISIANA HARRY             |
| JOHNNY      | LOVE SUICIDES               |
| TOM         | LOVE SUICIDES               |
| CHRISTIAN   | LOVE SUICIDES               |
| GRETA       | LOVE SUICIDES               |
| VIVIEN      | LOVELY JINGLE               |
| DAN         | LOVELY JINGLE               |
| ELVIS       | LOVELY JINGLE               |
| SANDRA      | LOVELY JINGLE               |
| MINNIE      | LOVELY JINGLE               |
| MARY        | LOVELY JINGLE               |
| VIVIEN      | LOVER TRUMAN                |
| REESE       | LOVER TRUMAN                |
| CHRISTIAN   | LOVER TRUMAN                |
| MILLA       | LOVER TRUMAN                |
| MENA        | LOVER TRUMAN                |
| LISA        | LOVER TRUMAN                |
| THORA       | LOVER TRUMAN                |
| LUCILLE     | LOVERBOY ATTACKS            |
| KEVIN       | LOVERBOY ATTACKS            |
| PARKER      | LOVERBOY ATTACKS            |
| CARY        | LOVERBOY ATTACKS            |
| MORGAN      | LOVERBOY ATTACKS            |
| ADAM        | LOVERBOY ATTACKS            |
| GROUCHO     | LOVERBOY ATTACKS            |
| RENEE       | LOVERBOY ATTACKS            |
| THORA       | LOVERBOY ATTACKS            |
| ED          | LUCK OPUS                   |
| SUSAN       | LUCK OPUS                   |
| SCARLETT    | LUCK OPUS                   |
| JANE        | LUCK OPUS                   |
| GEOFFREY    | LUCK OPUS                   |
| MATTHEW     | LUCK OPUS                   |
| NICK        | LUCKY FLYING                |
| KARL        | LUCKY FLYING                |
| JULIA       | LUCKY FLYING                |
| PARKER      | LUCKY FLYING                |
| JAMES       | LUCKY FLYING                |
| KENNETH     | LUCKY FLYING                |
| JIM         | LUCKY FLYING                |
| EWAN        | LUCKY FLYING                |
| JADA        | LUCKY FLYING                |
| ANGELA      | LUCKY FLYING                |
| CUBA        | LUKE MUMMY                  |
| CHRISTIAN   | LUKE MUMMY                  |
| ANGELA      | LUKE MUMMY                  |
| BURT        | LUKE MUMMY                  |
| RITA        | LUKE MUMMY                  |
| JOHN        | LUKE MUMMY                  |
| BELA        | LUKE MUMMY                  |
| MARY        | LUKE MUMMY                  |
| JULIA       | LUKE MUMMY                  |
| ANNE        | LUST LOCK                   |
| CHARLIZE    | LUST LOCK                   |
| SEAN        | LUST LOCK                   |
| SALMA       | LUST LOCK                   |
| ED          | LUST LOCK                   |
| JAYNE       | LUST LOCK                   |
| MATTHEW     | LUST LOCK                   |
| RAY         | MADIGAN DORADO              |
| MILLA       | MADIGAN DORADO              |
| MINNIE      | MADIGAN DORADO              |
| KIRSTEN     | MADIGAN DORADO              |
| JON         | MADIGAN DORADO              |
| GENE        | MADIGAN DORADO              |
| RIP         | MADISON TRAP                |
| JODIE       | MADISON TRAP                |
| WALTER      | MADISON TRAP                |
| GREGORY     | MADISON TRAP                |
| THORA       | MADISON TRAP                |
| FRANCES     | MADNESS ATTACKS             |
| SCARLETT    | MADNESS ATTACKS             |
| KIRSTEN     | MADNESS ATTACKS             |
| SUSAN       | MADNESS ATTACKS             |
| FRANCES     | MADNESS ATTACKS             |
| HUMPHREY    | MADNESS ATTACKS             |
| MARY        | MADNESS ATTACKS             |
| TOM         | MADRE GABLES                |
| PENELOPE    | MADRE GABLES                |
| DARYL       | MADRE GABLES                |
| MATTHEW     | MADRE GABLES                |
| ALEC        | MAGIC MALLRATS              |
| TOM         | MAGIC MALLRATS              |
| BURT        | MAGIC MALLRATS              |
| KIRSTEN     | MAGIC MALLRATS              |
| FRED        | MAGNIFICENT CHITTY          |
| GARY        | MAGNIFICENT CHITTY          |
| GREG        | MAGNIFICENT CHITTY          |
| KENNETH     | MAGNIFICENT CHITTY          |
| GINA        | MAGNIFICENT CHITTY          |
| RENEE       | MAGNIFICENT CHITTY          |
| CUBA        | MAGNIFICENT CHITTY          |
| SANDRA      | MAGNOLIA FORRESTER          |
| CHRISTIAN   | MAGNOLIA FORRESTER          |
| GROUCHO     | MAGNOLIA FORRESTER          |
| GRETA       | MAGNOLIA FORRESTER          |
| LAURA       | MAGNOLIA FORRESTER          |
| OLYMPIA     | MAGNOLIA FORRESTER          |
| AUDREY      | MAGNOLIA FORRESTER          |
| NICK        | MAGUIRE APACHE              |
| SEAN        | MAGUIRE APACHE              |
| RENEE       | MAGUIRE APACHE              |
| ALAN        | MAGUIRE APACHE              |
| WOODY       | MAIDEN HOME                 |
| CHRISTIAN   | MAIDEN HOME                 |
| HENRY       | MAIDEN HOME                 |
| WOODY       | MAIDEN HOME                 |
| KENNETH     | MAIDEN HOME                 |
| DARYL       | MAIDEN HOME                 |
| JAYNE       | MAIDEN HOME                 |
| GREGORY     | MAIDEN HOME                 |
| JOE         | MAJESTIC FLOATS             |
| NATALIE     | MAJESTIC FLOATS             |
| GROUCHO     | MAJESTIC FLOATS             |
| ED          | MAJESTIC FLOATS             |
| JULIA       | MAJESTIC FLOATS             |
| CUBA        | MAKER GABLES                |
| VAL         | MAKER GABLES                |
| CHRISTIAN   | MAKER GABLES                |
| MARY        | MAKER GABLES                |
| RALPH       | MAKER GABLES                |
| KIRSTEN     | MAKER GABLES                |
| MEG         | MAKER GABLES                |
| CUBA        | MAKER GABLES                |
| KEVIN       | MAKER GABLES                |
| RITA        | MAKER GABLES                |
| LUCILLE     | MAKER GABLES                |
| GRACE       | MALKOVICH PET               |
| MATTHEW     | MALKOVICH PET               |
| JADA        | MALKOVICH PET               |
| FAY         | MALKOVICH PET               |
| LAURENCE    | MALKOVICH PET               |
| MICHAEL     | MALKOVICH PET               |
| REESE       | MALKOVICH PET               |
| NICK        | MALLRATS UNITED             |
| VAL         | MALLRATS UNITED             |
| CAMERON     | MALLRATS UNITED             |
| VIVIEN      | MALLRATS UNITED             |
| MARY        | MALLRATS UNITED             |
| ANGELA      | MALTESE HOPE                |
| RAY         | MANCHURIAN CURTAIN          |
| ALBERT      | MANCHURIAN CURTAIN          |
| ANNE        | MANNEQUIN WORST             |
| MINNIE      | MANNEQUIN WORST             |
| SIDNEY      | MANNEQUIN WORST             |
| CUBA        | MANNEQUIN WORST             |
| GENE        | MANNEQUIN WORST             |
| GOLDIE      | MARRIED GO                  |
| FRANCES     | MARRIED GO                  |
| GROUCHO     | MARRIED GO                  |
| ADAM        | MARS ROMAN                  |
| RIVER       | MARS ROMAN                  |
| OLYMPIA     | MARS ROMAN                  |
| MICHAEL     | MARS ROMAN                  |
| CUBA        | MARS ROMAN                  |
| JAYNE       | MARS ROMAN                  |
| BELA        | MARS ROMAN                  |
| NICK        | MASK PEACH                  |
| DAN         | MASK PEACH                  |
| GARY        | MASK PEACH                  |
| WOODY       | MASK PEACH                  |
| MEG         | MASK PEACH                  |
| SIDNEY      | MASK PEACH                  |
| WARREN      | MASK PEACH                  |
| LUCILLE     | MASK PEACH                  |
| LAURA       | MASK PEACH                  |
| JEFF        | MASK PEACH                  |
| RENEE       | MASK PEACH                  |
| GARY        | MASKED BUBBLE               |
| ADAM        | MASKED BUBBLE               |
| AUDREY      | MASKED BUBBLE               |
| SPENCER     | MASSACRE USUAL              |
| FAY         | MASSACRE USUAL              |
| GENE        | MASSACRE USUAL              |
| KEVIN       | MASSAGE IMAGE               |
| RIP         | MASSAGE IMAGE               |
| SCARLETT    | MASSAGE IMAGE               |
| CHARLIZE    | MASSAGE IMAGE               |
| KIRSTEN     | MASSAGE IMAGE               |
| CATE        | MASSAGE IMAGE               |
| MORGAN      | MASSAGE IMAGE               |
| KENNETH     | MASSAGE IMAGE               |
| ALAN        | MASSAGE IMAGE               |
| SANDRA      | MATRIX SNOWMAN              |
| GARY        | MATRIX SNOWMAN              |
| RUSSELL     | MATRIX SNOWMAN              |
| CARY        | MAUDE MOD                   |
| JAMES       | MAUDE MOD                   |
| GROUCHO     | MAUDE MOD                   |
| OLYMPIA     | MAUDE MOD                   |
| ED          | MAUDE MOD                   |
| ROCK        | MAUDE MOD                   |
| ZERO        | MEET CHOCOLATE              |
| TIM         | MEET CHOCOLATE              |
| PARKER      | MEET CHOCOLATE              |
| WARREN      | MEET CHOCOLATE              |
| WARREN      | MEET CHOCOLATE              |
| GROUCHO     | MEET CHOCOLATE              |
| TOM         | MEMENTO ZOOLANDER           |
| ANGELINA    | MEMENTO ZOOLANDER           |
| KIRSTEN     | MEMENTO ZOOLANDER           |
| SUSAN       | MEMENTO ZOOLANDER           |
| ALBERT      | MEMENTO ZOOLANDER           |
| MARY        | MEMENTO ZOOLANDER           |
| BURT        | MENAGERIE RUSHMORE          |
| RAY         | MENAGERIE RUSHMORE          |
| FRANCES     | MERMAID INSECTS             |
| SPENCER     | MERMAID INSECTS             |
| WARREN      | MERMAID INSECTS             |
| EWAN        | MERMAID INSECTS             |
| GEOFFREY    | MERMAID INSECTS             |
| MARY        | MERMAID INSECTS             |
| JOHNNY      | METAL ARMAGEDDON            |
| UMA         | METAL ARMAGEDDON            |
| ANGELA      | METAL ARMAGEDDON            |
| GINA        | METAL ARMAGEDDON            |
| ALBERT      | METAL ARMAGEDDON            |
| KENNETH     | METAL ARMAGEDDON            |
| ALAN        | METAL ARMAGEDDON            |
| MICHAEL     | METAL ARMAGEDDON            |
| VAL         | METROPOLIS COMA             |
| DUSTIN      | METROPOLIS COMA             |
| RAY         | METROPOLIS COMA             |
| GENE        | METROPOLIS COMA             |
| JIM         | METROPOLIS COMA             |
| CUBA        | METROPOLIS COMA             |
| HELEN       | MICROCOSMOS PARADISE        |
| MENA        | MICROCOSMOS PARADISE        |
| ELLEN       | MICROCOSMOS PARADISE        |
| KEVIN       | MICROCOSMOS PARADISE        |
| GRETA       | MICROCOSMOS PARADISE        |
| JON         | MICROCOSMOS PARADISE        |
| WOODY       | MIDNIGHT WESTWARD           |
| MILLA       | MIDNIGHT WESTWARD           |
| ADAM        | MIDNIGHT WESTWARD           |
| JAMES       | MIDNIGHT WESTWARD           |
| GINA        | MIDNIGHT WESTWARD           |
| GEOFFREY    | MIDNIGHT WESTWARD           |
| GRETA       | MIDNIGHT WESTWARD           |
| OPRAH       | MIDNIGHT WESTWARD           |
| HUMPHREY    | MIDNIGHT WESTWARD           |
| JADA        | MIDSUMMER GROUNDHOG         |
| BELA        | MIDSUMMER GROUNDHOG         |
| JULIA       | MIGHTY LUCK                 |
| MENA        | MIGHTY LUCK                 |
| JESSICA     | MIGHTY LUCK                 |
| JULIANNE    | MIGHTY LUCK                 |
| WHOOPI      | MIGHTY LUCK                 |
| RIVER       | MIGHTY LUCK                 |
| RUSSELL     | MIGHTY LUCK                 |
| BELA        | MIGHTY LUCK                 |
| MENA        | MILE MULAN                  |
| ANGELA      | MILE MULAN                  |
| JULIANNE    | MILE MULAN                  |
| CHRISTIAN   | MILLION ACE                 |
| SCARLETT    | MILLION ACE                 |
| RENEE       | MILLION ACE                 |
| BEN         | MILLION ACE                 |
| JOHN        | MILLION ACE                 |
| ANNE        | MINDS TRUMAN                |
| BURT        | MINDS TRUMAN                |
| SCARLETT    | MINDS TRUMAN                |
| CHRIS       | MINDS TRUMAN                |
| MATTHEW     | MINDS TRUMAN                |
| JULIA       | MINDS TRUMAN                |
| NICK        | MINE TITANS                 |
| HUMPHREY    | MINE TITANS                 |
| VIVIEN      | MINORITY KISS               |
| FRED        | MIRACLE VIRTUAL             |
| FRED        | MISSION ZOOLANDER           |
| KEVIN       | MISSION ZOOLANDER           |
| TOM         | MISSION ZOOLANDER           |
| PENELOPE    | MISSION ZOOLANDER           |
| LUCILLE     | MISSION ZOOLANDER           |
| CARMEN      | MIXED DOORS                 |
| MICHELLE    | MIXED DOORS                 |
| DAN         | MIXED DOORS                 |
| ALBERT      | MIXED DOORS                 |
| IAN         | MIXED DOORS                 |
| MICHAEL     | MIXED DOORS                 |
| CAMERON     | MOB DUFFEL                  |
| SISSY       | MOB DUFFEL                  |
| TIM         | MOB DUFFEL                  |
| CHRISTIAN   | MOB DUFFEL                  |
| MATTHEW     | MOB DUFFEL                  |
| GROUCHO     | MOB DUFFEL                  |
| JULIA       | MOCKINGBIRD HOLLYWOOD       |
| SEAN        | MOCKINGBIRD HOLLYWOOD       |
| ADAM        | MOCKINGBIRD HOLLYWOOD       |
| CHRISTIAN   | MOD SECRETARY               |
| ZERO        | MOD SECRETARY               |
| GOLDIE      | MOD SECRETARY               |
| WHOOPI      | MOD SECRETARY               |
| LISA        | MOD SECRETARY               |
| BELA        | MOD SECRETARY               |
| UMA         | MODEL FISH                  |
| VAL         | MODEL FISH                  |
| RICHARD     | MODEL FISH                  |
| GENE        | MODEL FISH                  |
| MERYL       | MODEL FISH                  |
| HARVEY      | MODEL FISH                  |
| ED          | MODEL FISH                  |
| MARY        | MODEL FISH                  |
| LUCILLE     | MODERN DORADO               |
| JUDY        | MODERN DORADO               |
| JAMES       | MODERN DORADO               |
| JULIANNE    | MODERN DORADO               |
| CATE        | MODERN DORADO               |
| ALEC        | MONEY HAROLD                |
| BURT        | MONEY HAROLD                |
| GENE        | MONEY HAROLD                |
| PENELOPE    | MONEY HAROLD                |
| JANE        | MONEY HAROLD                |
| IAN         | MONEY HAROLD                |
| DEBBIE      | MONEY HAROLD                |
| NICK        | MONSOON CAUSE               |
| NATALIE     | MONSOON CAUSE               |
| MINNIE      | MONSOON CAUSE               |
| ALBERT      | MONSOON CAUSE               |
| WILLIAM     | MONSOON CAUSE               |
| JUDE        | MONSTER SPARTACUS           |
| WARREN      | MONSTER SPARTACUS           |
| GRETA       | MONSTER SPARTACUS           |
| KIM         | MONSTER SPARTACUS           |
| ALAN        | MONSTER SPARTACUS           |
| JOHN        | MONSTER SPARTACUS           |
| JAYNE       | MONSTER SPARTACUS           |
| KARL        | MONTEREY LABYRINTH          |
| JULIA       | MONTEREY LABYRINTH          |
| DAN         | MONTEREY LABYRINTH          |
| JULIANNE    | MONTEREY LABYRINTH          |
| FAY         | MONTEREY LABYRINTH          |
| ROCK        | MONTEREY LABYRINTH          |
| CUBA        | MONTEZUMA COMMAND           |
| RICHARD     | MONTEZUMA COMMAND           |
| ANNE        | MOON BUNCH                  |
| JODIE       | MOONSHINE CABIN             |
| CARMEN      | MOONSHINE CABIN             |
| WILLIAM     | MOONSHINE CABIN             |
| MATTHEW     | MOONSHINE CABIN             |
| GREGORY     | MOONSHINE CABIN             |
| ZERO        | MOONWALKER FOOL             |
| UMA         | MOONWALKER FOOL             |
| WOODY       | MOONWALKER FOOL             |
| RAY         | MOONWALKER FOOL             |
| DARYL       | MOONWALKER FOOL             |
| HUMPHREY    | MOONWALKER FOOL             |
| MARY        | MOONWALKER FOOL             |
| GOLDIE      | MOSQUITO ARMAGEDDON         |
| KIRK        | MOSQUITO ARMAGEDDON         |
| NICK        | MOSQUITO ARMAGEDDON         |
| REESE       | MOSQUITO ARMAGEDDON         |
| FRANCES     | MOTHER OLEANDER             |
| GROUCHO     | MOTHER OLEANDER             |
| SPENCER     | MOTHER OLEANDER             |
| WHOOPI      | MOTHER OLEANDER             |
| ANGELA      | MOTHER OLEANDER             |
| UMA         | MOTIONS DETAILS             |
| ELVIS       | MOTIONS DETAILS             |
| BURT        | MOTIONS DETAILS             |
| PENELOPE    | MOTIONS DETAILS             |
| JIM         | MOTIONS DETAILS             |
| WALTER      | MOTIONS DETAILS             |
| PENELOPE    | MOTIONS DETAILS             |
| LAURA       | MOTIONS DETAILS             |
| JESSICA     | MOULIN WAKE                 |
| SCARLETT    | MOULIN WAKE                 |
| VIVIEN      | MOULIN WAKE                 |
| CHRISTIAN   | MOURNING PURPLE             |
| KENNETH     | MOURNING PURPLE             |
| ALBERT      | MOURNING PURPLE             |
| DARYL       | MOURNING PURPLE             |
| EWAN        | MOURNING PURPLE             |
| MERYL       | MOURNING PURPLE             |
| WILL        | MOURNING PURPLE             |
| HELEN       | MOVIE SHAKESPEARE           |
| CAMERON     | MOVIE SHAKESPEARE           |
| FAY         | MOVIE SHAKESPEARE           |
| GINA        | MOVIE SHAKESPEARE           |
| CAMERON     | MOVIE SHAKESPEARE           |
| RUSSELL     | MOVIE SHAKESPEARE           |
| MORGAN      | MOVIE SHAKESPEARE           |
| RIVER       | MOVIE SHAKESPEARE           |
| NICK        | MULAN MOON                  |
| ANGELINA    | MULAN MOON                  |
| GRETA       | MULAN MOON                  |
| MATTHEW     | MULAN MOON                  |
| JULIA       | MULAN MOON                  |
| PENELOPE    | MULHOLLAND BEAST            |
| BETTE       | MULHOLLAND BEAST            |
| KIRK        | MULHOLLAND BEAST            |
| JUDE        | MULHOLLAND BEAST            |
| WALTER      | MULHOLLAND BEAST            |
| EWAN        | MULHOLLAND BEAST            |
| HELEN       | MUMMY CREATURES             |
| KEVIN       | MUMMY CREATURES             |
| TIM         | MUMMY CREATURES             |
| GOLDIE      | MUMMY CREATURES             |
| ANGELINA    | MUMMY CREATURES             |
| SPENCER     | MUMMY CREATURES             |
| WALTER      | MUMMY CREATURES             |
| SIDNEY      | MUMMY CREATURES             |
| GINA        | MUMMY CREATURES             |
| RUSSELL     | MUMMY CREATURES             |
| DAN         | MUMMY CREATURES             |
| ROCK        | MUMMY CREATURES             |
| AUDREY      | MUMMY CREATURES             |
| RIP         | MUPPET MILE                 |
| MAE         | MUPPET MILE                 |
| CHRIS       | MUPPET MILE                 |
| PENELOPE    | MUPPET MILE                 |
| HARRISON    | MUPPET MILE                 |
| CATE        | MUPPET MILE                 |
| BEN         | MUPPET MILE                 |
| AL          | MUPPET MILE                 |
| KIRK        | MURDER ANTITRUST            |
| MARY        | MURDER ANTITRUST            |
| CHRISTOPHER | MURDER ANTITRUST            |
| SUSAN       | MURDER ANTITRUST            |
| CAMERON     | MURDER ANTITRUST            |
| WHOOPI      | MURDER ANTITRUST            |
| JADA        | MURDER ANTITRUST            |
| OLYMPIA     | MURDER ANTITRUST            |
| SEAN        | MUSCLE BRIGHT               |
| MATTHEW     | MUSCLE BRIGHT               |
| GROUCHO     | MUSCLE BRIGHT               |
| JEFF        | MUSCLE BRIGHT               |
| MATTHEW     | MUSCLE BRIGHT               |
| MORGAN      | MUSIC BOONDOCK              |
| HUMPHREY    | MUSIC BOONDOCK              |
| MICHAEL     | MUSIC BOONDOCK              |
| BEN         | MUSKETEERS WAIT             |
| VIVIEN      | MUSSOLINI SPOILERS          |
| DAN         | MUSSOLINI SPOILERS          |
| JUDY        | MUSSOLINI SPOILERS          |
| FAY         | MUSSOLINI SPOILERS          |
| KENNETH     | MUSSOLINI SPOILERS          |
| CARY        | MUSSOLINI SPOILERS          |
| OPRAH       | MUSSOLINI SPOILERS          |
| SCARLETT    | MYSTIC TRUMAN               |
| KEVIN       | MYSTIC TRUMAN               |
| RIVER       | MYSTIC TRUMAN               |
| HUMPHREY    | MYSTIC TRUMAN               |
| WARREN      | NAME DETECTIVE              |
| CATE        | NAME DETECTIVE              |
| JOHN        | NAME DETECTIVE              |
| JUDY        | NASH CHOCOLAT               |
| ANGELA      | NASH CHOCOLAT               |
| BEN         | NASH CHOCOLAT               |
| HARRISON    | NASH CHOCOLAT               |
| BEN         | NASH CHOCOLAT               |
| HUMPHREY    | NASH CHOCOLAT               |
| BELA        | NASH CHOCOLAT               |
| JENNIFER    | NATIONAL STORY              |
| RAY         | NATIONAL STORY              |
| JAMES       | NATIONAL STORY              |
| RITA        | NATIONAL STORY              |
| GRETA       | NATIONAL STORY              |
| VIVIEN      | NATIONAL STORY              |
| WILLIAM     | NATIONAL STORY              |
| MILLA       | NATURAL STOCK               |
| SUSAN       | NATURAL STOCK               |
| KEVIN       | NATURAL STOCK               |
| RENEE       | NATURAL STOCK               |
| ED          | NECKLACE OUTBREAK           |
| GRACE       | NECKLACE OUTBREAK           |
| MILLA       | NECKLACE OUTBREAK           |
| TOM         | NECKLACE OUTBREAK           |
| KIRSTEN     | NECKLACE OUTBREAK           |
| JIM         | NECKLACE OUTBREAK           |
| MICHAEL     | NECKLACE OUTBREAK           |
| JOHN        | NECKLACE OUTBREAK           |
| WOODY       | NEIGHBORS CHARADE           |
| TOM         | NEIGHBORS CHARADE           |
| RALPH       | NEIGHBORS CHARADE           |
| SCARLETT    | NEIGHBORS CHARADE           |
| DARYL       | NEIGHBORS CHARADE           |
| MORGAN      | NEIGHBORS CHARADE           |
| WILL        | NEIGHBORS CHARADE           |
| FAY         | NEMO CAMPUS                 |
| KENNETH     | NEMO CAMPUS                 |
| JIM         | NEMO CAMPUS                 |
| SALMA       | NEMO CAMPUS                 |
| ED          | NEMO CAMPUS                 |
| KIRK        | NETWORK PEAK                |
| NATALIE     | NETWORK PEAK                |
| ELLEN       | NETWORK PEAK                |
| RALPH       | NEWSIES STORY               |
| JIM         | NEWSIES STORY               |
| SYLVESTER   | NEWSIES STORY               |
| DAN         | NEWSIES STORY               |
| NICK        | NEWSIES STORY               |
| MICHAEL     | NEWSIES STORY               |
| JEFF        | NEWSIES STORY               |
| JOHN        | NEWSIES STORY               |
| SEAN        | NEWTON LABYRINTH            |
| GREG        | NEWTON LABYRINTH            |
| ALBERT      | NEWTON LABYRINTH            |
| AUDREY      | NEWTON LABYRINTH            |
| WALTER      | NIGHTMARE CHILL             |
| GENE        | NIGHTMARE CHILL             |
| WOODY       | NONE SPIKING                |
| SUSAN       | NONE SPIKING                |
| KIM         | NONE SPIKING                |
| OLYMPIA     | NONE SPIKING                |
| MATTHEW     | NONE SPIKING                |
| RENEE       | NONE SPIKING                |
| CUBA        | NOON PAPI                   |
| MILLA       | NOON PAPI                   |
| ADAM        | NOON PAPI                   |
| VIVIEN      | NOON PAPI                   |
| LAURENCE    | NOON PAPI                   |
| WILL        | NOON PAPI                   |
| GARY        | NORTH TEQUILA               |
| GARY        | NORTH TEQUILA               |
| DARYL       | NORTH TEQUILA               |
| LUCILLE     | NORTH TEQUILA               |
| MINNIE      | NORTH TEQUILA               |
| MICHELLE    | NORTHWEST POLISH            |
| MAE         | NORTHWEST POLISH            |
| RITA        | NORTHWEST POLISH            |
| LAURENCE    | NORTHWEST POLISH            |
| JEFF        | NORTHWEST POLISH            |
| CUBA        | NORTHWEST POLISH            |
| REESE       | NORTHWEST POLISH            |
| MARY        | NORTHWEST POLISH            |
| KIM         | NOTORIOUS REUNION           |
| JAYNE       | NOTORIOUS REUNION           |
| MINNIE      | NOTTING SPEAKEASY           |
| IAN         | NOTTING SPEAKEASY           |
| KARL        | NOVOCAINE FLIGHT            |
| BEN         | NOVOCAINE FLIGHT            |
| GREG        | NOVOCAINE FLIGHT            |
| WALTER      | NOVOCAINE FLIGHT            |
| RUSSELL     | NOVOCAINE FLIGHT            |
| MICHAEL     | NOVOCAINE FLIGHT            |
| NATALIE     | NUTS TIES                   |
| CHRISTIAN   | NUTS TIES                   |
| GRACE       | OCTOBER SUBMARINE           |
| CAMERON     | OCTOBER SUBMARINE           |
| SEAN        | OCTOBER SUBMARINE           |
| LIZA        | OCTOBER SUBMARINE           |
| EMILY       | OCTOBER SUBMARINE           |
| ELVIS       | ODDS BOOGIE                 |
| MAE         | ODDS BOOGIE                 |
| CHRIS       | ODDS BOOGIE                 |
| GEOFFREY    | ODDS BOOGIE                 |
| KENNETH     | ODDS BOOGIE                 |
| PENELOPE    | OKLAHOMA JUMANJI            |
| JENNIFER    | OKLAHOMA JUMANJI            |
| KARL        | OKLAHOMA JUMANJI            |
| CUBA        | OKLAHOMA JUMANJI            |
| RIP         | OKLAHOMA JUMANJI            |
| CHRISTIAN   | OKLAHOMA JUMANJI            |
| CARY        | OKLAHOMA JUMANJI            |
| RICHARD     | OKLAHOMA JUMANJI            |
| BELA        | OKLAHOMA JUMANJI            |
| ZERO        | OLEANDER CLUE               |
| SANDRA      | OLEANDER CLUE               |
| PENELOPE    | OLEANDER CLUE               |
| SEAN        | OLEANDER CLUE               |
| GREG        | OLEANDER CLUE               |
| JIM         | OLEANDER CLUE               |
| WARREN      | OLEANDER CLUE               |
| EWAN        | OLEANDER CLUE               |
| OPRAH       | OLEANDER CLUE               |
| RUSSELL     | OLEANDER CLUE               |
| GRACE       | OPEN AFRICAN                |
| JULIA       | OPEN AFRICAN                |
| SISSY       | OPEN AFRICAN                |
| JUDE        | OPEN AFRICAN                |
| MILLA       | OPEN AFRICAN                |
| GINA        | OPEN AFRICAN                |
| ADAM        | OPEN AFRICAN                |
| VIVIEN      | OPEN AFRICAN                |
| JULIA       | OPEN AFRICAN                |
| CHRISTIAN   | OPERATION OPERATION         |
| ADAM        | OPERATION OPERATION         |
| GREGORY     | OPERATION OPERATION         |
| CHRISTIAN   | OPPOSITE NECKLACE           |
| MATTHEW     | OPPOSITE NECKLACE           |
| GROUCHO     | OPPOSITE NECKLACE           |
| LUCILLE     | OPPOSITE NECKLACE           |
| GROUCHO     | OPPOSITE NECKLACE           |
| DEBBIE      | OPPOSITE NECKLACE           |
| SEAN        | OPUS ICE                    |
| DARYL       | OPUS ICE                    |
| HUMPHREY    | OPUS ICE                    |
| JULIA       | OPUS ICE                    |
| MEG         | ORANGE GRAPES               |
| CUBA        | ORANGE GRAPES               |
| PENELOPE    | ORANGE GRAPES               |
| KEVIN       | ORANGE GRAPES               |
| KIM         | ORANGE GRAPES               |
| ANGELINA    | ORDER BETRAYED              |
| SPENCER     | ORDER BETRAYED              |
| MORGAN      | ORDER BETRAYED              |
| PENELOPE    | ORDER BETRAYED              |
| GRETA       | ORDER BETRAYED              |
| KENNETH     | ORDER BETRAYED              |
| HUMPHREY    | ORDER BETRAYED              |
| LUCILLE     | ORIENT CLOSER               |
| SCARLETT    | ORIENT CLOSER               |
| MATTHEW     | ORIENT CLOSER               |
| CAMERON     | ORIENT CLOSER               |
| BOB         | OSCAR GOLD                  |
| RIP         | OSCAR GOLD                  |
| DUSTIN      | OSCAR GOLD                  |
| ELLEN       | OSCAR GOLD                  |
| HARVEY      | OSCAR GOLD                  |
| AL          | OSCAR GOLD                  |
| FRANCES     | OTHERS SOUP                 |
| NATALIE     | OTHERS SOUP                 |
| BURT        | OTHERS SOUP                 |
| OLYMPIA     | OTHERS SOUP                 |
| ALEC        | OUTBREAK DIVINE             |
| RAY         | OUTBREAK DIVINE             |
| MAE         | OUTBREAK DIVINE             |
| JAMES       | OUTBREAK DIVINE             |
| FAY         | OUTBREAK DIVINE             |
| DAN         | OUTFIELD MASSACRE           |
| JANE        | OUTFIELD MASSACRE           |
| WHOOPI      | OUTFIELD MASSACRE           |
| JAYNE       | OUTFIELD MASSACRE           |
| ELVIS       | OUTLAW HANKY                |
| GOLDIE      | OUTLAW HANKY                |
| TOM         | OUTLAW HANKY                |
| CHRISTIAN   | OUTLAW HANKY                |
| ANGELINA    | OUTLAW HANKY                |
| WARREN      | OUTLAW HANKY                |
| JULIA       | OUTLAW HANKY                |
| SANDRA      | OZ LIAISONS                 |
| PENELOPE    | OZ LIAISONS                 |
| CHRISTIAN   | OZ LIAISONS                 |
| SIDNEY      | OZ LIAISONS                 |
| WARREN      | OZ LIAISONS                 |
| SALMA       | OZ LIAISONS                 |
| ED          | OZ LIAISONS                 |
| FAY         | OZ LIAISONS                 |
| GROUCHO     | OZ LIAISONS                 |
| GENE        | OZ LIAISONS                 |
| JAYNE       | OZ LIAISONS                 |
| JOHNNY      | PACIFIC AMISTAD             |
| JOE         | PACIFIC AMISTAD             |
| DUSTIN      | PACIFIC AMISTAD             |
| ANGELINA    | PACIFIC AMISTAD             |
| SUSAN       | PACIFIC AMISTAD             |
| CATE        | PACIFIC AMISTAD             |
| ED          | PACIFIC AMISTAD             |
| HUMPHREY    | PACIFIC AMISTAD             |
| TIM         | PACKER MADIGAN              |
| LUCILLE     | PAJAMA JAWBREAKER           |
| WOODY       | PAJAMA JAWBREAKER           |
| WARREN      | PAJAMA JAWBREAKER           |
| RICHARD     | PAJAMA JAWBREAKER           |
| WILL        | PAJAMA JAWBREAKER           |
| CAMERON     | PANIC CLUB                  |
| DAN         | PANIC CLUB                  |
| HARVEY      | PANIC CLUB                  |
| RIP         | PANKY SUBMARINE             |
| MICHELLE    | PANKY SUBMARINE             |
| SPENCER     | PANKY SUBMARINE             |
| GROUCHO     | PANKY SUBMARINE             |
| RUSSELL     | PANKY SUBMARINE             |
| LIZA        | PANKY SUBMARINE             |
| SALMA       | PANKY SUBMARINE             |
| JULIA       | PANKY SUBMARINE             |
| BEN         | PANTHER REDS                |
| SUSAN       | PANTHER REDS                |
| WARREN      | PANTHER REDS                |
| GENE        | PANTHER REDS                |
| HARVEY      | PANTHER REDS                |
| MEG         | PAPI NECKLACE               |
| MORGAN      | PAPI NECKLACE               |
| CUBA        | PAPI NECKLACE               |
| JODIE       | PARADISE SABRINA            |
| PENELOPE    | PARADISE SABRINA            |
| SYLVESTER   | PARADISE SABRINA            |
| JEFF        | PARADISE SABRINA            |
| PENELOPE    | PARIS WEEKEND               |
| HENRY       | PARIS WEEKEND               |
| ANGELA      | PARIS WEEKEND               |
| LIZA        | PARIS WEEKEND               |
| GEOFFREY    | PARIS WEEKEND               |
| JAYNE       | PARIS WEEKEND               |
| GROUCHO     | PARK CITIZEN                |
| PENELOPE    | PARK CITIZEN                |
| RIVER       | PARK CITIZEN                |
| OPRAH       | PARK CITIZEN                |
| AL          | PARK CITIZEN                |
| MICHAEL     | PARK CITIZEN                |
| RIVER       | PARTY KNOCK                 |
| CHRIS       | PARTY KNOCK                 |
| GENE        | PAST SUICIDES               |
| HARRISON    | PAST SUICIDES               |
| KIM         | PAST SUICIDES               |
| GRETA       | PAST SUICIDES               |
| GROUCHO     | PAST SUICIDES               |
| HUMPHREY    | PAST SUICIDES               |
| VAL         | PATHS CONTROL               |
| ANNE        | PATHS CONTROL               |
| KIRSTEN     | PATHS CONTROL               |
| SUSAN       | PATHS CONTROL               |
| ROCK        | PATHS CONTROL               |
| LUCILLE     | PATIENT SISTER              |
| VAL         | PATIENT SISTER              |
| MILLA       | PATIENT SISTER              |
| SEAN        | PATIENT SISTER              |
| CARMEN      | PATRIOT ROMAN               |
| ALBERT      | PATRIOT ROMAN               |
| KIM         | PATRIOT ROMAN               |
| RENEE       | PATRIOT ROMAN               |
| JOHNNY      | PATTON INTERVIEW            |
| TOM         | PATTON INTERVIEW            |
| HENRY       | PATTON INTERVIEW            |
| RIP         | PATTON INTERVIEW            |
| SEAN        | PATTON INTERVIEW            |
| CATE        | PATTON INTERVIEW            |
| WHOOPI      | PATTON INTERVIEW            |
| GEOFFREY    | PATTON INTERVIEW            |
| MICHAEL     | PATTON INTERVIEW            |
| GARY        | PAYCHECK WAIT               |
| RUSSELL     | PAYCHECK WAIT               |
| LIZA        | PAYCHECK WAIT               |
| TIM         | PEACH INNOCENT              |
| MILLA       | PEACH INNOCENT              |
| GARY        | PEACH INNOCENT              |
| BURT        | PEACH INNOCENT              |
| GROUCHO     | PEACH INNOCENT              |
| AUDREY      | PEAK FOREVER                |
| KENNETH     | PEAK FOREVER                |
| ANGELA      | PEAK FOREVER                |
| DEBBIE      | PEAK FOREVER                |
| GREGORY     | PEAK FOREVER                |
| TIM         | PEARL DESTINY               |
| CAMERON     | PEARL DESTINY               |
| DARYL       | PEARL DESTINY               |
| HARVEY      | PEARL DESTINY               |
| BOB         | PELICAN COMFORTS            |
| JULIA       | PELICAN COMFORTS            |
| GROUCHO     | PELICAN COMFORTS            |
| WHOOPI      | PELICAN COMFORTS            |
| RUSSELL     | PELICAN COMFORTS            |
| JOE         | PERDITION FARGO             |
| RIP         | PERDITION FARGO             |
| HARRISON    | PERDITION FARGO             |
| CATE        | PERDITION FARGO             |
| RENEE       | PERDITION FARGO             |
| KARL        | PERFECT GROOVE              |
| NATALIE     | PERFECT GROOVE              |
| BEN         | PERFECT GROOVE              |
| JIM         | PERFECT GROOVE              |
| JAYNE       | PERFECT GROOVE              |
| LAURENCE    | PERFECT GROOVE              |
| BOB         | PERSONAL LADYBUGS           |
| SANDRA      | PERSONAL LADYBUGS           |
| TOM         | PERSONAL LADYBUGS           |
| WARREN      | PERSONAL LADYBUGS           |
| SALMA       | PERSONAL LADYBUGS           |
| CATE        | PERSONAL LADYBUGS           |
| HUMPHREY    | PERSONAL LADYBUGS           |
| KENNETH     | PERSONAL LADYBUGS           |
| JAYNE       | PERSONAL LADYBUGS           |
| JODIE       | PET HAUNTING                |
| GROUCHO     | PET HAUNTING                |
| MORGAN      | PET HAUNTING                |
| BEN         | PET HAUNTING                |
| LAURA       | PET HAUNTING                |
| NICK        | PET HAUNTING                |
| JOHN        | PET HAUNTING                |
| CARMEN      | PHANTOM GLORY               |
| GROUCHO     | PHANTOM GLORY               |
| MARY        | PHILADELPHIA WIFE           |
| SEAN        | PHILADELPHIA WIFE           |
| PENELOPE    | PIANIST OUTFIELD            |
| MICHAEL     | PIANIST OUTFIELD            |
| DEBBIE      | PIANIST OUTFIELD            |
| JOHN        | PIANIST OUTFIELD            |
| JAYNE       | PIANIST OUTFIELD            |
| JODIE       | PICKUP DRIVING              |
| GARY        | PICKUP DRIVING              |
| MINNIE      | PICKUP DRIVING              |
| ELLEN       | PICKUP DRIVING              |
| WILL        | PICKUP DRIVING              |
| JULIA       | PILOT HOOSIERS              |
| WOODY       | PILOT HOOSIERS              |
| HENRY       | PILOT HOOSIERS              |
| SPENCER     | PILOT HOOSIERS              |
| CAMERON     | PILOT HOOSIERS              |
| DEBBIE      | PILOT HOOSIERS              |
| AUDREY      | PILOT HOOSIERS              |
| KIRSTEN     | PINOCCHIO SIMON             |
| REESE       | PINOCCHIO SIMON             |
| RALPH       | PINOCCHIO SIMON             |
| ELLEN       | PINOCCHIO SIMON             |
| CAMERON     | PINOCCHIO SIMON             |
| MORGAN      | PINOCCHIO SIMON             |
| RIVER       | PINOCCHIO SIMON             |
| BEN         | PINOCCHIO SIMON             |
| MERYL       | PINOCCHIO SIMON             |
| LAURA       | PINOCCHIO SIMON             |
| JOHN        | PINOCCHIO SIMON             |
| HUMPHREY    | PIRATES ROXANNE             |
| RIP         | PITTSBURGH HUNCHBACK        |
| JULIA       | PITTSBURGH HUNCHBACK        |
| PENELOPE    | PITTSBURGH HUNCHBACK        |
| AUDREY      | PITTSBURGH HUNCHBACK        |
| JOHN        | PITTSBURGH HUNCHBACK        |
| GOLDIE      | PITY BOUND                  |
| ANGELA      | PITY BOUND                  |
| ALBERT      | PITY BOUND                  |
| GENE        | PITY BOUND                  |
| GENE        | PITY BOUND                  |
| DARYL       | PIZZA JUMANJI               |
| HARVEY      | PIZZA JUMANJI               |
| GENE        | PIZZA JUMANJI               |
| HUMPHREY    | PIZZA JUMANJI               |
| BELA        | PIZZA JUMANJI               |
| ED          | PLATOON INSTINCT            |
| JUDE        | PLATOON INSTINCT            |
| FRANCES     | PLATOON INSTINCT            |
| RUSSELL     | PLATOON INSTINCT            |
| WILL        | PLATOON INSTINCT            |
| KIRSTEN     | PLUTO OLEANDER              |
| BEN         | PLUTO OLEANDER              |
| KIRSTEN     | PLUTO OLEANDER              |
| CHRIS       | PLUTO OLEANDER              |
| SIDNEY      | PLUTO OLEANDER              |
| HARRISON    | PLUTO OLEANDER              |
| ED          | PLUTO OLEANDER              |
| JOHNNY      | POCUS PULP                  |
| TOM         | POCUS PULP                  |
| RALPH       | POCUS PULP                  |
| GROUCHO     | POCUS PULP                  |
| RIVER       | POCUS PULP                  |
| VIVIEN      | POLISH BROOKLYN             |
| ELVIS       | POLISH BROOKLYN             |
| KEVIN       | POLISH BROOKLYN             |
| RIP         | POLISH BROOKLYN             |
| JAYNE       | POLISH BROOKLYN             |
| RALPH       | POLISH BROOKLYN             |
| MORGAN      | POLISH BROOKLYN             |
| FAY         | POLISH BROOKLYN             |
| IAN         | POLISH BROOKLYN             |
| ALAN        | POLISH BROOKLYN             |
| GOLDIE      | POLLOCK DELIVERANCE         |
| CARMEN      | POLLOCK DELIVERANCE         |
| DUSTIN      | POLLOCK DELIVERANCE         |
| GROUCHO     | POLLOCK DELIVERANCE         |
| BURT        | POLLOCK DELIVERANCE         |
| JULIA       | POLLOCK DELIVERANCE         |
| DARYL       | POND SEATTLE                |
| GENE        | POND SEATTLE                |
| RIVER       | POND SEATTLE                |
| JENNIFER    | POSEIDON FOREVER            |
| GRACE       | POSEIDON FOREVER            |
| SANDRA      | POSEIDON FOREVER            |
| PENELOPE    | POSEIDON FOREVER            |
| EWAN        | POSEIDON FOREVER            |
| REESE       | POSEIDON FOREVER            |
| BETTE       | POTLUCK MIXED               |
| SCARLETT    | POTLUCK MIXED               |
| MATTHEW     | POTLUCK MIXED               |
| KIM         | POTLUCK MIXED               |
| LAURENCE    | POTLUCK MIXED               |
| GREGORY     | POTLUCK MIXED               |
| WARREN      | POTTER CONNECTICUT          |
| WARREN      | POTTER CONNECTICUT          |
| CATE        | POTTER CONNECTICUT          |
| JANE        | POTTER CONNECTICUT          |
| WHOOPI      | POTTER CONNECTICUT          |
| AL          | POTTER CONNECTICUT          |
| AUDREY      | POTTER CONNECTICUT          |
| CHRISTIAN   | PREJUDICE OLEANDER          |
| MILLA       | PREJUDICE OLEANDER          |
| VAL         | PREJUDICE OLEANDER          |
| DUSTIN      | PREJUDICE OLEANDER          |
| RAY         | PREJUDICE OLEANDER          |
| ANGELA      | PREJUDICE OLEANDER          |
| CARY        | PREJUDICE OLEANDER          |
| SYLVESTER   | PREJUDICE OLEANDER          |
| KENNETH     | PREJUDICE OLEANDER          |
| MICHAEL     | PREJUDICE OLEANDER          |
| JULIA       | PRESIDENT BANG              |
| CUBA        | PRESIDENT BANG              |
| LUCILLE     | PRESIDENT BANG              |
| DEBBIE      | PRESIDENT BANG              |
| AUDREY      | PRESIDENT BANG              |
| GOLDIE      | PRIDE ALAMO                 |
| WARREN      | PRIDE ALAMO                 |
| CATE        | PRIDE ALAMO                 |
| GRETA       | PRIDE ALAMO                 |
| JOE         | PRIMARY GLASS               |
| KEVIN       | PRIMARY GLASS               |
| VAL         | PRIMARY GLASS               |
| MENA        | PRIMARY GLASS               |
| MARY        | PRIMARY GLASS               |
| CHARLIZE    | PRIMARY GLASS               |
| JAYNE       | PRIMARY GLASS               |
| CHRISTIAN   | PRINCESS GIANT              |
| ADAM        | PRINCESS GIANT              |
| MERYL       | PRINCESS GIANT              |
| HUMPHREY    | PRINCESS GIANT              |
| ED          | PRINCESS GIANT              |
| NICK        | PRIVATE DROP                |
| KIRSTEN     | PRIVATE DROP                |
| ELLEN       | PRIVATE DROP                |
| CAMERON     | PRIVATE DROP                |
| JON         | PRIVATE DROP                |
| KIRSTEN     | PRIX UNDEFEATED             |
| SISSY       | PRIX UNDEFEATED             |
| GOLDIE      | PRIX UNDEFEATED             |
| SUSAN       | PRIX UNDEFEATED             |
| SYLVESTER   | PRIX UNDEFEATED             |
| RUSSELL     | PRIX UNDEFEATED             |
| MORGAN      | PRIX UNDEFEATED             |
| OLYMPIA     | PSYCHO SHRUNK               |
| KIRSTEN     | PULP BEVERLY                |
| DUSTIN      | PULP BEVERLY                |
| SUSAN       | PULP BEVERLY                |
| WARREN      | PULP BEVERLY                |
| GRETA       | PULP BEVERLY                |
| WHOOPI      | PULP BEVERLY                |
| ANGELA      | PULP BEVERLY                |
| CHRISTIAN   | PUNK DIVORCE                |
| GOLDIE      | PUNK DIVORCE                |
| CHRISTIAN   | PUNK DIVORCE                |
| JAMES       | PUNK DIVORCE                |
| HARRISON    | PUNK DIVORCE                |
| MORGAN      | PUNK DIVORCE                |
| GEOFFREY    | PUNK DIVORCE                |
| CAMERON     | PURE RUNNER                 |
| MILLA       | PURE RUNNER                 |
| TOM         | PURPLE MOVIE                |
| FRANCES     | PURPLE MOVIE                |
| CHRIS       | PURPLE MOVIE                |
| DARYL       | PURPLE MOVIE                |
| FAY         | PURPLE MOVIE                |
| MENA        | PURPLE MOVIE                |
| MICHAEL     | PURPLE MOVIE                |
| AUDREY      | PURPLE MOVIE                |
| MARY        | QUEEN LUKE                  |
| RIP         | QUEEN LUKE                  |
| SPENCER     | QUEEN LUKE                  |
| EWAN        | QUEEN LUKE                  |
| RIVER       | QUEEN LUKE                  |
| JAYNE       | QUEEN LUKE                  |
| JUDY        | QUEST MUSSOLINI             |
| JUDE        | QUEST MUSSOLINI             |
| JAYNE       | QUEST MUSSOLINI             |
| GARY        | QUEST MUSSOLINI             |
| RENEE       | QUEST MUSSOLINI             |
| FAY         | QUILLS BULL                 |
| LISA        | QUILLS BULL                 |
| AUDREY      | QUILLS BULL                 |
| JOHN        | QUILLS BULL                 |
| ZERO        | RACER EGG                   |
| ANNE        | RACER EGG                   |
| FAY         | RACER EGG                   |
| ANGELINA    | RACER EGG                   |
| RALPH       | RACER EGG                   |
| BURT        | RACER EGG                   |
| SCARLETT    | RAGE GAMES                  |
| CHRIS       | RAGE GAMES                  |
| RENEE       | RAGE GAMES                  |
| ALBERT      | RAGE GAMES                  |
| KEVIN       | RAGE GAMES                  |
| JADA        | RAGE GAMES                  |
| GROUCHO     | RAGE GAMES                  |
| BOB         | RAGING AIRPLANE             |
| MINNIE      | RAGING AIRPLANE             |
| JOHN        | RAGING AIRPLANE             |
| JENNIFER    | RAIDERS ANTITRUST           |
| MILLA       | RAIDERS ANTITRUST           |
| KIRSTEN     | RAIDERS ANTITRUST           |
| KENNETH     | RAIDERS ANTITRUST           |
| WALTER      | RAIDERS ANTITRUST           |
| JADA        | RAIDERS ANTITRUST           |
| TOM         | RAINBOW SHOCK               |
| DUSTIN      | RAINBOW SHOCK               |
| KENNETH     | RAINBOW SHOCK               |
| JANE        | RAINBOW SHOCK               |
| KIM         | RAINBOW SHOCK               |
| GRETA       | RAINBOW SHOCK               |
| JENNIFER    | RANDOM GO                   |
| LUCILLE     | RANDOM GO                   |
| BURT        | RANDOM GO                   |
| REESE       | RANDOM GO                   |
| CARMEN      | RANDOM GO                   |
| JUDE        | RANDOM GO                   |
| ANGELA      | RANDOM GO                   |
| SPENCER     | RANDOM GO                   |
| HARRISON    | RANDOM GO                   |
| HARVEY      | RANDOM GO                   |
| NICK        | RANDOM GO                   |
| DEBBIE      | RANDOM GO                   |
| THORA       | RANDOM GO                   |
| RIP         | RANGE MOONWALKER            |
| BURT        | RANGE MOONWALKER            |
| PENELOPE    | RANGE MOONWALKER            |
| RUSSELL     | RANGE MOONWALKER            |
| CHRISTIAN   | REAP UNFAITHFUL             |
| KARL        | REAP UNFAITHFUL             |
| BURT        | REAP UNFAITHFUL             |
| ANNE        | REAP UNFAITHFUL             |
| FRED        | REAR TRADING                |
| DAN         | REAR TRADING                |
| LUCILLE     | REAR TRADING                |
| NATALIE     | REAR TRADING                |
| JUDE        | REAR TRADING                |
| KENNETH     | REAR TRADING                |
| PENELOPE    | REAR TRADING                |
| LAURENCE    | REAR TRADING                |
| UMA         | REBEL AIRPORT               |
| SEAN        | REBEL AIRPORT               |
| SPENCER     | REBEL AIRPORT               |
| SPENCER     | REBEL AIRPORT               |
| SALMA       | REBEL AIRPORT               |
| EMILY       | REBEL AIRPORT               |
| JAYNE       | RECORDS ZORRO               |
| BEN         | RECORDS ZORRO               |
| MORGAN      | RECORDS ZORRO               |
| RITA        | RECORDS ZORRO               |
| EWAN        | RECORDS ZORRO               |
| CHRISTOPHER | RECORDS ZORRO               |
| WILLIAM     | RECORDS ZORRO               |
| MERYL       | RECORDS ZORRO               |
| AUDREY      | REDEMPTION COMFORTS         |
| KENNETH     | REDEMPTION COMFORTS         |
| MILLA       | REDEMPTION COMFORTS         |
| ALBERT      | REDEMPTION COMFORTS         |
| DEBBIE      | REDEMPTION COMFORTS         |
| JENNIFER    | REDS POCUS                  |
| JODIE       | REDS POCUS                  |
| SPENCER     | REDS POCUS                  |
| CHRIS       | REDS POCUS                  |
| WARREN      | REDS POCUS                  |
| JOE         | REEF SALUTE                 |
| KENNETH     | REEF SALUTE                 |
| PENELOPE    | REEF SALUTE                 |
| MICHAEL     | REEF SALUTE                 |
| ALEC        | REIGN GENTLEMEN             |
| JOHNNY      | REIGN GENTLEMEN             |
| MORGAN      | REIGN GENTLEMEN             |
| JODIE       | REMEMBER DIARY              |
| KENNETH     | REMEMBER DIARY              |
| JEFF        | REMEMBER DIARY              |
| REESE       | REMEMBER DIARY              |
| ANNE        | REQUIEM TYCOON              |
| MENA        | REQUIEM TYCOON              |
| MARY        | REQUIEM TYCOON              |
| JESSICA     | REQUIEM TYCOON              |
| MICHELLE    | REQUIEM TYCOON              |
| CHRIS       | REQUIEM TYCOON              |
| JULIANNE    | REQUIEM TYCOON              |
| GRETA       | REQUIEM TYCOON              |
| CHRISTIAN   | RESERVOIR ADAPTATION        |
| JESSICA     | RESERVOIR ADAPTATION        |
| JIM         | RESERVOIR ADAPTATION        |
| MORGAN      | RESERVOIR ADAPTATION        |
| SCARLETT    | RESERVOIR ADAPTATION        |
| KIM         | RESERVOIR ADAPTATION        |
| JON         | RESERVOIR ADAPTATION        |
| GENE        | RESERVOIR ADAPTATION        |
| MENA        | RESURRECTION SILVERADO      |
| MAE         | RESURRECTION SILVERADO      |
| KEVIN       | RESURRECTION SILVERADO      |
| RICHARD     | RESURRECTION SILVERADO      |
| KENNETH     | RESURRECTION SILVERADO      |
| KARL        | REUNION WITCHES             |
| DAN         | REUNION WITCHES             |
| KIRSTEN     | REUNION WITCHES             |
| MEG         | REUNION WITCHES             |
| WALTER      | REUNION WITCHES             |
| RUSSELL     | REUNION WITCHES             |
| JAYNE       | REUNION WITCHES             |
| UMA         | RIDER CADDYSHACK            |
| ANNE        | RIDER CADDYSHACK            |
| SCARLETT    | RIDER CADDYSHACK            |
| JAMES       | RIDER CADDYSHACK            |
| WHOOPI      | RIDER CADDYSHACK            |
| BEN         | RIDER CADDYSHACK            |
| WILLIAM     | RIDER CADDYSHACK            |
| JEFF        | RIDER CADDYSHACK            |
| JULIA       | RIDER CADDYSHACK            |
| JOHNNY      | RIDGEMONT SUBMARINE         |
| JULIANNE    | RIDGEMONT SUBMARINE         |
| WHOOPI      | RIDGEMONT SUBMARINE         |
| MICHAEL     | RIDGEMONT SUBMARINE         |
| JULIA       | RIDGEMONT SUBMARINE         |
| ELVIS       | RIGHT CRANES                |
| BURT        | RIGHT CRANES                |
| PARKER      | RIGHT CRANES                |
| JESSICA     | RIGHT CRANES                |
| CAMERON     | RIGHT CRANES                |
| WHOOPI      | RIGHT CRANES                |
| ALBERT      | RIGHT CRANES                |
| JOHNNY      | RINGS HEARTBREAKERS         |
| RIP         | RINGS HEARTBREAKERS         |
| SANDRA      | RINGS HEARTBREAKERS         |
| JUDY        | RINGS HEARTBREAKERS         |
| NATALIE     | RINGS HEARTBREAKERS         |
| SYLVESTER   | RINGS HEARTBREAKERS         |
| CAMERON     | RINGS HEARTBREAKERS         |
| MORGAN      | RINGS HEARTBREAKERS         |
| MINNIE      | RINGS HEARTBREAKERS         |
| ED          | RINGS HEARTBREAKERS         |
| JEFF        | RINGS HEARTBREAKERS         |
| KIRSTEN     | RIVER OUTLAW                |
| GARY        | RIVER OUTLAW                |
| WARREN      | RIVER OUTLAW                |
| LISA        | RIVER OUTLAW                |
| HELEN       | ROAD ROXANNE                |
| KIRSTEN     | ROAD ROXANNE                |
| JULIA       | ROAD ROXANNE                |
| GARY        | ROAD ROXANNE                |
| CHRIS       | ROAD ROXANNE                |
| ALBERT      | ROAD ROXANNE                |
| LAURENCE    | ROAD ROXANNE                |
| CUBA        | ROAD ROXANNE                |
| MILLA       | ROBBERS JOON                |
| ANGELA      | ROBBERS JOON                |
| MATTHEW     | ROBBERS JOON                |
| CUBA        | ROBBERS JOON                |
| JADA        | ROBBERS JOON                |
| GOLDIE      | ROBBERY BRIGHT              |
| WHOOPI      | ROBBERY BRIGHT              |
| MILLA       | ROCK INSTINCT               |
| JOHNNY      | ROCK INSTINCT               |
| JULIA       | ROCK INSTINCT               |
| GARY        | ROCK INSTINCT               |
| JUDE        | ROCK INSTINCT               |
| CAMERON     | ROCK INSTINCT               |
| AL          | ROCK INSTINCT               |
| ED          | ROCK INSTINCT               |
| JUDY        | ROCKETEER MOTHER            |
| TOM         | ROCKETEER MOTHER            |
| CHRIS       | ROCKETEER MOTHER            |
| RENEE       | ROCKETEER MOTHER            |
| WARREN      | ROCKETEER MOTHER            |
| MERYL       | ROCKETEER MOTHER            |
| JAYNE       | ROCKETEER MOTHER            |
| SISSY       | ROCKY WAR                   |
| PENELOPE    | ROCKY WAR                   |
| RENEE       | ROCKY WAR                   |
| HARRISON    | ROLLERCOASTER BRINGING      |
| CATE        | ROLLERCOASTER BRINGING      |
| JON         | ROLLERCOASTER BRINGING      |
| JIM         | ROMAN PUNK                  |
| WARREN      | ROMAN PUNK                  |
| NICK        | ROOF CHAMPION               |
| ELVIS       | ROOF CHAMPION               |
| DAN         | ROOF CHAMPION               |
| SCARLETT    | ROOF CHAMPION               |
| WHOOPI      | ROOF CHAMPION               |
| WOODY       | ROOM ROMAN                  |
| SEAN        | ROOM ROMAN                  |
| JOHNNY      | ROOTS REMEMBER              |
| BURT        | ROOTS REMEMBER              |
| ELLEN       | ROOTS REMEMBER              |
| WALTER      | ROOTS REMEMBER              |
| WARREN      | ROOTS REMEMBER              |
| CAMERON     | ROOTS REMEMBER              |
| EWAN        | ROOTS REMEMBER              |
| GROUCHO     | ROOTS REMEMBER              |
| LISA        | ROOTS REMEMBER              |
| MATTHEW     | ROOTS REMEMBER              |
| CUBA        | ROSES TREASURE              |
| MORGAN      | ROSES TREASURE              |
| HUMPHREY    | ROSES TREASURE              |
| BURT        | ROSES TREASURE              |
| MARY        | ROSES TREASURE              |
| PENELOPE    | ROUGE SQUAD                 |
| EWAN        | ROUGE SQUAD                 |
| JON         | ROUGE SQUAD                 |
| REESE       | ROUGE SQUAD                 |
| JOHNNY      | ROXANNE REBEL               |
| RIP         | ROXANNE REBEL               |
| MILLA       | ROXANNE REBEL               |
| LUCILLE     | ROXANNE REBEL               |
| JOHN        | ROXANNE REBEL               |
| JUDY        | RUGRATS SHAKESPEARE         |
| GARY        | RUGRATS SHAKESPEARE         |
| DARYL       | RUGRATS SHAKESPEARE         |
| MORGAN      | RUGRATS SHAKESPEARE         |
| KIM         | RUGRATS SHAKESPEARE         |
| CUBA        | RUGRATS SHAKESPEARE         |
| PENELOPE    | RULES HUMAN                 |
| DUSTIN      | RULES HUMAN                 |
| CARY        | RULES HUMAN                 |
| KEVIN       | RULES HUMAN                 |
| HARVEY      | RULES HUMAN                 |
| BOB         | RUN PACIFIC                 |
| GARY        | RUN PACIFIC                 |
| DAN         | RUN PACIFIC                 |
| MAE         | RUN PACIFIC                 |
| WOODY       | RUN PACIFIC                 |
| SIDNEY      | RUN PACIFIC                 |
| NICK        | RUNAWAY TENENBAUMS          |
| WARREN      | RUNAWAY TENENBAUMS          |
| GENE        | RUNAWAY TENENBAUMS          |
| MATTHEW     | RUNNER MADIGAN              |
| JOE         | RUNNER MADIGAN              |
| BOB         | RUNNER MADIGAN              |
| CHRISTIAN   | RUNNER MADIGAN              |
| GREG        | RUNNER MADIGAN              |
| GROUCHO     | RUNNER MADIGAN              |
| CATE        | RUNNER MADIGAN              |
| REESE       | RUNNER MADIGAN              |
| KIRK        | RUSH GOODFELLAS             |
| MAE         | RUSH GOODFELLAS             |
| SYLVESTER   | RUSH GOODFELLAS             |
| ANGELA      | RUSH GOODFELLAS             |
| ALAN        | RUSH GOODFELLAS             |
| NICK        | RUSHMORE MERMAID            |
| MILLA       | RUSHMORE MERMAID            |
| JOHNNY      | RUSHMORE MERMAID            |
| PENELOPE    | RUSHMORE MERMAID            |
| HENRY       | RUSHMORE MERMAID            |
| HARRISON    | RUSHMORE MERMAID            |
| FAY         | RUSHMORE MERMAID            |
| KEVIN       | SABRINA MIDNIGHT            |
| CHRISTIAN   | SABRINA MIDNIGHT            |
| MEG         | SABRINA MIDNIGHT            |
| CHRIS       | SABRINA MIDNIGHT            |
| BOB         | SADDLE ANTITRUST            |
| ADAM        | SADDLE ANTITRUST            |
| MINNIE      | SADDLE ANTITRUST            |
| LUCILLE     | SAGEBRUSH CLUELESS          |
| FRANCES     | SAGEBRUSH CLUELESS          |
| SEAN        | SAGEBRUSH CLUELESS          |
| MEG         | SAGEBRUSH CLUELESS          |
| MORGAN      | SAGEBRUSH CLUELESS          |
| IAN         | SAGEBRUSH CLUELESS          |
| ALAN        | SAGEBRUSH CLUELESS          |
| GRACE       | SAINTS BRIDE                |
| FRED        | SAINTS BRIDE                |
| RIP         | SAINTS BRIDE                |
| SUSAN       | SAINTS BRIDE                |
| MORGAN      | SAINTS BRIDE                |
| MENA        | SAINTS BRIDE                |
| GROUCHO     | SAINTS BRIDE                |
| JON         | SAINTS BRIDE                |
| REESE       | SAINTS BRIDE                |
| MARY        | SAINTS BRIDE                |
| VIVIEN      | SALUTE APOLLO               |
| SPENCER     | SALUTE APOLLO               |
| CATE        | SALUTE APOLLO               |
| JADA        | SALUTE APOLLO               |
| ANGELINA    | SAMURAI LION                |
| GREG        | SAMURAI LION                |
| KENNETH     | SANTA PARIS                 |
| SCARLETT    | SANTA PARIS                 |
| MINNIE      | SANTA PARIS                 |
| RUSSELL     | SANTA PARIS                 |
| OLYMPIA     | SANTA PARIS                 |
| MICHAEL     | SANTA PARIS                 |
| GROUCHO     | SASSY PACKER                |
| ANGELA      | SASSY PACKER                |
| LISA        | SASSY PACKER                |
| CAMERON     | SATISFACTION CONFIDENTIAL   |
| GROUCHO     | SATISFACTION CONFIDENTIAL   |
| KEVIN       | SATISFACTION CONFIDENTIAL   |
| GENE        | SATISFACTION CONFIDENTIAL   |
| JOHN        | SATISFACTION CONFIDENTIAL   |
| VIVIEN      | SATURDAY LAMBS              |
| RIP         | SATURDAY LAMBS              |
| PENELOPE    | SATURDAY LAMBS              |
| BURT        | SATURDAY LAMBS              |
| BEN         | SATURDAY LAMBS              |
| JAMES       | SATURDAY LAMBS              |
| GRETA       | SATURDAY LAMBS              |
| MENA        | SATURDAY LAMBS              |
| GENE        | SATURDAY LAMBS              |
| ANGELINA    | SATURN NAME                 |
| CHRIS       | SATURN NAME                 |
| GRACE       | SAVANNAH TOWN               |
| SANDRA      | SAVANNAH TOWN               |
| PARKER      | SAVANNAH TOWN               |
| CHRISTIAN   | SAVANNAH TOWN               |
| JESSICA     | SAVANNAH TOWN               |
| MINNIE      | SAVANNAH TOWN               |
| REESE       | SCALAWAG DUCK               |
| JUDE        | SCALAWAG DUCK               |
| CHRISTIAN   | SCALAWAG DUCK               |
| GROUCHO     | SCALAWAG DUCK               |
| CHRIS       | SCALAWAG DUCK               |
| PARKER      | SCARFACE BANG               |
| ELLEN       | SCARFACE BANG               |
| CATE        | SCARFACE BANG               |
| EMILY       | SCARFACE BANG               |
| BEN         | SCARFACE BANG               |
| IAN         | SCARFACE BANG               |
| RENEE       | SCARFACE BANG               |
| MATTHEW     | SCHOOL JACKET               |
| DAN         | SCHOOL JACKET               |
| MARY        | SCHOOL JACKET               |
| MAE         | SCHOOL JACKET               |
| CHRIS       | SCHOOL JACKET               |
| ED          | SCHOOL JACKET               |
| JAYNE       | SCHOOL JACKET               |
| REESE       | SCHOOL JACKET               |
| GRACE       | SCISSORHANDS SLUMS          |
| HELEN       | SCISSORHANDS SLUMS          |
| JULIA       | SCISSORHANDS SLUMS          |
| JANE        | SCISSORHANDS SLUMS          |
| ROCK        | SCISSORHANDS SLUMS          |
| MATTHEW     | SCORPION APOLLO             |
| BOB         | SCORPION APOLLO             |
| JULIA       | SCORPION APOLLO             |
| HENRY       | SCORPION APOLLO             |
| SEAN        | SCORPION APOLLO             |
| LIZA        | SCORPION APOLLO             |
| KEVIN       | SCORPION APOLLO             |
| GROUCHO     | SCORPION APOLLO             |
| GOLDIE      | SEA VIRGIN                  |
| DUSTIN      | SEA VIRGIN                  |
| GARY        | SEA VIRGIN                  |
| RUSSELL     | SEA VIRGIN                  |
| CATE        | SEA VIRGIN                  |
| EMILY       | SEA VIRGIN                  |
| WILLIAM     | SEA VIRGIN                  |
| HUMPHREY    | SEA VIRGIN                  |
| ADAM        | SEABISCUIT PUNK             |
| SEAN        | SEABISCUIT PUNK             |
| ROCK        | SEABISCUIT PUNK             |
| SUSAN       | SEARCHERS WAIT              |
| GINA        | SEARCHERS WAIT              |
| CATE        | SEARCHERS WAIT              |
| ROCK        | SEARCHERS WAIT              |
| ELVIS       | SEATTLE EXPECATIONS         |
| MILLA       | SEATTLE EXPECATIONS         |
| KENNETH     | SEATTLE EXPECATIONS         |
| SCARLETT    | SEATTLE EXPECATIONS         |
| FAY         | SEATTLE EXPECATIONS         |
| GREGORY     | SEATTLE EXPECATIONS         |
| FAY         | SECRET GROUNDHOG            |
| MAE         | SECRET GROUNDHOG            |
| ANGELA      | SECRET GROUNDHOG            |
| JULIA       | SECRETARY ROUGE             |
| BEN         | SECRETARY ROUGE             |
| ELLEN       | SECRETARY ROUGE             |
| CAMERON     | SECRETARY ROUGE             |
| JAYNE       | SECRETARY ROUGE             |
| JEFF        | SECRETARY ROUGE             |
| REESE       | SECRETS PARADISE            |
| GENE        | SECRETS PARADISE            |
| RENEE       | SECRETS PARADISE            |
| WHOOPI      | SECRETS PARADISE            |
| KENNETH     | SECRETS PARADISE            |
| WILLIAM     | SECRETS PARADISE            |
| FRED        | SENSE GREEK                 |
| AUDREY      | SENSE GREEK                 |
| JODIE       | SENSE GREEK                 |
| SPENCER     | SENSE GREEK                 |
| AL          | SENSE GREEK                 |
| OLYMPIA     | SENSE GREEK                 |
| RENEE       | SENSE GREEK                 |
| CHRISTIAN   | SENSIBILITY REAR            |
| MILLA       | SENSIBILITY REAR            |
| BURT        | SENSIBILITY REAR            |
| GROUCHO     | SENSIBILITY REAR            |
| LIZA        | SENSIBILITY REAR            |
| MICHAEL     | SENSIBILITY REAR            |
| CAMERON     | SEVEN SWARM                 |
| DAN         | SEVEN SWARM                 |
| CAMERON     | SEVEN SWARM                 |
| ANGELINA    | SEVEN SWARM                 |
| GINA        | SEVEN SWARM                 |
| ED          | SEVEN SWARM                 |
| JAYNE       | SEVEN SWARM                 |
| CHRISTIAN   | SHAKESPEARE SADDLE          |
| SANDRA      | SHAKESPEARE SADDLE          |
| JAMES       | SHAKESPEARE SADDLE          |
| CHRIS       | SHAKESPEARE SADDLE          |
| WARREN      | SHAKESPEARE SADDLE          |
| RUSSELL     | SHAKESPEARE SADDLE          |
| CUBA        | SHANE DARKNESS              |
| HENRY       | SHANE DARKNESS              |
| RENEE       | SHANE DARKNESS              |
| LUCILLE     | SHANGHAI TYCOON             |
| JODIE       | SHANGHAI TYCOON             |
| NICK        | SHANGHAI TYCOON             |
| HENRY       | SHANGHAI TYCOON             |
| BEN         | SHANGHAI TYCOON             |
| DAN         | SHANGHAI TYCOON             |
| LAURA       | SHANGHAI TYCOON             |
| JULIA       | SHANGHAI TYCOON             |
| BOB         | SHAWSHANK BUBBLE            |
| VAL         | SHAWSHANK BUBBLE            |
| KENNETH     | SHAWSHANK BUBBLE            |
| SYLVESTER   | SHAWSHANK BUBBLE            |
| RENEE       | SHAWSHANK BUBBLE            |
| SCARLETT    | SHAWSHANK BUBBLE            |
| ANGELA      | SHAWSHANK BUBBLE            |
| IAN         | SHAWSHANK BUBBLE            |
| CHRISTOPHER | SHAWSHANK BUBBLE            |
| JULIA       | SHAWSHANK BUBBLE            |
| SYLVESTER   | SHEPHERD MIDSUMMER          |
| WARREN      | SHEPHERD MIDSUMMER          |
| JULIANNE    | SHEPHERD MIDSUMMER          |
| OPRAH       | SHEPHERD MIDSUMMER          |
| MERYL       | SHEPHERD MIDSUMMER          |
| JULIA       | SHINING ROSES               |
| WOODY       | SHINING ROSES               |
| SUSAN       | SHINING ROSES               |
| CATE        | SHINING ROSES               |
| HUMPHREY    | SHINING ROSES               |
| AUDREY      | SHIP WONDERLAND             |
| MAE         | SHIP WONDERLAND             |
| RALPH       | SHIP WONDERLAND             |
| KENNETH     | SHIP WONDERLAND             |
| CUBA        | SHIP WONDERLAND             |
| WARREN      | SHIP WONDERLAND             |
| NICK        | SHIP WONDERLAND             |
| CUBA        | SHIP WONDERLAND             |
| LAURA       | SHOCK CABIN                 |
| WOODY       | SHOOTIST SUPERFLY           |
| JULIA       | SHOOTIST SUPERFLY           |
| FAY         | SHOOTIST SUPERFLY           |
| KENNETH     | SHOW LORD                   |
| KEVIN       | SHOW LORD                   |
| FRANCES     | SHREK LICENSE               |
| RIVER       | SHREK LICENSE               |
| EMILY       | SHREK LICENSE               |
| WOODY       | SHRUNK DIVINE               |
| SISSY       | SHRUNK DIVINE               |
| TOM         | SHRUNK DIVINE               |
| MARY        | SHRUNK DIVINE               |
| HELEN       | SIDE ARK                    |
| AUDREY      | SIDE ARK                    |
| JADA        | SIDE ARK                    |
| CHRIS       | SIDE ARK                    |
| LAURENCE    | SIDE ARK                    |
| JAYNE       | SIDE ARK                    |
| CUBA        | SIEGE MADRE                 |
| RIP         | SIEGE MADRE                 |
| NATALIE     | SIEGE MADRE                 |
| DAN         | SIEGE MADRE                 |
| SIDNEY      | SIEGE MADRE                 |
| SALMA       | SIEGE MADRE                 |
| BELA        | SIEGE MADRE                 |
| JIM         | SIERRA DIVIDE               |
| WALTER      | SIERRA DIVIDE               |
| GINA        | SIERRA DIVIDE               |
| RUSSELL     | SIERRA DIVIDE               |
| MARY        | SIERRA DIVIDE               |
| SANDRA      | SILENCE KANE                |
| REESE       | SILENCE KANE                |
| RENEE       | SILENCE KANE                |
| MICHAEL     | SILENCE KANE                |
| JENNIFER    | SILVERADO GOLDFINGER        |
| KIRSTEN     | SILVERADO GOLDFINGER        |
| TOM         | SILVERADO GOLDFINGER        |
| JANE        | SILVERADO GOLDFINGER        |
| AL          | SILVERADO GOLDFINGER        |
| JOHNNY      | SIMON NORTH                 |
| JODIE       | SIMON NORTH                 |
| VIVIEN      | SIMON NORTH                 |
| HELEN       | SINNERS ATLANTIS            |
| CHRISTIAN   | SINNERS ATLANTIS            |
| LAURA       | SINNERS ATLANTIS            |
| LAURENCE    | SINNERS ATLANTIS            |
| SUSAN       | SISTER FREDDY               |
| HUMPHREY    | SISTER FREDDY               |
| GREGORY     | SISTER FREDDY               |
| ELVIS       | SKY MIRACLE                 |
| SISSY       | SKY MIRACLE                 |
| WOODY       | SKY MIRACLE                 |
| KIRSTEN     | SKY MIRACLE                 |
| WALTER      | SKY MIRACLE                 |
| WARREN      | SKY MIRACLE                 |
| MERYL       | SKY MIRACLE                 |
| GRETA       | SKY MIRACLE                 |
| LAURA       | SKY MIRACLE                 |
| LAURENCE    | SKY MIRACLE                 |
| JON         | SKY MIRACLE                 |
| AUDREY      | SKY MIRACLE                 |
| KIRSTEN     | SLEEPING SUSPECTS           |
| SANDRA      | SLEEPING SUSPECTS           |
| MILLA       | SLEEPING SUSPECTS           |
| WILL        | SLEEPING SUSPECTS           |
| GRACE       | SLEEPLESS MONSOON           |
| JULIA       | SLEEPLESS MONSOON           |
| HENRY       | SLEEPLESS MONSOON           |
| DARYL       | SLEEPLESS MONSOON           |
| GRACE       | SLEEPY JAPANESE             |
| ADAM        | SLEEPY JAPANESE             |
| RICHARD     | SLEEPY JAPANESE             |
| ED          | SLEEPY JAPANESE             |
| AUDREY      | SLEEPY JAPANESE             |
| MARY        | SLEEPY JAPANESE             |
| RALPH       | SLEUTH ORIENT               |
| CHRISTOPHER | SLEUTH ORIENT               |
| MORGAN      | SLEUTH ORIENT               |
| HARVEY      | SLEUTH ORIENT               |
| AL          | SLEUTH ORIENT               |
| WILL        | SLEUTH ORIENT               |
| BURT        | SLEUTH ORIENT               |
| DAN         | SLING LUKE                  |
| GREG        | SLING LUKE                  |
| ED          | SLING LUKE                  |
| CAMERON     | SLIPPER FIDELITY            |
| JAMES       | SLIPPER FIDELITY            |
| GRETA       | SLIPPER FIDELITY            |
| JANE        | SLIPPER FIDELITY            |
| AL          | SLIPPER FIDELITY            |
| MICHAEL     | SLIPPER FIDELITY            |
| JEFF        | SLIPPER FIDELITY            |
| REESE       | SLUMS DUCK                  |
| WALTER      | SLUMS DUCK                  |
| RUSSELL     | SLUMS DUCK                  |
| NICK        | SMILE EARRING               |
| JOHNNY      | SMILE EARRING               |
| JOE         | SMILE EARRING               |
| ANNE        | SMILE EARRING               |
| GROUCHO     | SMILE EARRING               |
| RUSSELL     | SMILE EARRING               |
| ED          | SMILE EARRING               |
| JEFF        | SMILE EARRING               |
| KARL        | SMOKING BARBARELLA          |
| ALEC        | SMOKING BARBARELLA          |
| CARMEN      | SMOKING BARBARELLA          |
| MINNIE      | SMOKING BARBARELLA          |
| RENEE       | SMOKING BARBARELLA          |
| VIVIEN      | SMOKING BARBARELLA          |
| DARYL       | SMOOCHY CONTROL             |
| JAYNE       | SMOOCHY CONTROL             |
| SCARLETT    | SNATCH SLIPPER              |
| CATE        | SNATCH SLIPPER              |
| RITA        | SNATCH SLIPPER              |
| JOE         | SNATCHERS MONTEZUMA         |
| TIM         | SNATCHERS MONTEZUMA         |
| GOLDIE      | SNATCHERS MONTEZUMA         |
| FAY         | SNATCHERS MONTEZUMA         |
| SPENCER     | SNATCHERS MONTEZUMA         |
| KENNETH     | SNATCHERS MONTEZUMA         |
| ROCK        | SNATCHERS MONTEZUMA         |
| BELA        | SNATCHERS MONTEZUMA         |
| REESE       | SNATCHERS MONTEZUMA         |
| UMA         | SNOWMAN ROLLERCOASTER       |
| WOODY       | SNOWMAN ROLLERCOASTER       |
| MATTHEW     | SNOWMAN ROLLERCOASTER       |
| JOHNNY      | SOLDIERS EVOLUTION          |
| UMA         | SOLDIERS EVOLUTION          |
| CUBA        | SOLDIERS EVOLUTION          |
| JUDY        | SOLDIERS EVOLUTION          |
| SEAN        | SOLDIERS EVOLUTION          |
| RUSSELL     | SOLDIERS EVOLUTION          |
| MINNIE      | SOLDIERS EVOLUTION          |
| ED          | SOLDIERS EVOLUTION          |
| MARY        | SOLDIERS EVOLUTION          |
| ED          | SOMETHING DUCK              |
| LAURA       | SOMETHING DUCK              |
| MICHAEL     | SOMETHING DUCK              |
| KENNETH     | SONG HEDWIG                 |
| KEVIN       | SONG HEDWIG                 |
| DEBBIE      | SONG HEDWIG                 |
| GREGORY     | SONG HEDWIG                 |
| JOHN        | SONG HEDWIG                 |
| SANDRA      | SONS INTERVIEW              |
| PARKER      | SONS INTERVIEW              |
| WHOOPI      | SONS INTERVIEW              |
| HUMPHREY    | SONS INTERVIEW              |
| JEFF        | SONS INTERVIEW              |
| CUBA        | SONS INTERVIEW              |
| RIP         | SORORITY QUEEN              |
| CATE        | SORORITY QUEEN              |
| RIVER       | SORORITY QUEEN              |
| BEN         | SORORITY QUEEN              |
| MATTHEW     | SOUP WISDOM                 |
| KIM         | SOUP WISDOM                 |
| MICHELLE    | SOUTH WAIT                  |
| GARY        | SOUTH WAIT                  |
| CHRIS       | SPARTACUS CHEAPER           |
| VIVIEN      | SPARTACUS CHEAPER           |
| JEFF        | SPARTACUS CHEAPER           |
| NICK        | SPEAKEASY DATE              |
| KIRSTEN     | SPEAKEASY DATE              |
| HARVEY      | SPEAKEASY DATE              |
| BETTE       | SPEED SUIT                  |
| SANDRA      | SPEED SUIT                  |
| MEG         | SPEED SUIT                  |
| DARYL       | SPEED SUIT                  |
| CHRIS       | SPEED SUIT                  |
| WILL        | SPEED SUIT                  |
| ED          | SPICE SORORITY              |
| WOODY       | SPICE SORORITY              |
| TOM         | SPICE SORORITY              |
| KIRK        | SPICE SORORITY              |
| FAY         | SPICE SORORITY              |
| SCARLETT    | SPICE SORORITY              |
| MORGAN      | SPICE SORORITY              |
| MICHAEL     | SPICE SORORITY              |
| JON         | SPICE SORORITY              |
| GENE        | SPICE SORORITY              |
| GREGORY     | SPICE SORORITY              |
| DARYL       | SPIKING ELEMENT             |
| SUSAN       | SPIKING ELEMENT             |
| WALTER      | SPIKING ELEMENT             |
| WILLIAM     | SPIKING ELEMENT             |
| DEBBIE      | SPIKING ELEMENT             |
| BURT        | SPIKING ELEMENT             |
| CAMERON     | SPINAL ROCKY                |
| PARKER      | SPINAL ROCKY                |
| NATALIE     | SPINAL ROCKY                |
| MARY        | SPINAL ROCKY                |
| CHRISTOPHER | SPINAL ROCKY                |
| CHRIS       | SPINAL ROCKY                |
| RUSSELL     | SPINAL ROCKY                |
| CATE        | SPINAL ROCKY                |
| JULIA       | SPIRIT FLINTSTONES          |
| PARKER      | SPIRIT FLINTSTONES          |
| HENRY       | SPIRIT FLINTSTONES          |
| JAMES       | SPIRIT FLINTSTONES          |
| SPENCER     | SPIRIT FLINTSTONES          |
| PENELOPE    | SPIRIT FLINTSTONES          |
| WHOOPI      | SPIRIT FLINTSTONES          |
| RIVER       | SPIRIT FLINTSTONES          |
| VIVIEN      | SPIRIT FLINTSTONES          |
| MICHAEL     | SPIRIT FLINTSTONES          |
| GREGORY     | SPIRIT FLINTSTONES          |
| GOLDIE      | SPIRITED CASUALTIES         |
| CHRISTIAN   | SPIRITED CASUALTIES         |
| SIDNEY      | SPIRITED CASUALTIES         |
| GINA        | SPIRITED CASUALTIES         |
| RENEE       | SPIRITED CASUALTIES         |
| PENELOPE    | SPLASH GUMP                 |
| JENNIFER    | SPLASH GUMP                 |
| UMA         | SPLASH GUMP                 |
| CAMERON     | SPLASH GUMP                 |
| CHRISTIAN   | SPLASH GUMP                 |
| RAY         | SPLASH GUMP                 |
| GENE        | SPLASH GUMP                 |
| MORGAN      | SPLASH GUMP                 |
| HUMPHREY    | SPLASH GUMP                 |
| AL          | SPLASH GUMP                 |
| UMA         | SPLENDOR PATTON             |
| SANDRA      | SPLENDOR PATTON             |
| KIRK        | SPLENDOR PATTON             |
| ADAM        | SPLENDOR PATTON             |
| BEN         | SPLENDOR PATTON             |
| CHARLIZE    | SPLENDOR PATTON             |
| CHRISTOPHER | SPLENDOR PATTON             |
| AL          | SPLENDOR PATTON             |
| GROUCHO     | SPLENDOR PATTON             |
| BELA        | SPLENDOR PATTON             |
| RIP         | SPOILERS HELLFIGHTERS       |
| MICHELLE    | SPOILERS HELLFIGHTERS       |
| MILLA       | SPOILERS HELLFIGHTERS       |
| DARYL       | SPOILERS HELLFIGHTERS       |
| HUMPHREY    | SPOILERS HELLFIGHTERS       |
| GREGORY     | SPOILERS HELLFIGHTERS       |
| BURT        | SPOILERS HELLFIGHTERS       |
| WOODY       | SPY MILE                    |
| JOHNNY      | SPY MILE                    |
| HENRY       | SPY MILE                    |
| ELLEN       | SPY MILE                    |
| JIM         | SPY MILE                    |
| SIDNEY      | SPY MILE                    |
| WHOOPI      | SPY MILE                    |
| GRETA       | SPY MILE                    |
| AUDREY      | SQUAD FISH                  |
| PARKER      | SQUAD FISH                  |
| MILLA       | SQUAD FISH                  |
| FRANCES     | SQUAD FISH                  |
| MATTHEW     | SQUAD FISH                  |
| WALTER      | STAGE WORLD                 |
| BELA        | STAGE WORLD                 |
| KARL        | STAGECOACH ARMAGEDDON       |
| SANDRA      | STAGECOACH ARMAGEDDON       |
| WOODY       | STAGECOACH ARMAGEDDON       |
| SEAN        | STAGECOACH ARMAGEDDON       |
| KIRSTEN     | STAGECOACH ARMAGEDDON       |
| MORGAN      | STAGECOACH ARMAGEDDON       |
| VAL         | STALLION SUNDANCE           |
| TOM         | STALLION SUNDANCE           |
| RIP         | STALLION SUNDANCE           |
| WOODY       | STALLION SUNDANCE           |
| KENNETH     | STALLION SUNDANCE           |
| KEVIN       | STALLION SUNDANCE           |
| JON         | STALLION SUNDANCE           |
| VAL         | STAMPEDE DISTURBING         |
| NATALIE     | STAMPEDE DISTURBING         |
| RIP         | STAMPEDE DISTURBING         |
| MAE         | STAMPEDE DISTURBING         |
| CATE        | STAMPEDE DISTURBING         |
| VIVIEN      | STAMPEDE DISTURBING         |
| JOHNNY      | STAR OPERATION              |
| SUSAN       | STAR OPERATION              |
| MORGAN      | STAR OPERATION              |
| MORGAN      | STAR OPERATION              |
| WILL        | STAR OPERATION              |
| DAN         | STATE WASTELAND             |
| SANDRA      | STATE WASTELAND             |
| PENELOPE    | STATE WASTELAND             |
| ED          | STATE WASTELAND             |
| JADA        | STATE WASTELAND             |
| MERYL       | STATE WASTELAND             |
| WILLIAM     | STATE WASTELAND             |
| UMA         | STEEL SANTA                 |
| JAMES       | STEEL SANTA                 |
| MARY        | STEEL SANTA                 |
| DAN         | STEERS ARMAGEDDON           |
| DAN         | STEERS ARMAGEDDON           |
| FAY         | STEERS ARMAGEDDON           |
| OPRAH       | STEERS ARMAGEDDON           |
| WALTER      | STEPMOM DREAM               |
| ANGELA      | STEPMOM DREAM               |
| DEBBIE      | STEPMOM DREAM               |
| MICHAEL     | STEPMOM DREAM               |
| GRACE       | STING PERSONAL              |
| AUDREY      | STING PERSONAL              |
| GENE        | STING PERSONAL              |
| SPENCER     | STING PERSONAL              |
| HARRISON    | STING PERSONAL              |
| KEVIN       | STING PERSONAL              |
| BEN         | STING PERSONAL              |
| VIVIEN      | STOCK GLASS                 |
| GARY        | STOCK GLASS                 |
| CAMERON     | STOCK GLASS                 |
| LIZA        | STOCK GLASS                 |
| MINNIE      | STOCK GLASS                 |
| KENNETH     | STOCK GLASS                 |
| JEFF        | STOCK GLASS                 |
| MILLA       | STONE FIRE                  |
| CHRISTOPHER | STORM HAPPINESS             |
| GINA        | STORM HAPPINESS             |
| CATE        | STORM HAPPINESS             |
| IAN         | STORM HAPPINESS             |
| KENNETH     | STORM HAPPINESS             |
| OLYMPIA     | STORM HAPPINESS             |
| ROCK        | STORM HAPPINESS             |
| GREGORY     | STORM HAPPINESS             |
| ZERO        | STORY SIDE                  |
| ANGELINA    | STORY SIDE                  |
| SPENCER     | STORY SIDE                  |
| HARVEY      | STORY SIDE                  |
| RUSSELL     | STORY SIDE                  |
| DAN         | STRAIGHT HOURS              |
| HUMPHREY    | STRAIGHT HOURS              |
| BURT        | STRAIGHT HOURS              |
| JUDE        | STRANGELOVE DESIRE          |
| RAY         | STRANGELOVE DESIRE          |
| ANGELA      | STRANGELOVE DESIRE          |
| GROUCHO     | STRANGELOVE DESIRE          |
| WALTER      | STRANGELOVE DESIRE          |
| CUBA        | STRANGELOVE DESIRE          |
| ALAN        | STRANGELOVE DESIRE          |
| MICHAEL     | STRANGELOVE DESIRE          |
| ED          | STRANGELOVE DESIRE          |
| HELEN       | STRANGER STRANGERS          |
| SANDRA      | STRANGER STRANGERS          |
| AUDREY      | STRANGER STRANGERS          |
| VAL         | STRANGER STRANGERS          |
| TOM         | STRANGER STRANGERS          |
| DUSTIN      | STRANGER STRANGERS          |
| MAE         | STRANGER STRANGERS          |
| MICHAEL     | STRANGER STRANGERS          |
| CUBA        | STRANGER STRANGERS          |
| ZERO        | STRANGERS GRAFFITI          |
| JULIA       | STRANGERS GRAFFITI          |
| NICK        | STRANGERS GRAFFITI          |
| SEAN        | STRANGERS GRAFFITI          |
| JAYNE       | STRANGERS GRAFFITI          |
| SANDRA      | STREAK RIDGEMONT            |
| SEAN        | STREAK RIDGEMONT            |
| DARYL       | STREAK RIDGEMONT            |
| VIVIEN      | STREETCAR INTENTIONS        |
| SANDRA      | STREETCAR INTENTIONS        |
| CHRISTIAN   | STREETCAR INTENTIONS        |
| MICHELLE    | STREETCAR INTENTIONS        |
| ELLEN       | STREETCAR INTENTIONS        |
| RUSSELL     | STREETCAR INTENTIONS        |
| LAURENCE    | STREETCAR INTENTIONS        |
| GREG        | STRICTLY SCARFACE           |
| DARYL       | STRICTLY SCARFACE           |
| WHOOPI      | STRICTLY SCARFACE           |
| ALAN        | STRICTLY SCARFACE           |
| JENNIFER    | SUBMARINE BED               |
| PENELOPE    | SUBMARINE BED               |
| CHRISTIAN   | SUBMARINE BED               |
| RALPH       | SUBMARINE BED               |
| SEAN        | SUBMARINE BED               |
| SIDNEY      | SUBMARINE BED               |
| GROUCHO     | SUBMARINE BED               |
| WARREN      | SUBMARINE BED               |
| SCARLETT    | SUBMARINE BED               |
| GREGORY     | SUBMARINE BED               |
| MARY        | SUBMARINE BED               |
| MATTHEW     | SUGAR WONKA                 |
| CHRISTOPHER | SUGAR WONKA                 |
| GINA        | SUGAR WONKA                 |
| JADA        | SUGAR WONKA                 |
| JON         | SUGAR WONKA                 |
| RAY         | SUICIDES SILENCE            |
| JULIANNE    | SUICIDES SILENCE            |
| FRANCES     | SUICIDES SILENCE            |
| TOM         | SUIT WALLS                  |
| PENELOPE    | SUIT WALLS                  |
| JESSICA     | SUIT WALLS                  |
| MORGAN      | SUIT WALLS                  |
| GENE        | SUIT WALLS                  |
| ALEC        | SUMMER SCARFACE             |
| DAN         | SUMMER SCARFACE             |
| DUSTIN      | SUMMER SCARFACE             |
| ANGELINA    | SUMMER SCARFACE             |
| MEG         | SUMMER SCARFACE             |
| EWAN        | SUMMER SCARFACE             |
| CATE        | SUMMER SCARFACE             |
| RUSSELL     | SUMMER SCARFACE             |
| DAN         | SUN CONFESSIONS             |
| LUCILLE     | SUN CONFESSIONS             |
| SYLVESTER   | SUN CONFESSIONS             |
| CATE        | SUN CONFESSIONS             |
| JADA        | SUN CONFESSIONS             |
| KENNETH     | SUNDANCE INVASION           |
| CHARLIZE    | SUNDANCE INVASION           |
| SIDNEY      | SUNDANCE INVASION           |
| RENEE       | SUNDANCE INVASION           |
| FAY         | SUNDANCE INVASION           |
| LAURENCE    | SUNDANCE INVASION           |
| DEBBIE      | SUNDANCE INVASION           |
| JOHNNY      | SUNRISE LEAGUE              |
| JOE         | SUNRISE LEAGUE              |
| TOM         | SUNRISE LEAGUE              |
| SEAN        | SUNRISE LEAGUE              |
| RUSSELL     | SUNRISE LEAGUE              |
| ANGELINA    | SUNSET RACER                |
| GROUCHO     | SUNSET RACER                |
| MORGAN      | SUNSET RACER                |
| TOM         | SUPER WYOMING               |
| NICK        | SUPER WYOMING               |
| HUMPHREY    | SUPER WYOMING               |
| JOHNNY      | SUPERFLY TRIP               |
| DAN         | SUPERFLY TRIP               |
| SEAN        | SUPERFLY TRIP               |
| WARREN      | SUPERFLY TRIP               |
| RICHARD     | SUPERFLY TRIP               |
| MENA        | SUPERFLY TRIP               |
| MATTHEW     | SUPERFLY TRIP               |
| JOHNNY      | SUSPECTS QUILLS             |
| MICHELLE    | SUSPECTS QUILLS             |
| MINNIE      | SUSPECTS QUILLS             |
| RUSSELL     | SUSPECTS QUILLS             |
| GRETA       | SUSPECTS QUILLS             |
| VIVIEN      | SUSPECTS QUILLS             |
| JEFF        | SUSPECTS QUILLS             |
| JAYNE       | SUSPECTS QUILLS             |
| JESSICA     | SWARM GOLD                  |
| BURT        | SWARM GOLD                  |
| ANGELINA    | SWARM GOLD                  |
| WOODY       | SWARM GOLD                  |
| SPENCER     | SWARM GOLD                  |
| MATTHEW     | SWARM GOLD                  |
| KARL        | SWEDEN SHINING              |
| KEVIN       | SWEDEN SHINING              |
| MARY        | SWEDEN SHINING              |
| ALBERT      | SWEDEN SHINING              |
| MARY        | SWEDEN SHINING              |
| MILLA       | SWEET BROTHERHOOD           |
| SPENCER     | SWEET BROTHERHOOD           |
| RIVER       | SWEET BROTHERHOOD           |
| OLYMPIA     | SWEET BROTHERHOOD           |
| JON         | SWEET BROTHERHOOD           |
| MERYL       | SWEET BROTHERHOOD           |
| JOE         | SWEETHEARTS SUSPECTS        |
| HELEN       | SWEETHEARTS SUSPECTS        |
| JULIA       | SWEETHEARTS SUSPECTS        |
| BEN         | SWEETHEARTS SUSPECTS        |
| JAYNE       | SWEETHEARTS SUSPECTS        |
| HELEN       | TADPOLE PARK                |
| ADAM        | TADPOLE PARK                |
| ELLEN       | TADPOLE PARK                |
| GENE        | TADPOLE PARK                |
| GRETA       | TADPOLE PARK                |
| JEFF        | TADPOLE PARK                |
| MATTHEW     | TADPOLE PARK                |
| AUDREY      | TADPOLE PARK                |
| BURT        | TALENTED HOMICIDE           |
| NICK        | TALENTED HOMICIDE           |
| MINNIE      | TALENTED HOMICIDE           |
| JANE        | TALENTED HOMICIDE           |
| JADA        | TALENTED HOMICIDE           |
| TOM         | TARZAN VIDEOTAPE            |
| TOM         | TARZAN VIDEOTAPE            |
| LAURA       | TARZAN VIDEOTAPE            |
| BOB         | TAXI KICK                   |
| KENNETH     | TAXI KICK                   |
| WOODY       | TAXI KICK                   |
| SPENCER     | TAXI KICK                   |
| ALBERT      | TAXI KICK                   |
| MENA        | TAXI KICK                   |
| MILLA       | TEEN APOLLO                 |
| NICK        | TEEN APOLLO                 |
| CARMEN      | TEEN APOLLO                 |
| GREG        | TEEN APOLLO                 |
| RIVER       | TEEN APOLLO                 |
| WOODY       | TELEGRAPH VOYAGE            |
| CARMEN      | TELEGRAPH VOYAGE            |
| GINA        | TELEGRAPH VOYAGE            |
| LUCILLE     | TELEGRAPH VOYAGE            |
| VIVIEN      | TELEGRAPH VOYAGE            |
| MICHAEL     | TELEGRAPH VOYAGE            |
| THORA       | TELEGRAPH VOYAGE            |
| KARL        | TELEMARK HEARTBREAKERS      |
| HELEN       | TELEMARK HEARTBREAKERS      |
| JULIA       | TELEMARK HEARTBREAKERS      |
| SISSY       | TELEMARK HEARTBREAKERS      |
| GROUCHO     | TELEMARK HEARTBREAKERS      |
| SEAN        | TELEMARK HEARTBREAKERS      |
| JAYNE       | TELEMARK HEARTBREAKERS      |
| GEOFFREY    | TELEMARK HEARTBREAKERS      |
| VIVIEN      | TELEMARK HEARTBREAKERS      |
| HARVEY      | TELEMARK HEARTBREAKERS      |
| MICHAEL     | TELEMARK HEARTBREAKERS      |
| MILLA       | TEMPLE ATTRACTION           |
| KENNETH     | TEMPLE ATTRACTION           |
| GROUCHO     | TEMPLE ATTRACTION           |
| JANE        | TEMPLE ATTRACTION           |
| CHRISTOPHER | TEMPLE ATTRACTION           |
| SCARLETT    | TENENBAUMS COMMAND          |
| RICHARD     | TENENBAUMS COMMAND          |
| LAURENCE    | TENENBAUMS COMMAND          |
| MICHAEL     | TENENBAUMS COMMAND          |
| CUBA        | TENENBAUMS COMMAND          |
| DAN         | TEQUILA PAST                |
| NICK        | TEQUILA PAST                |
| CHRIS       | TEQUILA PAST                |
| LIZA        | TERMINATOR CLUB             |
| HUMPHREY    | TERMINATOR CLUB             |
| RIP         | TEXAS WATCH                 |
| SYLVESTER   | TEXAS WATCH                 |
| LIZA        | TEXAS WATCH                 |
| LUCILLE     | TEXAS WATCH                 |
| IAN         | TEXAS WATCH                 |
| JAYNE       | TEXAS WATCH                 |
| CUBA        | THEORY MERMAID              |
| FRED        | THEORY MERMAID              |
| WILL        | THEORY MERMAID              |
| MENA        | THEORY MERMAID              |
| MARY        | THEORY MERMAID              |
| JULIA       | THEORY MERMAID              |
| KIRSTEN     | THIEF PELICAN               |
| JOHNNY      | THIEF PELICAN               |
| JAMES       | THIEF PELICAN               |
| WARREN      | THIEF PELICAN               |
| HARRISON    | THIEF PELICAN               |
| RENEE       | THIEF PELICAN               |
| JAYNE       | THIEF PELICAN               |
| ZERO        | THIN SAGEBRUSH              |
| RALPH       | THIN SAGEBRUSH              |
| JOE         | TIES HUNGER                 |
| JULIA       | TIES HUNGER                 |
| PARKER      | TIES HUNGER                 |
| KIRSTEN     | TIES HUNGER                 |
| JAYNE       | TIES HUNGER                 |
| WILL        | TIES HUNGER                 |
| VIVIEN      | TIGHTS DAWN                 |
| TOM         | TIGHTS DAWN                 |
| MORGAN      | TIGHTS DAWN                 |
| IAN         | TIGHTS DAWN                 |
| WILLIAM     | TIGHTS DAWN                 |
| GARY        | TIMBERLAND SKY              |
| JUDE        | TIMBERLAND SKY              |
| BEN         | TIMBERLAND SKY              |
| CHRISTOPHER | TIMBERLAND SKY              |
| BETTE       | TITANIC BOONDOCK            |
| DAN         | TITANIC BOONDOCK            |
| PENELOPE    | TITANIC BOONDOCK            |
| WARREN      | TITANIC BOONDOCK            |
| JULIANNE    | TITANIC BOONDOCK            |
| EWAN        | TITANIC BOONDOCK            |
| JAYNE       | TITANIC BOONDOCK            |
| GEOFFREY    | TITANIC BOONDOCK            |
| WILL        | TITANIC BOONDOCK            |
| OLYMPIA     | TITANIC BOONDOCK            |
| MATTHEW     | TITANIC BOONDOCK            |
| MARY        | TITANIC BOONDOCK            |
| KIRSTEN     | TITANS JERK                 |
| DAN         | TITANS JERK                 |
| CAMERON     | TITANS JERK                 |
| WOODY       | TITANS JERK                 |
| GREG        | TITANS JERK                 |
| SIDNEY      | TITANS JERK                 |
| KIM         | TITANS JERK                 |
| JODIE       | TOMATOES HELLFIGHTERS       |
| GROUCHO     | TOMATOES HELLFIGHTERS       |
| WARREN      | TOMATOES HELLFIGHTERS       |
| CAMERON     | TOMATOES HELLFIGHTERS       |
| PENELOPE    | TOMATOES HELLFIGHTERS       |
| RICHARD     | TOMATOES HELLFIGHTERS       |
| ANGELA      | TOMATOES HELLFIGHTERS       |
| VIVIEN      | TOMATOES HELLFIGHTERS       |
| KENNETH     | TOMATOES HELLFIGHTERS       |
| MATTHEW     | TOMORROW HUSTLER            |
| REESE       | TOMORROW HUSTLER            |
| GARY        | TOMORROW HUSTLER            |
| MINNIE      | TOMORROW HUSTLER            |
| MATTHEW     | TOMORROW HUSTLER            |
| GEOFFREY    | TOMORROW HUSTLER            |
| ZERO        | TOOTSIE PILOT               |
| NICK        | TOOTSIE PILOT               |
| GENE        | TOOTSIE PILOT               |
| VIVIEN      | TOOTSIE PILOT               |
| CUBA        | TOOTSIE PILOT               |
| UMA         | TORQUE BOUND                |
| NATALIE     | TORQUE BOUND                |
| ADAM        | TORQUE BOUND                |
| GENE        | TORQUE BOUND                |
| KENNETH     | TORQUE BOUND                |
| PENELOPE    | TOURIST PELICAN             |
| BEN         | TOURIST PELICAN             |
| OLYMPIA     | TOURIST PELICAN             |
| CATE        | TOWERS HURRICANE            |
| ADAM        | TOWERS HURRICANE            |
| RUSSELL     | TOWERS HURRICANE            |
| CUBA        | TOWERS HURRICANE            |
| GRACE       | TOWN ARK                    |
| VAL         | TOWN ARK                    |
| REESE       | TOWN ARK                    |
| WARREN      | TOWN ARK                    |
| GRACE       | TRACY CIDER                 |
| REESE       | TRACY CIDER                 |
| SEAN        | TRACY CIDER                 |
| BETTE       | TRADING PINOCCHIO           |
| NICK        | TRADING PINOCCHIO           |
| MILLA       | TRADING PINOCCHIO           |
| JOE         | TRAFFIC HOBBIT              |
| DARYL       | TRAFFIC HOBBIT              |
| MATTHEW     | TRAFFIC HOBBIT              |
| OLYMPIA     | TRAFFIC HOBBIT              |
| RIP         | TRAIN BUNCH                 |
| JULIA       | TRAIN BUNCH                 |
| PENELOPE    | TRAIN BUNCH                 |
| ADAM        | TRAIN BUNCH                 |
| GREG        | TRAINSPOTTING STRANGERS     |
| GINA        | TRAINSPOTTING STRANGERS     |
| RITA        | TRAINSPOTTING STRANGERS     |
| RUSSELL     | TRAINSPOTTING STRANGERS     |
| RIP         | TRAMP OTHERS                |
| SIDNEY      | TRAMP OTHERS                |
| JADA        | TRAMP OTHERS                |
| RIVER       | TRAMP OTHERS                |
| RENEE       | TRAMP OTHERS                |
| BELA        | TRAMP OTHERS                |
| TOM         | TRANSLATION SUMMER          |
| LAURA       | TRANSLATION SUMMER          |
| MATTHEW     | TRANSLATION SUMMER          |
| VIVIEN      | TRAP GUYS                   |
| WOODY       | TRAP GUYS                   |
| KENNETH     | TRAP GUYS                   |
| ALBERT      | TRAP GUYS                   |
| HUMPHREY    | TRAP GUYS                   |
| WILLIAM     | TRAP GUYS                   |
| BELA        | TRAP GUYS                   |
| JENNIFER    | TREASURE COMMAND            |
| MARY        | TREASURE COMMAND            |
| ELLEN       | TREASURE COMMAND            |
| SPENCER     | TREASURE COMMAND            |
| CATE        | TREASURE COMMAND            |
| ALBERT      | TREASURE COMMAND            |
| OPRAH       | TREASURE COMMAND            |
| GRACE       | TREATMENT JEKYLL            |
| SCARLETT    | TREATMENT JEKYLL            |
| SIDNEY      | TREATMENT JEKYLL            |
| DARYL       | TREATMENT JEKYLL            |
| GENE        | TREATMENT JEKYLL            |
| WOODY       | TRIP NEWTON                 |
| PENELOPE    | TRIP NEWTON                 |
| KEVIN       | TRIP NEWTON                 |
| MATTHEW     | TRIP NEWTON                 |
| ELVIS       | TROJAN TOMORROW             |
| JODIE       | TROJAN TOMORROW             |
| ANGELINA    | TROJAN TOMORROW             |
| CHRIS       | TROJAN TOMORROW             |
| MATTHEW     | TROJAN TOMORROW             |
| SUSAN       | TROJAN TOMORROW             |
| CATE        | TROJAN TOMORROW             |
| THORA       | TROJAN TOMORROW             |
| JULIA       | TROOPERS METAL              |
| PENELOPE    | TROOPERS METAL              |
| MORGAN      | TROOPERS METAL              |
| RUSSELL     | TROOPERS METAL              |
| GRETA       | TROOPERS METAL              |
| CHRISTIAN   | TROUBLE DATE                |
| KEVIN       | TROUBLE DATE                |
| JUDY        | TROUBLE DATE                |
| KENNETH     | TROUBLE DATE                |
| JADA        | TROUBLE DATE                |
| RUSSELL     | TROUBLE DATE                |
| RENEE       | TROUBLE DATE                |
| GREGORY     | TROUBLE DATE                |
| BURT        | TRUMAN CRAZY                |
| CARMEN      | TRUMAN CRAZY                |
| MARY        | TRUMAN CRAZY                |
| JESSICA     | TRUMAN CRAZY                |
| SIDNEY      | TRUMAN CRAZY                |
| GENE        | TRUMAN CRAZY                |
| MAE         | TURN STAR                   |
| ELLEN       | TURN STAR                   |
| REESE       | TURN STAR                   |
| DAN         | TUXEDO MILE                 |
| KIRK        | TUXEDO MILE                 |
| MORGAN      | TUXEDO MILE                 |
| NATALIE     | TWISTED PIRATES             |
| JUDE        | TWISTED PIRATES             |
| ADAM        | TWISTED PIRATES             |
| VIVIEN      | TYCOON GATHERING            |
| SPENCER     | TYCOON GATHERING            |
| CAMERON     | TYCOON GATHERING            |
| MINNIE      | TYCOON GATHERING            |
| MICHAEL     | TYCOON GATHERING            |
| BELA        | TYCOON GATHERING            |
| KIRSTEN     | UNBREAKABLE KARATE          |
| GOLDIE      | UNBREAKABLE KARATE          |
| REESE       | UNBREAKABLE KARATE          |
| BURT        | UNBREAKABLE KARATE          |
| WARREN      | UNBREAKABLE KARATE          |
| DARYL       | UNBREAKABLE KARATE          |
| HARVEY      | UNBREAKABLE KARATE          |
| MICHAEL     | UNBREAKABLE KARATE          |
| RAY         | UNCUT SUICIDES              |
| MORGAN      | UNCUT SUICIDES              |
| JANE        | UNCUT SUICIDES              |
| RUSSELL     | UNCUT SUICIDES              |
| HARVEY      | UNCUT SUICIDES              |
| ALAN        | UNCUT SUICIDES              |
| MATTHEW     | UNCUT SUICIDES              |
| TOM         | UNDEFEATED DALMATIONS       |
| FRANCES     | UNDEFEATED DALMATIONS       |
| ALBERT      | UNDEFEATED DALMATIONS       |
| JULIA       | UNFAITHFUL KILL             |
| GREG        | UNFAITHFUL KILL             |
| DARYL       | UNFAITHFUL KILL             |
| LUCILLE     | UNFAITHFUL KILL             |
| WHOOPI      | UNFAITHFUL KILL             |
| KIM         | UNFAITHFUL KILL             |
| LAURENCE    | UNFAITHFUL KILL             |
| RENEE       | UNFAITHFUL KILL             |
| JENNIFER    | UNFORGIVEN ZOOLANDER        |
| CUBA        | UNFORGIVEN ZOOLANDER        |
| JULIA       | UNFORGIVEN ZOOLANDER        |
| NATALIE     | UNFORGIVEN ZOOLANDER        |
| HARVEY      | UNFORGIVEN ZOOLANDER        |
| ED          | UNFORGIVEN ZOOLANDER        |
| MARY        | UNFORGIVEN ZOOLANDER        |
| VAL         | UNITED PILOT                |
| REESE       | UNITED PILOT                |
| RAY         | UNITED PILOT                |
| SEAN        | UNITED PILOT                |
| MENA        | UNITED PILOT                |
| ROCK        | UNITED PILOT                |
| JOE         | UNTOUCHABLES SUNRISE        |
| FRANCES     | UNTOUCHABLES SUNRISE        |
| PENELOPE    | UNTOUCHABLES SUNRISE        |
| RENEE       | UNTOUCHABLES SUNRISE        |
| JULIANNE    | UNTOUCHABLES SUNRISE        |
| ANNE        | UPRISING UPTOWN             |
| GENE        | UPRISING UPTOWN             |
| BEN         | UPRISING UPTOWN             |
| HARVEY      | UPRISING UPTOWN             |
| WILL        | UPRISING UPTOWN             |
| ZERO        | UPTOWN YOUNG                |
| ALEC        | UPTOWN YOUNG                |
| TIM         | UPTOWN YOUNG                |
| HENRY       | UPTOWN YOUNG                |
| MARY        | UPTOWN YOUNG                |
| SUSAN       | UPTOWN YOUNG                |
| ALAN        | UPTOWN YOUNG                |
| CHRISTIAN   | USUAL UNTOUCHABLES          |
| AUDREY      | USUAL UNTOUCHABLES          |
| GREG        | USUAL UNTOUCHABLES          |
| KENNETH     | USUAL UNTOUCHABLES          |
| KIRSTEN     | USUAL UNTOUCHABLES          |
| CHRISTIAN   | VACATION BOONDOCK           |
| FAY         | VACATION BOONDOCK           |
| MEG         | VACATION BOONDOCK           |
| GRETA       | VACATION BOONDOCK           |
| ADAM        | VACATION BOONDOCK           |
| LISA        | VACATION BOONDOCK           |
| BURT        | VALENTINE VANISHING         |
| ED          | VALENTINE VANISHING         |
| TOM         | VALLEY PACKER               |
| CAMERON     | VALLEY PACKER               |
| BEN         | VALLEY PACKER               |
| SUSAN       | VALLEY PACKER               |
| JOHNNY      | VAMPIRE WHALE               |
| MEG         | VAMPIRE WHALE               |
| RICHARD     | VAMPIRE WHALE               |
| ED          | VAMPIRE WHALE               |
| ALAN        | VAMPIRE WHALE               |
| GROUCHO     | VANILLA DAY                 |
| WHOOPI      | VANILLA DAY                 |
| SANDRA      | VANISHED GARDEN             |
| ANGELINA    | VANISHED GARDEN             |
| MATTHEW     | VANISHING ROCKY             |
| DAN         | VANISHING ROCKY             |
| GARY        | VANISHING ROCKY             |
| SUSAN       | VANISHING ROCKY             |
| GENE        | VANISHING ROCKY             |
| NICK        | VARSITY TRIP                |
| MENA        | VARSITY TRIP                |
| BURT        | VARSITY TRIP                |
| ZERO        | VELVET TERMINATOR           |
| JOHNNY      | VELVET TERMINATOR           |
| ANGELA      | VELVET TERMINATOR           |
| SEAN        | VELVET TERMINATOR           |
| CARY        | VELVET TERMINATOR           |
| CUBA        | VELVET TERMINATOR           |
| DARYL       | VELVET TERMINATOR           |
| MINNIE      | VELVET TERMINATOR           |
| MERYL       | VELVET TERMINATOR           |
| PENELOPE    | VERTIGO NORTHWEST           |
| DAN         | VERTIGO NORTHWEST           |
| WARREN      | VERTIGO NORTHWEST           |
| BELA        | VERTIGO NORTHWEST           |
| GARY        | VICTORY ACADEMY             |
| KENNETH     | VICTORY ACADEMY             |
| DEBBIE      | VICTORY ACADEMY             |
| CUBA        | VICTORY ACADEMY             |
| MERYL       | VICTORY ACADEMY             |
| RALPH       | VIDEOTAPE ARSENIC           |
| CHRISTOPHER | VIDEOTAPE ARSENIC           |
| SUSAN       | VIDEOTAPE ARSENIC           |
| IAN         | VIDEOTAPE ARSENIC           |
| RUSSELL     | VIDEOTAPE ARSENIC           |
| JODIE       | VIETNAM SMOOCHY             |
| MATTHEW     | VIETNAM SMOOCHY             |
| DUSTIN      | VILLAIN DESPERATE           |
| CARY        | VILLAIN DESPERATE           |
| DAN         | VIRGIN DAISY                |
| ALEC        | VIRGIN DAISY                |
| NICK        | VIRGIN DAISY                |
| JULIA       | VIRGIN DAISY                |
| CAMERON     | VIRGIN DAISY                |
| SPENCER     | VIRGIN DAISY                |
| CATE        | VIRGIN DAISY                |
| NICK        | VIRGIN DAISY                |
| KARL        | VIRGINIAN PLUTO             |
| SANDRA      | VIRGINIAN PLUTO             |
| CAMERON     | VIRGINIAN PLUTO             |
| JESSICA     | VIRGINIAN PLUTO             |
| GENE        | VIRGINIAN PLUTO             |
| PENELOPE    | VIRGINIAN PLUTO             |
| ALBERT      | VIRGINIAN PLUTO             |
| THORA       | VIRGINIAN PLUTO             |
| DUSTIN      | VIRTUAL SPOILERS            |
| GARY        | VIRTUAL SPOILERS            |
| JON         | VIRTUAL SPOILERS            |
| MENA        | VISION TORQUE               |
| MEG         | VISION TORQUE               |
| RUSSELL     | VISION TORQUE               |
| CHRISTOPHER | VISION TORQUE               |
| AL          | VISION TORQUE               |
| VIVIEN      | VOICE PEACH                 |
| HELEN       | VOICE PEACH                 |
| AL          | VOICE PEACH                 |
| CUBA        | VOLCANO TEXAS               |
| ALBERT      | VOLCANO TEXAS               |
| CATE        | VOLCANO TEXAS               |
| RUSSELL     | VOLCANO TEXAS               |
| RUSSELL     | VOLCANO TEXAS               |
| AUDREY      | VOLUME HOUSE                |
| GARY        | VOLUME HOUSE                |
| KENNETH     | VOLUME HOUSE                |
| CHRIS       | VOLUME HOUSE                |
| REESE       | VOLUME HOUSE                |
| CARMEN      | VOYAGE LEGALLY              |
| JAYNE       | VOYAGE LEGALLY              |
| ANGELA      | VOYAGE LEGALLY              |
| MARY        | VOYAGE LEGALLY              |
| MEG         | VOYAGE LEGALLY              |
| NICK        | WAGON JAWS                  |
| HENRY       | WAGON JAWS                  |
| SPENCER     | WAGON JAWS                  |
| HARRISON    | WAGON JAWS                  |
| RICHARD     | WAGON JAWS                  |
| MARY        | WAGON JAWS                  |
| WOODY       | WAIT CIDER                  |
| MICHELLE    | WAIT CIDER                  |
| KEVIN       | WAIT CIDER                  |
| ANGELA      | WAIT CIDER                  |
| KIM         | WAIT CIDER                  |
| JAYNE       | WAIT CIDER                  |
| OLYMPIA     | WAIT CIDER                  |
| BURT        | WAIT CIDER                  |
| JULIA       | WAIT CIDER                  |
| WOODY       | WAKE JAWS                   |
| SIDNEY      | WAKE JAWS                   |
| MERYL       | WAKE JAWS                   |
| CHRIS       | WAKE JAWS                   |
| KENNETH     | WAKE JAWS                   |
| CHRIS       | WALLS ARTIST                |
| SYLVESTER   | WALLS ARTIST                |
| HARRISON    | WALLS ARTIST                |
| ALBERT      | WALLS ARTIST                |
| JEFF        | WALLS ARTIST                |
| BURT        | WANDA CHAMBER               |
| ADAM        | WANDA CHAMBER               |
| SEAN        | WANDA CHAMBER               |
| MILLA       | WANDA CHAMBER               |
| MATTHEW     | WANDA CHAMBER               |
| DAN         | WANDA CHAMBER               |
| GENE        | WANDA CHAMBER               |
| GRACE       | WAR NOTTING                 |
| HELEN       | WAR NOTTING                 |
| NATALIE     | WAR NOTTING                 |
| MARY        | WAR NOTTING                 |
| MINNIE      | WAR NOTTING                 |
| CUBA        | WAR NOTTING                 |
| SALMA       | WAR NOTTING                 |
| FAY         | WAR NOTTING                 |
| HUMPHREY    | WAR NOTTING                 |
| NICK        | WARDROBE PHANTOM            |
| KIRK        | WARDROBE PHANTOM            |
| ANGELINA    | WARDROBE PHANTOM            |
| WALTER      | WARDROBE PHANTOM            |
| WARREN      | WARDROBE PHANTOM            |
| RIVER       | WARDROBE PHANTOM            |
| GREGORY     | WARDROBE PHANTOM            |
| THORA       | WARDROBE PHANTOM            |
| GRACE       | WARLOCK WEREWOLF            |
| HELEN       | WARLOCK WEREWOLF            |
| WILL        | WARLOCK WEREWOLF            |
| GROUCHO     | WARLOCK WEREWOLF            |
| HUMPHREY    | WARLOCK WEREWOLF            |
| AUDREY      | WARLOCK WEREWOLF            |
| MARY        | WARS PLUTO                  |
| MINNIE      | WARS PLUTO                  |
| ED          | WARS PLUTO                  |
| BURT        | WARS PLUTO                  |
| MENA        | WASH HEAVENLY               |
| SPENCER     | WASH HEAVENLY               |
| SUSAN       | WASH HEAVENLY               |
| MORGAN      | WASH HEAVENLY               |
| SALMA       | WASH HEAVENLY               |
| LUCILLE     | WASTELAND DIVINE            |
| CAMERON     | WASTELAND DIVINE            |
| DARYL       | WASTELAND DIVINE            |
| JAYNE       | WASTELAND DIVINE            |
| AL          | WASTELAND DIVINE            |
| JAYNE       | WASTELAND DIVINE            |
| VAL         | WATCH TRACY                 |
| FAY         | WATCH TRACY                 |
| CARY        | WATCH TRACY                 |
| GROUCHO     | WATCH TRACY                 |
| JEFF        | WATCH TRACY                 |
| JOE         | WATERFRONT DELIVERANCE      |
| CHRISTIAN   | WATERFRONT DELIVERANCE      |
| ELVIS       | WATERFRONT DELIVERANCE      |
| MICHELLE    | WATERFRONT DELIVERANCE      |
| SEAN        | WATERFRONT DELIVERANCE      |
| BEN         | WATERFRONT DELIVERANCE      |
| MILLA       | WATERSHIP FRONTIER          |
| DAN         | WATERSHIP FRONTIER          |
| ANGELA      | WATERSHIP FRONTIER          |
| ALBERT      | WATERSHIP FRONTIER          |
| CATE        | WATERSHIP FRONTIER          |
| MICHAEL     | WATERSHIP FRONTIER          |
| ED          | WEDDING APOLLO              |
| CHRISTIAN   | WEDDING APOLLO              |
| UMA         | WEDDING APOLLO              |
| VAL         | WEDDING APOLLO              |
| WARREN      | WEDDING APOLLO              |
| HARRISON    | WEDDING APOLLO              |
| LIZA        | WEDDING APOLLO              |
| ALBERT      | WEDDING APOLLO              |
| IAN         | WEDDING APOLLO              |
| HUMPHREY    | WEDDING APOLLO              |
| ED          | WEEKEND PERSONAL            |
| FRED        | WEEKEND PERSONAL            |
| JULIA       | WEEKEND PERSONAL            |
| JIM         | WEEKEND PERSONAL            |
| SPENCER     | WEEKEND PERSONAL            |
| SYLVESTER   | WEEKEND PERSONAL            |
| GRETA       | WEEKEND PERSONAL            |
| VIVIEN      | WEEKEND PERSONAL            |
| HUMPHREY    | WEEKEND PERSONAL            |
| REESE       | WEEKEND PERSONAL            |
| CUBA        | WEREWOLF LOLA               |
| GROUCHO     | WEREWOLF LOLA               |
| KENNETH     | WEREWOLF LOLA               |
| GENE        | WEREWOLF LOLA               |
| BEN         | WEREWOLF LOLA               |
| VIVIEN      | WEREWOLF LOLA               |
| OPRAH       | WEREWOLF LOLA               |
| ZERO        | WEST LION                   |
| CAMERON     | WEST LION                   |
| SEAN        | WEST LION                   |
| CARY        | WEST LION                   |
| MORGAN      | WEST LION                   |
| CUBA        | WEST LION                   |
| ALBERT      | WEST LION                   |
| HUMPHREY    | WEST LION                   |
| GREGORY     | WEST LION                   |
| PENELOPE    | WESTWARD SEABISCUIT         |
| VIVIEN      | WESTWARD SEABISCUIT         |
| PENELOPE    | WESTWARD SEABISCUIT         |
| CHARLIZE    | WESTWARD SEABISCUIT         |
| KEVIN       | WESTWARD SEABISCUIT         |
| LUCILLE     | WESTWARD SEABISCUIT         |
| ED          | WHALE BIKINI                |
| AUDREY      | WHALE BIKINI                |
| HENRY       | WHALE BIKINI                |
| RIP         | WHALE BIKINI                |
| GREGORY     | WHALE BIKINI                |
| MILLA       | WHISPERER GIANT             |
| JESSICA     | WHISPERER GIANT             |
| BELA        | WHISPERER GIANT             |
| WOODY       | WIFE TURN                   |
| JULIA       | WIFE TURN                   |
| GINA        | WIFE TURN                   |
| CAMERON     | WIFE TURN                   |
| GRETA       | WIFE TURN                   |
| MICHAEL     | WIFE TURN                   |
| JOE         | WILD APOLLO                 |
| GARY        | WILD APOLLO                 |
| LISA        | WILD APOLLO                 |
| REESE       | WILD APOLLO                 |
| REESE       | WILLOW TRACY                |
| JAMES       | WILLOW TRACY                |
| CHARLIZE    | WIND PHANTOM                |
| ED          | WIND PHANTOM                |
| RENEE       | WIND PHANTOM                |
| LUCILLE     | WINDOW SIDE                 |
| ANNE        | WINDOW SIDE                 |
| GINA        | WINDOW SIDE                 |
| WILLIAM     | WINDOW SIDE                 |
| SISSY       | WISDOM WORKER               |
| REESE       | WISDOM WORKER               |
| WOODY       | WISDOM WORKER               |
| JIM         | WISDOM WORKER               |
| SUSAN       | WISDOM WORKER               |
| LAURA       | WISDOM WORKER               |
| WILLIAM     | WISDOM WORKER               |
| RALPH       | WITCHES PANIC               |
| SPENCER     | WITCHES PANIC               |
| WALTER      | WITCHES PANIC               |
| REESE       | WITCHES PANIC               |
| PENELOPE    | WIZARD COLDBLOODED          |
| CHRISTIAN   | WIZARD COLDBLOODED          |
| TIM         | WIZARD COLDBLOODED          |
| PARKER      | WIZARD COLDBLOODED          |
| ANNE        | WIZARD COLDBLOODED          |
| MENA        | WIZARD COLDBLOODED          |
| RAY         | WIZARD COLDBLOODED          |
| SUSAN       | WIZARD COLDBLOODED          |
| WALTER      | WIZARD COLDBLOODED          |
| SANDRA      | WOLVES DESIRE               |
| JAYNE       | WOLVES DESIRE               |
| CAMERON     | WOLVES DESIRE               |
| JESSICA     | WOLVES DESIRE               |
| MORGAN      | WOLVES DESIRE               |
| GRETA       | WOLVES DESIRE               |
| NICK        | WOMEN DORADO                |
| CHRISTOPHER | WOMEN DORADO                |
| ELLEN       | WOMEN DORADO                |
| JIM         | WOMEN DORADO                |
| MICHAEL     | WOMEN DORADO                |
| CHRISTIAN   | WON DARES                   |
| KIRSTEN     | WON DARES                   |
| LISA        | WON DARES                   |
| RUSSELL     | WON DARES                   |
| JULIA       | WON DARES                   |
| DUSTIN      | WONDERFUL DROP              |
| SUSAN       | WONDERFUL DROP              |
| PENELOPE    | WONDERFUL DROP              |
| HUMPHREY    | WONDERFUL DROP              |
| CUBA        | WONDERLAND CHRISTMAS        |
| WOODY       | WONDERLAND CHRISTMAS        |
| CHRIS       | WONDERLAND CHRISTMAS        |
| HARRISON    | WONDERLAND CHRISTMAS        |
| HUMPHREY    | WONDERLAND CHRISTMAS        |
| JULIA       | WONKA SEA                   |
| HENRY       | WONKA SEA                   |
| GENE        | WORDS HUNTER                |
| SUSAN       | WORDS HUNTER                |
| SCARLETT    | WORDS HUNTER                |
| ADAM        | WORDS HUNTER                |
| FAY         | WORDS HUNTER                |
| IAN         | WORDS HUNTER                |
| ZERO        | WORKER TARZAN               |
| PENELOPE    | WORKER TARZAN               |
| JAYNE       | WORKER TARZAN               |
| SUSAN       | WORKER TARZAN               |
| RUSSELL     | WORKER TARZAN               |
| JULIANNE    | WORKER TARZAN               |
| MINNIE      | WORKER TARZAN               |
| MERYL       | WORKER TARZAN               |
| ROCK        | WORKER TARZAN               |
| VAL         | WORKING MICROCOSMOS         |
| KENNETH     | WORKING MICROCOSMOS         |
| LUCILLE     | WORKING MICROCOSMOS         |
| GEOFFREY    | WORKING MICROCOSMOS         |
| ROCK        | WORKING MICROCOSMOS         |
| GARY        | WORLD LEATHERNECKS          |
| PENELOPE    | WORLD LEATHERNECKS          |
| CHRISTIAN   | WORLD LEATHERNECKS          |
| JAYNE       | WORLD LEATHERNECKS          |
| CHRIS       | WORLD LEATHERNECKS          |
| SIDNEY      | WORLD LEATHERNECKS          |
| VIVIEN      | WORLD LEATHERNECKS          |
| DEBBIE      | WORLD LEATHERNECKS          |
| PARKER      | WORST BANGER                |
| KIRSTEN     | WORST BANGER                |
| SPENCER     | WORST BANGER                |
| MATTHEW     | WORST BANGER                |
| SPENCER     | WRATH MILE                  |
| CATE        | WRATH MILE                  |
| RUSSELL     | WRATH MILE                  |
| KENNETH     | WRATH MILE                  |
| MILLA       | WRONG BEHAVIOR              |
| GARY        | WRONG BEHAVIOR              |
| CARY        | WRONG BEHAVIOR              |
| SIDNEY      | WRONG BEHAVIOR              |
| MORGAN      | WRONG BEHAVIOR              |
| ED          | WRONG BEHAVIOR              |
| MENA        | WRONG BEHAVIOR              |
| GREGORY     | WRONG BEHAVIOR              |
| THORA       | WRONG BEHAVIOR              |
| BETTE       | WYOMING STORM               |
| WOODY       | WYOMING STORM               |
| SIDNEY      | WYOMING STORM               |
| HARRISON    | WYOMING STORM               |
| PENELOPE    | WYOMING STORM               |
| JULIA       | WYOMING STORM               |
| REESE       | YENTL IDAHO                 |
| ED          | YOUNG LANGUAGE              |
| JULIA       | YOUNG LANGUAGE              |
| JAMES       | YOUNG LANGUAGE              |
| CHRISTOPHER | YOUNG LANGUAGE              |
| MENA        | YOUNG LANGUAGE              |
| SANDRA      | YOUTH KICK                  |
| VAL         | YOUTH KICK                  |
| SCARLETT    | YOUTH KICK                  |
| IAN         | YOUTH KICK                  |
| MARY        | YOUTH KICK                  |
| UMA         | ZHIVAGO CORE                |
| NICK        | ZHIVAGO CORE                |
| GARY        | ZHIVAGO CORE                |
| SALMA       | ZHIVAGO CORE                |
| KENNETH     | ZHIVAGO CORE                |
| WILLIAM     | ZHIVAGO CORE                |
| CARMEN      | ZOOLANDER FICTION           |
| MARY        | ZOOLANDER FICTION           |
| PENELOPE    | ZOOLANDER FICTION           |
| WHOOPI      | ZOOLANDER FICTION           |
| JADA        | ZOOLANDER FICTION           |
| IAN         | ZORRO ARK                   |
| NICK        | ZORRO ARK                   |
| LISA        | ZORRO ARK                   |
+-------------+-----------------------------+

5462 rows in set (0,01 sec)

```

Listar todos los clientes y los almacenes donde están
registrados.

```sql
SELECT id_cliente, nombre, id_almacen
FROM cliente;

+------------+-------------+------------+
| id_cliente | nombre      | id_almacen |
+------------+-------------+------------+
|          1 | MARY        |          1 |
|          2 | PATRICIA    |          1 |
|          3 | LINDA       |          1 |
|          4 | BARBARA     |          2 |
|          5 | ELIZABETH   |          1 |
|          6 | JENNIFER    |          2 |
|          7 | MARIA       |          1 |
|          8 | SUSAN       |          2 |
|          9 | MARGARET    |          2 |
|         10 | DOROTHY     |          1 |
|         11 | LISA        |          2 |
|         12 | NANCY       |          1 |
|         13 | KAREN       |          2 |
|         14 | BETTY       |          2 |
|         15 | HELEN       |          1 |
|         16 | SANDRA      |          2 |
|         17 | DONNA       |          1 |
|         18 | CAROL       |          2 |
|         19 | RUTH        |          1 |
|         20 | SHARON      |          2 |
|         21 | MICHELLE    |          1 |
|         22 | LAURA       |          1 |
|         23 | SARAH       |          2 |
|         24 | KIMBERLY    |          2 |
|         25 | DEBORAH     |          1 |
|         26 | JESSICA     |          2 |
|         27 | SHIRLEY     |          2 |
|         28 | CYNTHIA     |          1 |
|         29 | ANGELA      |          2 |
|         30 | MELISSA     |          1 |
|         31 | BRENDA      |          2 |
|         32 | AMY         |          1 |
|         33 | ANNA        |          2 |
|         34 | REBECCA     |          2 |
|         35 | VIRGINIA    |          2 |
|         36 | KATHLEEN    |          2 |
|         37 | PAMELA      |          1 |
|         38 | MARTHA      |          1 |
|         39 | DEBRA       |          1 |
|         40 | AMANDA      |          2 |
|         41 | STEPHANIE   |          1 |
|         42 | CAROLYN     |          2 |
|         43 | CHRISTINE   |          2 |
|         44 | MARIE       |          1 |
|         45 | JANET       |          1 |
|         46 | CATHERINE   |          2 |
|         47 | FRANCES     |          1 |
|         48 | ANN         |          1 |
|         49 | JOYCE       |          2 |
|         50 | DIANE       |          1 |
|         51 | ALICE       |          1 |
|         52 | JULIE       |          1 |
|         53 | HEATHER     |          1 |
|         54 | TERESA      |          1 |
|         55 | DORIS       |          2 |
|         56 | GLORIA      |          1 |
|         57 | EVELYN      |          2 |
|         58 | JEAN        |          1 |
|         59 | CHERYL      |          1 |
|         60 | MILDRED     |          1 |
|         61 | KATHERINE   |          2 |
|         62 | JOAN        |          1 |
|         63 | ASHLEY      |          1 |
|         64 | JUDITH      |          2 |
|         65 | ROSE        |          2 |
|         66 | JANICE      |          2 |
|         67 | KELLY       |          1 |
|         68 | NICOLE      |          1 |
|         69 | JUDY        |          2 |
|         70 | CHRISTINA   |          2 |
|         71 | KATHY       |          1 |
|         72 | THERESA     |          2 |
|         73 | BEVERLY     |          2 |
|         74 | DENISE      |          1 |
|         75 | TAMMY       |          2 |
|         76 | IRENE       |          2 |
|         77 | JANE        |          2 |
|         78 | LORI        |          1 |
|         79 | RACHEL      |          1 |
|         80 | MARILYN     |          1 |
|         81 | ANDREA      |          1 |
|         82 | KATHRYN     |          1 |
|         83 | LOUISE      |          1 |
|         84 | SARA        |          2 |
|         85 | ANNE        |          2 |
|         86 | JACQUELINE  |          2 |
|         87 | WANDA       |          1 |
|         88 | BONNIE      |          2 |
|         89 | JULIA       |          1 |
|         90 | RUBY        |          2 |
|         91 | LOIS        |          2 |
|         92 | TINA        |          2 |
|         93 | PHYLLIS     |          1 |
|         94 | NORMA       |          1 |
|         95 | PAULA       |          2 |
|         96 | DIANA       |          1 |
|         97 | ANNIE       |          2 |
|         98 | LILLIAN     |          1 |
|         99 | EMILY       |          2 |
|        100 | ROBIN       |          1 |
|        101 | PEGGY       |          1 |
|        102 | CRYSTAL     |          1 |
|        103 | GLADYS      |          1 |
|        104 | RITA        |          1 |
|        105 | DAWN        |          1 |
|        106 | CONNIE      |          1 |
|        107 | FLORENCE    |          1 |
|        108 | TRACY       |          1 |
|        109 | EDNA        |          2 |
|        110 | TIFFANY     |          2 |
|        111 | CARMEN      |          1 |
|        112 | ROSA        |          2 |
|        113 | CINDY       |          2 |
|        114 | GRACE       |          2 |
|        115 | WENDY       |          1 |
|        116 | VICTORIA    |          1 |
|        117 | EDITH       |          1 |
|        118 | KIM         |          1 |
|        119 | SHERRY      |          1 |
|        120 | SYLVIA      |          2 |
|        121 | JOSEPHINE   |          1 |
|        122 | THELMA      |          1 |
|        123 | SHANNON     |          2 |
|        124 | SHEILA      |          1 |
|        125 | ETHEL       |          1 |
|        126 | ELLEN       |          1 |
|        127 | ELAINE      |          2 |
|        128 | MARJORIE    |          1 |
|        129 | CARRIE      |          1 |
|        130 | CHARLOTTE   |          1 |
|        131 | MONICA      |          2 |
|        132 | ESTHER      |          2 |
|        133 | PAULINE     |          1 |
|        134 | EMMA        |          1 |
|        135 | JUANITA     |          2 |
|        136 | ANITA       |          2 |
|        137 | RHONDA      |          2 |
|        138 | HAZEL       |          1 |
|        139 | AMBER       |          1 |
|        140 | EVA         |          1 |
|        141 | DEBBIE      |          1 |
|        142 | APRIL       |          1 |
|        143 | LESLIE      |          1 |
|        144 | CLARA       |          1 |
|        145 | LUCILLE     |          1 |
|        146 | JAMIE       |          1 |
|        147 | JOANNE      |          2 |
|        148 | ELEANOR     |          1 |
|        149 | VALERIE     |          1 |
|        150 | DANIELLE    |          2 |
|        151 | MEGAN       |          2 |
|        152 | ALICIA      |          1 |
|        153 | SUZANNE     |          2 |
|        154 | MICHELE     |          2 |
|        155 | GAIL        |          1 |
|        156 | BERTHA      |          1 |
|        157 | DARLENE     |          2 |
|        158 | VERONICA    |          1 |
|        159 | JILL        |          1 |
|        160 | ERIN        |          2 |
|        161 | GERALDINE   |          1 |
|        162 | LAUREN      |          2 |
|        163 | CATHY       |          1 |
|        164 | JOANN       |          2 |
|        165 | LORRAINE    |          2 |
|        166 | LYNN        |          1 |
|        167 | SALLY       |          2 |
|        168 | REGINA      |          1 |
|        169 | ERICA       |          2 |
|        170 | BEATRICE    |          1 |
|        171 | DOLORES     |          2 |
|        172 | BERNICE     |          1 |
|        173 | AUDREY      |          1 |
|        174 | YVONNE      |          2 |
|        175 | ANNETTE     |          1 |
|        176 | JUNE        |          1 |
|        177 | SAMANTHA    |          2 |
|        178 | MARION      |          2 |
|        179 | DANA        |          1 |
|        180 | STACY       |          2 |
|        181 | ANA         |          2 |
|        182 | RENEE       |          1 |
|        183 | IDA         |          2 |
|        184 | VIVIAN      |          1 |
|        185 | ROBERTA     |          1 |
|        186 | HOLLY       |          2 |
|        187 | BRITTANY    |          2 |
|        188 | MELANIE     |          1 |
|        189 | LORETTA     |          1 |
|        190 | YOLANDA     |          2 |
|        191 | JEANETTE    |          1 |
|        192 | LAURIE      |          1 |
|        193 | KATIE       |          2 |
|        194 | KRISTEN     |          2 |
|        195 | VANESSA     |          1 |
|        196 | ALMA        |          1 |
|        197 | SUE         |          2 |
|        198 | ELSIE       |          2 |
|        199 | BETH        |          2 |
|        200 | JEANNE      |          2 |
|        201 | VICKI       |          1 |
|        202 | CARLA       |          2 |
|        203 | TARA        |          1 |
|        204 | ROSEMARY    |          1 |
|        205 | EILEEN      |          2 |
|        206 | TERRI       |          1 |
|        207 | GERTRUDE    |          1 |
|        208 | LUCY        |          1 |
|        209 | TONYA       |          2 |
|        210 | ELLA        |          2 |
|        211 | STACEY      |          1 |
|        212 | WILMA       |          2 |
|        213 | GINA        |          1 |
|        214 | KRISTIN     |          1 |
|        215 | JESSIE      |          2 |
|        216 | NATALIE     |          1 |
|        217 | AGNES       |          2 |
|        218 | VERA        |          1 |
|        219 | WILLIE      |          2 |
|        220 | CHARLENE    |          2 |
|        221 | BESSIE      |          1 |
|        222 | DELORES     |          2 |
|        223 | MELINDA     |          1 |
|        224 | PEARL       |          2 |
|        225 | ARLENE      |          1 |
|        226 | MAUREEN     |          2 |
|        227 | COLLEEN     |          1 |
|        228 | ALLISON     |          2 |
|        229 | TAMARA      |          1 |
|        230 | JOY         |          2 |
|        231 | GEORGIA     |          1 |
|        232 | CONSTANCE   |          2 |
|        233 | LILLIE      |          2 |
|        234 | CLAUDIA     |          1 |
|        235 | JACKIE      |          1 |
|        236 | MARCIA      |          1 |
|        237 | TANYA       |          1 |
|        238 | NELLIE      |          1 |
|        239 | MINNIE      |          2 |
|        240 | MARLENE     |          1 |
|        241 | HEIDI       |          2 |
|        242 | GLENDA      |          1 |
|        243 | LYDIA       |          1 |
|        244 | VIOLA       |          2 |
|        245 | COURTNEY    |          1 |
|        246 | MARIAN      |          1 |
|        247 | STELLA      |          1 |
|        248 | CAROLINE    |          1 |
|        249 | DORA        |          2 |
|        250 | JO          |          2 |
|        251 | VICKIE      |          2 |
|        252 | MATTIE      |          2 |
|        253 | TERRY       |          1 |
|        254 | MAXINE      |          2 |
|        255 | IRMA        |          2 |
|        256 | MABEL       |          2 |
|        257 | MARSHA      |          2 |
|        258 | MYRTLE      |          1 |
|        259 | LENA        |          2 |
|        260 | CHRISTY     |          1 |
|        261 | DEANNA      |          1 |
|        262 | PATSY       |          2 |
|        263 | HILDA       |          1 |
|        264 | GWENDOLYN   |          1 |
|        265 | JENNIE      |          2 |
|        266 | NORA        |          2 |
|        267 | MARGIE      |          1 |
|        268 | NINA        |          1 |
|        269 | CASSANDRA   |          1 |
|        270 | LEAH        |          1 |
|        271 | PENNY       |          1 |
|        272 | KAY         |          1 |
|        273 | PRISCILLA   |          2 |
|        274 | NAOMI       |          1 |
|        275 | CAROLE      |          2 |
|        276 | BRANDY      |          1 |
|        277 | OLGA        |          2 |
|        278 | BILLIE      |          2 |
|        279 | DIANNE      |          2 |
|        280 | TRACEY      |          2 |
|        281 | LEONA       |          2 |
|        282 | JENNY       |          2 |
|        283 | FELICIA     |          1 |
|        284 | SONIA       |          1 |
|        285 | MIRIAM      |          1 |
|        286 | VELMA       |          1 |
|        287 | BECKY       |          2 |
|        288 | BOBBIE      |          1 |
|        289 | VIOLET      |          1 |
|        290 | KRISTINA    |          1 |
|        291 | TONI        |          1 |
|        292 | MISTY       |          2 |
|        293 | MAE         |          2 |
|        294 | SHELLY      |          2 |
|        295 | DAISY       |          1 |
|        296 | RAMONA      |          2 |
|        297 | SHERRI      |          1 |
|        298 | ERIKA       |          1 |
|        299 | JAMES       |          2 |
|        300 | JOHN        |          1 |
|        301 | ROBERT      |          2 |
|        302 | MICHAEL     |          1 |
|        303 | WILLIAM     |          2 |
|        304 | DAVID       |          2 |
|        305 | RICHARD     |          1 |
|        306 | CHARLES     |          1 |
|        307 | JOSEPH      |          2 |
|        308 | THOMAS      |          1 |
|        309 | CHRISTOPHER |          1 |
|        310 | DANIEL      |          2 |
|        311 | PAUL        |          2 |
|        312 | MARK        |          2 |
|        313 | DONALD      |          2 |
|        314 | GEORGE      |          1 |
|        315 | KENNETH     |          2 |
|        316 | STEVEN      |          1 |
|        317 | EDWARD      |          2 |
|        318 | BRIAN       |          1 |
|        319 | RONALD      |          2 |
|        320 | ANTHONY     |          2 |
|        321 | KEVIN       |          1 |
|        322 | JASON       |          1 |
|        323 | MATTHEW     |          2 |
|        324 | GARY        |          2 |
|        325 | TIMOTHY     |          1 |
|        326 | JOSE        |          1 |
|        327 | LARRY       |          2 |
|        328 | JEFFREY     |          2 |
|        329 | FRANK       |          2 |
|        330 | SCOTT       |          1 |
|        331 | ERIC        |          1 |
|        332 | STEPHEN     |          1 |
|        333 | ANDREW      |          2 |
|        334 | RAYMOND     |          2 |
|        335 | GREGORY     |          1 |
|        336 | JOSHUA      |          1 |
|        337 | JERRY       |          1 |
|        338 | DENNIS      |          1 |
|        339 | WALTER      |          2 |
|        340 | PATRICK     |          1 |
|        341 | PETER       |          1 |
|        342 | HAROLD      |          1 |
|        343 | DOUGLAS     |          1 |
|        344 | HENRY       |          1 |
|        345 | CARL        |          1 |
|        346 | ARTHUR      |          1 |
|        347 | RYAN        |          2 |
|        348 | ROGER       |          2 |
|        349 | JOE         |          2 |
|        350 | JUAN        |          1 |
|        351 | JACK        |          1 |
|        352 | ALBERT      |          1 |
|        353 | JONATHAN    |          1 |
|        354 | JUSTIN      |          2 |
|        355 | TERRY       |          2 |
|        356 | GERALD      |          2 |
|        357 | KEITH       |          1 |
|        358 | SAMUEL      |          2 |
|        359 | WILLIE      |          2 |
|        360 | RALPH       |          2 |
|        361 | LAWRENCE    |          2 |
|        362 | NICHOLAS    |          1 |
|        363 | ROY         |          2 |
|        364 | BENJAMIN    |          1 |
|        365 | BRUCE       |          2 |
|        366 | BRANDON     |          1 |
|        367 | ADAM        |          1 |
|        368 | HARRY       |          1 |
|        369 | FRED        |          2 |
|        370 | WAYNE       |          2 |
|        371 | BILLY       |          1 |
|        372 | STEVE       |          2 |
|        373 | LOUIS       |          1 |
|        374 | JEREMY      |          2 |
|        375 | AARON       |          2 |
|        376 | RANDY       |          1 |
|        377 | HOWARD      |          1 |
|        378 | EUGENE      |          1 |
|        379 | CARLOS      |          1 |
|        380 | RUSSELL     |          1 |
|        381 | BOBBY       |          2 |
|        382 | VICTOR      |          2 |
|        383 | MARTIN      |          1 |
|        384 | ERNEST      |          2 |
|        385 | PHILLIP     |          1 |
|        386 | TODD        |          1 |
|        387 | JESSE       |          2 |
|        388 | CRAIG       |          2 |
|        389 | ALAN        |          1 |
|        390 | SHAWN       |          1 |
|        391 | CLARENCE    |          1 |
|        392 | SEAN        |          2 |
|        393 | PHILIP      |          1 |
|        394 | CHRIS       |          2 |
|        395 | JOHNNY      |          2 |
|        396 | EARL        |          1 |
|        397 | JIMMY       |          1 |
|        398 | ANTONIO     |          1 |
|        399 | DANNY       |          1 |
|        400 | BRYAN       |          2 |
|        401 | TONY        |          2 |
|        402 | LUIS        |          1 |
|        403 | MIKE        |          1 |
|        404 | STANLEY     |          2 |
|        405 | LEONARD     |          1 |
|        406 | NATHAN      |          1 |
|        407 | DALE        |          1 |
|        408 | MANUEL      |          1 |
|        409 | RODNEY      |          2 |
|        410 | CURTIS      |          2 |
|        411 | NORMAN      |          1 |
|        412 | ALLEN       |          2 |
|        413 | MARVIN      |          2 |
|        414 | VINCENT     |          1 |
|        415 | GLENN       |          1 |
|        416 | JEFFERY     |          2 |
|        417 | TRAVIS      |          1 |
|        418 | JEFF        |          2 |
|        419 | CHAD        |          1 |
|        420 | JACOB       |          1 |
|        421 | LEE         |          1 |
|        422 | MELVIN      |          1 |
|        423 | ALFRED      |          2 |
|        424 | KYLE        |          2 |
|        425 | FRANCIS     |          2 |
|        426 | BRADLEY     |          1 |
|        427 | JESUS       |          2 |
|        428 | HERBERT     |          2 |
|        429 | FREDERICK   |          2 |
|        430 | RAY         |          1 |
|        431 | JOEL        |          2 |
|        432 | EDWIN       |          1 |
|        433 | DON         |          1 |
|        434 | EDDIE       |          1 |
|        435 | RICKY       |          2 |
|        436 | TROY        |          1 |
|        437 | RANDALL     |          2 |
|        438 | BARRY       |          1 |
|        439 | ALEXANDER   |          2 |
|        440 | BERNARD     |          1 |
|        441 | MARIO       |          1 |
|        442 | LEROY       |          1 |
|        443 | FRANCISCO   |          2 |
|        444 | MARCUS      |          2 |
|        445 | MICHEAL     |          1 |
|        446 | THEODORE    |          2 |
|        447 | CLIFFORD    |          1 |
|        448 | MIGUEL      |          1 |
|        449 | OSCAR       |          2 |
|        450 | JAY         |          1 |
|        451 | JIM         |          1 |
|        452 | TOM         |          1 |
|        453 | CALVIN      |          1 |
|        454 | ALEX        |          2 |
|        455 | JON         |          2 |
|        456 | RONNIE      |          2 |
|        457 | BILL        |          2 |
|        458 | LLOYD       |          1 |
|        459 | TOMMY       |          1 |
|        460 | LEON        |          1 |
|        461 | DEREK       |          1 |
|        462 | WARREN      |          2 |
|        463 | DARRELL     |          2 |
|        464 | JEROME      |          1 |
|        465 | FLOYD       |          1 |
|        466 | LEO         |          1 |
|        467 | ALVIN       |          2 |
|        468 | TIM         |          1 |
|        469 | WESLEY      |          2 |
|        470 | GORDON      |          1 |
|        471 | DEAN        |          1 |
|        472 | GREG        |          1 |
|        473 | JORGE       |          2 |
|        474 | DUSTIN      |          2 |
|        475 | PEDRO       |          2 |
|        476 | DERRICK     |          1 |
|        477 | DAN         |          1 |
|        478 | LEWIS       |          1 |
|        479 | ZACHARY     |          1 |
|        480 | COREY       |          1 |
|        481 | HERMAN      |          1 |
|        482 | MAURICE     |          1 |
|        483 | VERNON      |          2 |
|        484 | ROBERTO     |          1 |
|        485 | CLYDE       |          1 |
|        486 | GLEN        |          1 |
|        487 | HECTOR      |          2 |
|        488 | SHANE       |          2 |
|        489 | RICARDO     |          1 |
|        490 | SAM         |          1 |
|        491 | RICK        |          2 |
|        492 | LESTER      |          2 |
|        493 | BRENT       |          1 |
|        494 | RAMON       |          2 |
|        495 | CHARLIE     |          2 |
|        496 | TYLER       |          2 |
|        497 | GILBERT     |          2 |
|        498 | GENE        |          1 |
|        499 | MARC        |          2 |
|        500 | REGINALD    |          1 |
|        501 | RUBEN       |          1 |
|        502 | BRETT       |          1 |
|        503 | ANGEL       |          1 |
|        504 | NATHANIEL   |          1 |
|        505 | RAFAEL      |          1 |
|        506 | LESLIE      |          2 |
|        507 | EDGAR       |          2 |
|        508 | MILTON      |          2 |
|        509 | RAUL        |          1 |
|        510 | BEN         |          2 |
|        511 | CHESTER     |          1 |
|        512 | CECIL       |          1 |
|        513 | DUANE       |          2 |
|        514 | FRANKLIN    |          2 |
|        515 | ANDRE       |          1 |
|        516 | ELMER       |          2 |
|        517 | BRAD        |          2 |
|        518 | GABRIEL     |          1 |
|        519 | RON         |          2 |
|        520 | MITCHELL    |          2 |
|        521 | ROLAND      |          2 |
|        522 | ARNOLD      |          2 |
|        523 | HARVEY      |          1 |
|        524 | JARED       |          1 |
|        525 | ADRIAN      |          2 |
|        526 | KARL        |          2 |
|        527 | CORY        |          1 |
|        528 | CLAUDE      |          1 |
|        529 | ERIK        |          2 |
|        530 | DARRYL      |          2 |
|        531 | JAMIE       |          2 |
|        532 | NEIL        |          2 |
|        533 | JESSIE      |          1 |
|        534 | CHRISTIAN   |          1 |
|        535 | JAVIER      |          1 |
|        536 | FERNANDO    |          2 |
|        537 | CLINTON     |          2 |
|        538 | TED         |          2 |
|        539 | MATHEW      |          1 |
|        540 | TYRONE      |          1 |
|        541 | DARREN      |          2 |
|        542 | LONNIE      |          2 |
|        543 | LANCE       |          1 |
|        544 | CODY        |          2 |
|        545 | JULIO       |          2 |
|        546 | KELLY       |          1 |
|        547 | KURT        |          1 |
|        548 | ALLAN       |          1 |
|        549 | NELSON      |          1 |
|        550 | GUY         |          2 |
|        551 | CLAYTON     |          2 |
|        552 | HUGH        |          2 |
|        553 | MAX         |          1 |
|        554 | DWAYNE      |          1 |
|        555 | DWIGHT      |          1 |
|        556 | ARMANDO     |          2 |
|        557 | FELIX       |          1 |
|        558 | JIMMIE      |          1 |
|        559 | EVERETT     |          2 |
|        560 | JORDAN      |          1 |
|        561 | IAN         |          2 |
|        562 | WALLACE     |          1 |
|        563 | KEN         |          2 |
|        564 | BOB         |          2 |
|        565 | JAIME       |          2 |
|        566 | CASEY       |          1 |
|        567 | ALFREDO     |          2 |
|        568 | ALBERTO     |          2 |
|        569 | DAVE        |          2 |
|        570 | IVAN        |          2 |
|        571 | JOHNNIE     |          2 |
|        572 | SIDNEY      |          1 |
|        573 | BYRON       |          1 |
|        574 | JULIAN      |          2 |
|        575 | ISAAC       |          2 |
|        576 | MORRIS      |          2 |
|        577 | CLIFTON     |          2 |
|        578 | WILLARD     |          2 |
|        579 | DARYL       |          2 |
|        580 | ROSS        |          1 |
|        581 | VIRGIL      |          1 |
|        582 | ANDY        |          2 |
|        583 | MARSHALL    |          1 |
|        584 | SALVADOR    |          2 |
|        585 | PERRY       |          1 |
|        586 | KIRK        |          1 |
|        587 | SERGIO      |          1 |
|        588 | MARION      |          1 |
|        589 | TRACY       |          1 |
|        590 | SETH        |          2 |
|        591 | KENT        |          1 |
|        592 | TERRANCE    |          1 |
|        593 | RENE        |          2 |
|        594 | EDUARDO     |          1 |
|        595 | TERRENCE    |          1 |
|        596 | ENRIQUE     |          1 |
|        597 | FREDDIE     |          1 |
|        598 | WADE        |          1 |
|        599 | AUSTIN      |          2 |
|        600 | PEPE        |          2 |
|        601 | MARÍA       |          2 |
+------------+-------------+------------+
601 rows in set (0,00 sec)

```

Encontrar todas las películas y sus respectivas categorías.

```sql
SELECT f.title, c.nombre
FROM pelicula AS p
INNER JOIN film_text AS f ON p.id_pelicula = f.film_id
INNER JOIN pelicula_categoria AS pc ON p.id_pelicula = pc.id_pelicula
INNER JOIN categoria AS c ON c.id_categoria = pc.id_categoria;

```

| title                       | nombre      |
| --------------------------- | ----------- |
| ACADEMY DINOSAUR            | Documentary |
| ACE GOLDFINGER              | Horror      |
| ADAPTATION HOLES            | Documentary |
| AFFAIR PREJUDICE            | Horror      |
| AFRICAN EGG                 | Family      |
| AGENT TRUMAN                | Foreign     |
| AIRPLANE SIERRA             | Comedy      |
| AIRPORT POLLOCK             | Horror      |
| ALABAMA DEVIL               | Horror      |
| ALADDIN CALENDAR            | Sports      |
| ALAMO VIDEOTAPE             | Foreign     |
| ALASKA PHANTOM              | Music       |
| ALI FOREVER                 | Horror      |
| ALICE FANTASIA              | Classics    |
| ALIEN CENTER                | Foreign     |
| ALLEY EVOLUTION             | Foreign     |
| ALONE TRIP                  | Music       |
| ALTER VICTORY               | Animation   |
| AMADEUS HOLY                | Action      |
| AMELIE HELLFIGHTERS         | Music       |
| AMERICAN CIRCUS             | Action      |
| AMISTAD MIDSUMMER           | New         |
| ANACONDA CONFESSIONS        | Animation   |
| ANALYZE HOOSIERS            | Horror      |
| ANGELS LIFE                 | New         |
| ANNIE IDENTITY              | Sci-Fi      |
| ANONYMOUS HUMAN             | Sports      |
| ANTHEM LUKE                 | Comedy      |
| ANTITRUST TOMATOES          | Action      |
| ANYTHING SAVANNAH           | Horror      |
| APACHE DIVINE               | Family      |
| APOCALYPSE FLAMINGOS        | New         |
| APOLLO TEEN                 | Drama       |
| ARABIA DOGMA                | Horror      |
| ARACHNOPHOBIA ROLLERCOASTER | Horror      |
| ARGONAUTS TOWN              | Animation   |
| ARIZONA BANG                | Classics    |
| ARK RIDGEMONT               | Action      |
| ARMAGEDDON LOST             | Sci-Fi      |
| ARMY FLINTSTONES            | Documentary |
| ARSENIC INDEPENDENCE        | Travel      |
| ARTIST COLDBLOODED          | Sports      |
| ATLANTIS CAUSE              | Family      |
| ATTACKS HATE                | Sci-Fi      |
| ATTRACTION NEWTON           | New         |
| AUTUMN CROW                 | Games       |
| BABY HALL                   | Foreign     |
| BACKLASH UNDEFEATED         | Children    |
| BADMAN DAWN                 | Sci-Fi      |
| BAKED CLEOPATRA             | Family      |
| BALLOON HOMEWARD            | Music       |
| BALLROOM MOCKINGBIRD        | Foreign     |
| BANG KWAI                   | Family      |
| BANGER PINOCCHIO            | Music       |
| BARBARELLA STREETCAR        | Sci-Fi      |
| BAREFOOT MANCHURIAN         | Action      |
| BASIC EASY                  | Travel      |
| BEACH HEARTBREAKERS         | Documentary |
| BEAR GRACELAND              | Children    |
| BEAST HUNCHBACK             | Classics    |
| BEAUTY GREASE               | Drama       |
| BED HIGHBALL                | Documentary |
| BEDAZZLED MARRIED           | Family      |
| BEETHOVEN EXORCIST          | Drama       |
| BEHAVIOR RUNAWAY            | Horror      |
| BENEATH RUSH                | Children    |
| BERETS AGENT                | Action      |
| BETRAYED REAR               | Children    |
| BEVERLY OUTLAW              | Sci-Fi      |
| BIKINI BORROWERS            | Animation   |
| BILKO ANONYMOUS             | Family      |
| BILL OTHERS                 | Documentary |
| BINGO TALENTED              | Sci-Fi      |
| BIRCH ANTITRUST             | Music       |
| BIRD INDEPENDENCE           | Travel      |
| BIRDCAGE CASPER             | Music       |
| BIRDS PERDITION             | New         |
| BLACKOUT PRIVATE            | Animation   |
| BLADE POLISH                | Drama       |
| BLANKET BEVERLY             | Family      |
| BLINDNESS GUN               | Sci-Fi      |
| BLOOD ARGONAUTS             | Family      |
| BLUES INSTINCT              | Family      |
| BOILED DARES                | Travel      |
| BONNIE HOLOCAUST            | Documentary |
| BOOGIE AMELIE               | Music       |
| BOONDOCK BALLROOM           | Travel      |
| BORN SPINAL                 | Travel      |
| BORROWERS BEDAZZLED         | Animation   |
| BOULEVARD MOB               | New         |
| BOUND CHEAPER               | Classics    |
| BOWFINGER GABLES            | Horror      |
| BRANNIGAN SUNRISE           | New         |
| BRAVEHEART HUMAN            | Family      |
| BREAKFAST GOLDFINGER        | New         |
| BREAKING HOME               | New         |
| BRIDE INTRIGUE              | Action      |
| BRIGHT ENCOUNTERS           | Drama       |
| BRINGING HYSTERICAL         | Comedy      |
| BROOKLYN DESERT             | Foreign     |
| BROTHERHOOD BLANKET         | Documentary |
| BUBBLE GROSSE               | Sports      |
| BUCKET BROTHERHOOD          | Travel      |
| BUGSY SONG                  | Foreign     |
| BULL SHAWSHANK              | Action      |
| BULWORTH COMMANDMENTS       | Games       |
| BUNCH MINDS                 | Drama       |
| BUTCH PANTHER               | New         |
| BUTTERFLY CHOCOLAT          | New         |
| CABIN FLASH                 | Children    |
| CADDYSHACK JEDI             | Action      |
| CALENDAR GUNFIGHT           | Foreign     |
| CALIFORNIA BIRDS            | Sports      |
| CAMELOT VACATION            | Sci-Fi      |
| CAMPUS REMEMBER             | Action      |
| CANDIDATE PERDITION         | Classics    |
| CANDLES GRAPES              | Games       |
| CANYON STOCK                | Animation   |
| CAPER MOTIONS               | Comedy      |
| CARIBBEAN LIBERTY           | Sports      |
| CAROL TEXAS                 | Animation   |
| CARRIE BUNCH                | Horror      |
| CASABLANCA SUPER            | Travel      |
| CASPER DRAGONFLY            | Children    |
| CASSIDY WYOMING             | Travel      |
| CASUALTIES ENCINO           | Action      |
| CAT CONEHEADS               | Comedy      |
| CATCH AMISTAD               | Foreign     |
| CAUSE DATE                  | Documentary |
| CELEBRITY HORN              | Action      |
| CENTER DINOSAUR             | Classics    |
| CHAINSAW UPTOWN             | Sci-Fi      |
| CHAMBER ITALIAN             | Music       |
| CHAMPION FLATLINERS         | Animation   |
| CHANCE RESURRECTION         | Sports      |
| CHAPLIN LICENSE             | New         |
| CHARADE DUFFEL              | Sci-Fi      |
| CHARIOTS CONSPIRACY         | Sci-Fi      |
| CHASING FIGHT               | Family      |
| CHEAPER CLYDE               | Sci-Fi      |
| CHICAGO NORTH               | Games       |
| CHICKEN HELLFIGHTERS        | Documentary |
| CHILL LUCK                  | Drama       |
| CHINATOWN GLADIATOR         | New         |
| CHISUM BEHAVIOR             | Family      |
| CHITTY LOCK                 | Drama       |
| CHOCOLAT HARRY              | Family      |
| CHOCOLATE DUCK              | Foreign     |
| CHRISTMAS MOONSHINE         | Children    |
| CIDER DESIRE                | Documentary |
| CINCINATTI WHISPERER        | Sci-Fi      |
| CIRCUS YOUTH                | Children    |
| CITIZEN SHREK               | Sci-Fi      |
| CLASH FREDDY                | Animation   |
| CLEOPATRA DEVIL             | New         |
| CLERKS ANGELS               | Documentary |
| CLOCKWORK PARADISE          | Children    |
| CLONES PINOCCHIO            | Music       |
| CLOSER BANG                 | Comedy      |
| CLUB GRAFFITI               | Animation   |
| CLUE GRAIL                  | Music       |
| CLUELESS BUCKET             | Action      |
| CLYDE THEORY                | New         |
| COAST RAINBOW               | Documentary |
| COLDBLOODED DARLING         | Sci-Fi      |
| COLOR PHILADELPHIA          | Classics    |
| COMA HEAD                   | Travel      |
| COMANCHEROS ENEMY           | Children    |
| COMFORTS RUSH               | Travel      |
| COMMAND DARLING             | Foreign     |
| COMMANDMENTS EXPRESS        | Horror      |
| CONEHEADS SMOOCHY           | Drama       |
| CONFESSIONS MAGUIRE         | Drama       |
| CONFIDENTIAL INTERVIEW      | Music       |
| CONFUSED CANDLES            | Family      |
| CONGENIALITY QUEST          | Sports      |
| CONNECTICUT TRAMP           | Sci-Fi      |
| CONNECTION MICROCOSMOS      | Comedy      |
| CONQUERER NUTS              | Drama       |
| CONSPIRACY SPIRIT           | Classics    |
| CONTACT ANONYMOUS           | Travel      |
| CONTROL ANTHEM              | Comedy      |
| CONVERSATION DOWNHILL       | Family      |
| CORE SUIT                   | Classics    |
| COWBOY DOOM                 | Foreign     |
| CRAFT OUTFIELD              | Drama       |
| CRANES RESERVOIR            | Sports      |
| CRAZY HOME                  | Comedy      |
| CREATURES SHAKESPEARE       | Games       |
| CREEPERS KANE               | Classics    |
| CROOKED FROGMEN             | Children    |
| CROSSING DIVORCE            | Foreign     |
| CROSSROADS CASUALTIES       | Animation   |
| CROW GREASE                 | Action      |
| CROWDS TELEMARK             | Sci-Fi      |
| CRUELTY UNFORGIVEN          | Classics    |
| CRUSADE HONEY               | Sports      |
| CRYSTAL BREAKING            | Foreign     |
| CUPBOARD SINNERS            | Documentary |
| CURTAIN VIDEOTAPE           | Games       |

Listar los nombres de las ciudades junto con sus países.

```sql
SELECT c.nombre, p.nombre
FROM ciudad AS c
INNER JOIN pais AS p ON c.id_pais = p.id_pais;
```

| nombre                     | nombre                                |
| -------------------------- | ------------------------------------- |
| Kabul                      | Afghanistan                           |
| Batna                      | Algeria                               |
| Bchar                      | Algeria                               |
| Skikda                     | Algeria                               |
| Tafuna                     | American Samoa                        |
| Benguela                   | Angola                                |
| Namibe                     | Angola                                |
| South Hill                 | Anguilla                              |
| Almirante Brown            | Argentina                             |
| Avellaneda                 | Argentina                             |
| Baha Blanca                | Argentina                             |
| Crdoba                     | Argentina                             |
| Escobar                    | Argentina                             |
| Ezeiza                     | Argentina                             |
| La Plata                   | Argentina                             |
| Merlo                      | Argentina                             |
| Quilmes                    | Argentina                             |
| San Miguel de Tucumn       | Argentina                             |
| Santa F                    | Argentina                             |
| Tandil                     | Argentina                             |
| Vicente Lpez               | Argentina                             |
| Yerevan                    | Armenia                               |
| Woodridge                  | Australia                             |
| Graz                       | Austria                               |
| Linz                       | Austria                               |
| Salzburg                   | Austria                               |
| Baku                       | Azerbaijan                            |
| Sumqayit                   | Azerbaijan                            |
| al-Manama                  | Bahrain                               |
| Dhaka                      | Bangladesh                            |
| Jamalpur                   | Bangladesh                            |
| Tangail                    | Bangladesh                            |
| Mogiljov                   | Belarus                               |
| Molodetno                  | Belarus                               |
| El Alto                    | Bolivia                               |
| Sucre                      | Bolivia                               |
| Alvorada                   | Brazil                                |
| Angra dos Reis             | Brazil                                |
| Anpolis                    | Brazil                                |
| Aparecida de Goinia        | Brazil                                |
| Araatuba                   | Brazil                                |
| Bag                        | Brazil                                |
| Belm                       | Brazil                                |
| Blumenau                   | Brazil                                |
| Boa Vista                  | Brazil                                |
| Braslia                    | Brazil                                |
| Goinia                     | Brazil                                |
| Guaruj                     | Brazil                                |
| guas Lindas de Gois        | Brazil                                |
| Ibirit                     | Brazil                                |
| Juazeiro do Norte          | Brazil                                |
| Juiz de Fora               | Brazil                                |
| Luzinia                    | Brazil                                |
| Maring                     | Brazil                                |
| Po                         | Brazil                                |
| Poos de Caldas             | Brazil                                |
| Rio Claro                  | Brazil                                |
| Santa Brbara dOeste        | Brazil                                |
| Santo Andr                 | Brazil                                |
| So Bernardo do Campo       | Brazil                                |
| So Leopoldo                | Brazil                                |
| Sorocaba                   | Brazil                                |
| Vila Velha                 | Brazil                                |
| Vitria de Santo Anto       | Brazil                                |
| Bandar Seri Begawan        | Brunei                                |
| Ruse                       | Bulgaria                              |
| Stara Zagora               | Bulgaria                              |
| Battambang                 | Cambodia                              |
| Phnom Penh                 | Cambodia                              |
| Bamenda                    | Cameroon                              |
| Yaound                     | Cameroon                              |
| Gatineau                   | Canada                                |
| Halifax                    | Canada                                |
| Lethbridge                 | Canada                                |
| London                     | Canada                                |
| Oshawa                     | Canada                                |
| Richmond Hill              | Canada                                |
| Vancouver                  | Canada                                |
| NDjamna                    | Chad                                  |
| Antofagasta                | Chile                                 |
| Coquimbo                   | Chile                                 |
| Rancagua                   | Chile                                 |
| Baicheng                   | China                                 |
| Baiyin                     | China                                 |
| Binzhou                    | China                                 |
| Changzhou                  | China                                 |
| Datong                     | China                                 |
| Daxian                     | China                                 |
| Dongying                   | China                                 |
| Emeishan                   | China                                 |
| Enshi                      | China                                 |
| Ezhou                      | China                                 |
| Fuyu                       | China                                 |
| Fuzhou                     | China                                 |
| Haining                    | China                                 |
| Hami                       | China                                 |
| Hohhot                     | China                                 |
| Huaian                     | China                                 |
| Jinchang                   | China                                 |
| Jining                     | China                                 |
| Jinzhou                    | China                                 |
| Junan                      | China                                 |
| Korla                      | China                                 |
| Laiwu                      | China                                 |
| Laohekou                   | China                                 |
| Lengshuijiang              | China                                 |
| Leshan                     | China                                 |
| Liaocheng                  | China                                 |
| Meixian                    | China                                 |
| Nanyang                    | China                                 |
| Pingxiang                  | China                                 |
| Qinhuangdao                | China                                 |
| Rizhao                     | China                                 |
| Sanya                      | China                                 |
| Shanwei                    | China                                 |
| Shaoguan                   | China                                 |
| Shenzhen                   | China                                 |
| Suihua                     | China                                 |
| Tianjin                    | China                                 |
| Tiefa                      | China                                 |
| Tieli                      | China                                 |
| Tongliao                   | China                                 |
| Weifang                    | China                                 |
| Xiangfan                   | China                                 |
| Xiangtan                   | China                                 |
| Xintai                     | China                                 |
| Xinxiang                   | China                                 |
| Yantai                     | China                                 |
| Yinchuan                   | China                                 |
| Yingkou                    | China                                 |
| Yuncheng                   | China                                 |
| Yuzhou                     | China                                 |
| Zalantun                   | China                                 |
| Zaoyang                    | China                                 |
| Zhoushan                   | China                                 |
| Buenaventura               | Colombia                              |
| Dos Quebradas              | Colombia                              |
| Florencia                  | Colombia                              |
| Pereira                    | Colombia                              |
| Sincelejo                  | Colombia                              |
| Sogamoso                   | Colombia                              |
| Lubumbashi                 | Congo, The Democratic Republic of the |
| Mwene-Ditu                 | Congo, The Democratic Republic of the |
| Olomouc                    | Czech Republic                        |
| La Romana                  | Dominican Republic                    |
| San Felipe de Puerto Plata | Dominican Republic                    |
| Santiago de los Caballeros | Dominican Republic                    |
| Loja                       | Ecuador                               |
| Portoviejo                 | Ecuador                               |
| Robamba                    | Ecuador                               |
| Bilbays                    | Egypt                                 |
| Idfu                       | Egypt                                 |
| Mit Ghamr                  | Egypt                                 |
| Qalyub                     | Egypt                                 |
| Sawhaj                     | Egypt                                 |
| Shubra al-Khayma           | Egypt                                 |
| Tartu                      | Estonia                               |
| Addis Abeba                | Ethiopia                              |
| Trshavn                    | Faroe Islands                         |
| Oulu                       | Finland                               |
| Brest                      | France                                |
| Le Mans                    | France                                |
| Toulon                     | France                                |
| Toulouse                   | France                                |
| Cayenne                    | French Guiana                         |
| Faaa                       | French Polynesia                      |
| Papeete                    | French Polynesia                      |
| Banjul                     | Gambia                                |
| Duisburg                   | Germany                               |
| Erlangen                   | Germany                               |
| Halle/Saale                | Germany                               |
| Mannheim                   | Germany                               |
| Saarbrcken                 | Germany                               |
| Siegen                     | Germany                               |
| Witten                     | Germany                               |
| Athenai                    | Greece                                |
| Patras                     | Greece                                |
| Nuuk                       | Greenland                             |
| Citt del Vaticano          | Holy See (Vatican City State)         |
| Kowloon and New Kowloon    | Hong Kong                             |
| Szkesfehrvr                | Hungary                               |
| Adoni                      | India                                 |
| Ahmadnagar                 | India                                 |
| Allappuzha (Alleppey)      | India                                 |
| Ambattur                   | India                                 |
| Amroha                     | India                                 |
| Balurghat                  | India                                 |
| Berhampore (Baharampur)    | India                                 |
| Bhavnagar                  | India                                 |
| Bhilwara                   | India                                 |
| Bhimavaram                 | India                                 |
| Bhopal                     | India                                 |
| Bhusawal                   | India                                 |
| Bijapur                    | India                                 |
| Chandrapur                 | India                                 |
| Chapra                     | India                                 |
| Dhule (Dhulia)             | India                                 |
| Etawah                     | India                                 |
| Firozabad                  | India                                 |
| Gandhinagar                | India                                 |

Obtener los detalles de los alquileres, incluyendo el cliente y el empleado que gestionó el alquiler.

```sql
SELECT a.id_alquiler, a.fecha_alquiler, a.id_inventario, a.id_cliente, c.nombre AS Nombre_cliente, a.fecha_devolucion, a.id_empleado, e.nombre AS Nombre_empleado, a.ultima_actualizacion 
FROM alquiler AS a
INNER JOIN cliente AS c ON a.id_cliente = c.id_cliente
INNER JOIN empleado AS e ON a.id_empleado = e.id_empleado;
```

| id_alquiler | fecha_alquiler      | id_inventario | id_cliente | nombre cliente | fecha_devolucion    | id_empleado | nombre empleado | ultima_actualizacion |
| ----------- | ------------------- | ------------- | ---------- | -------------- | ------------------- | ----------- | --------------- | -------------------- |
| 76          | 2005-05-25 11:30:37 | 3021          | 1          | MARY           | 2005-06-03 12:00:37 | 2           | Jon             | 2006-02-15 21:30:53  |
| 573         | 2005-05-28 10:35:23 | 4020          | 1          | MARY           | 2005-06-03 06:32:23 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1185        | 2005-06-15 00:54:12 | 2785          | 1          | MARY           | 2005-06-23 02:42:12 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1422        | 2005-06-15 18:02:53 | 1021          | 1          | MARY           | 2005-06-19 15:54:53 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1476        | 2005-06-15 21:08:46 | 1407          | 1          | MARY           | 2005-06-25 02:26:46 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1725        | 2005-06-16 15:18:57 | 726           | 1          | MARY           | 2005-06-17 21:05:57 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2308        | 2005-06-18 08:41:48 | 197           | 1          | MARY           | 2005-06-22 03:36:48 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2363        | 2005-06-18 13:33:59 | 3497          | 1          | MARY           | 2005-06-19 17:40:59 | 1           | Mike            | 2006-02-15 21:30:53  |
| 3284        | 2005-06-21 06:24:45 | 4566          | 1          | MARY           | 2005-06-28 03:28:45 | 1           | Mike            | 2006-02-15 21:30:53  |
| 4526        | 2005-07-08 03:17:05 | 1443          | 1          | MARY           | 2005-07-14 01:19:05 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4611        | 2005-07-08 07:33:56 | 3486          | 1          | MARY           | 2005-07-12 13:25:56 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5244        | 2005-07-09 13:24:07 | 3726          | 1          | MARY           | 2005-07-14 14:01:07 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5326        | 2005-07-09 16:38:01 | 797           | 1          | MARY           | 2005-07-13 18:02:01 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6163        | 2005-07-11 10:13:46 | 1330          | 1          | MARY           | 2005-07-19 13:15:46 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7273        | 2005-07-27 11:31:22 | 2465          | 1          | MARY           | 2005-07-31 06:50:22 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7841        | 2005-07-28 09:04:45 | 1092          | 1          | MARY           | 2005-07-30 12:37:45 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8033        | 2005-07-28 16:18:23 | 4268          | 1          | MARY           | 2005-07-30 17:56:23 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8074        | 2005-07-28 17:33:39 | 1558          | 1          | MARY           | 2005-07-29 20:17:39 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8116        | 2005-07-28 19:20:07 | 4497          | 1          | MARY           | 2005-07-29 22:54:07 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8326        | 2005-07-29 03:58:49 | 108           | 1          | MARY           | 2005-08-01 05:16:49 | 2           | Jon             | 2006-02-15 21:30:53  |
| 9571        | 2005-07-31 02:42:18 | 2219          | 1          | MARY           | 2005-08-02 23:26:18 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10437       | 2005-08-01 08:51:04 | 14            | 1          | MARY           | 2005-08-10 12:12:04 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11299       | 2005-08-02 15:36:52 | 3232          | 1          | MARY           | 2005-08-10 16:40:52 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11367       | 2005-08-02 18:01:38 | 1440          | 1          | MARY           | 2005-08-04 13:19:38 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11824       | 2005-08-17 12:37:54 | 2639          | 1          | MARY           | 2005-08-19 10:11:54 | 2           | Jon             | 2006-02-15 21:30:53  |
| 12250       | 2005-08-18 03:57:29 | 921           | 1          | MARY           | 2005-08-22 23:05:29 | 1           | Mike            | 2006-02-15 21:30:53  |
| 13068       | 2005-08-19 09:55:16 | 3019          | 1          | MARY           | 2005-08-20 14:44:16 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13176       | 2005-08-19 13:56:54 | 2269          | 1          | MARY           | 2005-08-23 08:50:54 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14762       | 2005-08-21 23:33:57 | 4249          | 1          | MARY           | 2005-08-23 01:30:57 | 1           | Mike            | 2006-02-15 21:30:53  |
| 14825       | 2005-08-22 01:27:57 | 1449          | 1          | MARY           | 2005-08-27 07:01:57 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15298       | 2005-08-22 19:41:37 | 1446          | 1          | MARY           | 2005-08-28 22:49:37 | 1           | Mike            | 2006-02-15 21:30:53  |
| 15315       | 2005-08-22 20:03:46 | 312           | 1          | MARY           | 2005-08-30 01:51:46 | 2           | Jon             | 2006-02-15 21:30:53  |
| 320         | 2005-05-27 00:09:24 | 1090          | 2          | PATRICIA       | 2005-05-28 04:30:24 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2128        | 2005-06-17 20:54:58 | 352           | 2          | PATRICIA       | 2005-06-24 00:41:58 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5636        | 2005-07-10 06:31:24 | 4116          | 2          | PATRICIA       | 2005-07-13 02:36:24 | 1           | Mike            | 2006-02-15 21:30:53  |
| 5755        | 2005-07-10 12:38:56 | 2760          | 2          | PATRICIA       | 2005-07-19 17:02:56 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7346        | 2005-07-27 14:30:42 | 741           | 2          | PATRICIA       | 2005-08-02 16:48:42 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7376        | 2005-07-27 15:23:02 | 488           | 2          | PATRICIA       | 2005-08-04 10:35:02 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7459        | 2005-07-27 18:40:20 | 2053          | 2          | PATRICIA       | 2005-08-02 21:07:20 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8230        | 2005-07-29 00:12:59 | 1937          | 2          | PATRICIA       | 2005-08-06 19:52:59 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8598        | 2005-07-29 12:56:59 | 626           | 2          | PATRICIA       | 2005-08-01 08:39:59 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8705        | 2005-07-29 17:14:29 | 4038          | 2          | PATRICIA       | 2005-08-02 16:01:29 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9031        | 2005-07-30 06:06:10 | 2377          | 2          | PATRICIA       | 2005-08-04 10:45:10 | 2           | Jon             | 2006-02-15 21:30:53  |
| 9236        | 2005-07-30 13:47:43 | 4030          | 2          | PATRICIA       | 2005-08-08 18:52:43 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9248        | 2005-07-30 14:14:11 | 1382          | 2          | PATRICIA       | 2005-08-05 11:19:11 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9296        | 2005-07-30 16:21:13 | 4088          | 2          | PATRICIA       | 2005-08-08 11:57:13 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9465        | 2005-07-30 22:39:53 | 3084          | 2          | PATRICIA       | 2005-08-06 16:43:53 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10136       | 2005-07-31 21:58:56 | 3142          | 2          | PATRICIA       | 2005-08-03 19:44:56 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10466       | 2005-08-01 09:45:26 | 138           | 2          | PATRICIA       | 2005-08-06 06:28:26 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10918       | 2005-08-02 02:10:56 | 3418          | 2          | PATRICIA       | 2005-08-02 21:23:56 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11087       | 2005-08-02 07:41:41 | 654           | 2          | PATRICIA       | 2005-08-10 10:37:41 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11177       | 2005-08-02 10:43:48 | 1149          | 2          | PATRICIA       | 2005-08-10 10:55:48 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11256       | 2005-08-02 13:44:53 | 2060          | 2          | PATRICIA       | 2005-08-04 16:39:53 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11614       | 2005-08-17 03:52:18 | 805           | 2          | PATRICIA       | 2005-08-20 07:04:18 | 1           | Mike            | 2006-02-15 21:30:53  |
| 12963       | 2005-08-19 06:26:04 | 1521          | 2          | PATRICIA       | 2005-08-23 11:37:04 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14475       | 2005-08-21 13:24:32 | 3164          | 2          | PATRICIA       | 2005-08-27 08:59:32 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14743       | 2005-08-21 22:41:56 | 4570          | 2          | PATRICIA       | 2005-08-29 00:18:56 | 1           | Mike            | 2006-02-15 21:30:53  |
| 15145       | 2005-08-22 13:53:04 | 2179          | 2          | PATRICIA       | 2005-08-31 15:51:04 | 1           | Mike            | 2006-02-15 21:30:53  |
| 15907       | 2005-08-23 17:39:35 | 2898          | 2          | PATRICIA       | 2005-08-25 23:23:35 | 1           | Mike            | 2006-02-15 21:30:53  |
| 435         | 2005-05-27 17:17:09 | 3328          | 3          | LINDA          | 2005-06-02 11:20:09 | 2           | Jon             | 2006-02-15 21:30:53  |
| 830         | 2005-05-29 22:43:55 | 3464          | 3          | LINDA          | 2005-06-01 17:43:55 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1546        | 2005-06-16 01:34:05 | 3913          | 3          | LINDA          | 2005-06-24 04:27:05 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1726        | 2005-06-16 15:19:10 | 116           | 3          | LINDA          | 2005-06-25 11:39:10 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1911        | 2005-06-17 05:15:15 | 910           | 3          | LINDA          | 2005-06-24 11:05:15 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2628        | 2005-06-19 08:34:53 | 3917          | 3          | LINDA          | 2005-06-28 04:19:53 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4180        | 2005-07-07 10:23:25 | 1704          | 3          | LINDA          | 2005-07-10 13:18:25 | 1           | Mike            | 2006-02-15 21:30:53  |
| 4725        | 2005-07-08 12:47:11 | 2058          | 3          | LINDA          | 2005-07-15 09:08:11 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7096        | 2005-07-27 04:54:42 | 2575          | 3          | LINDA          | 2005-08-03 01:42:42 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7503        | 2005-07-27 20:23:12 | 579           | 3          | LINDA          | 2005-08-05 18:46:12 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7703        | 2005-07-28 03:59:21 | 2150          | 3          | LINDA          | 2005-08-05 08:52:21 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7724        | 2005-07-28 04:46:30 | 346           | 3          | LINDA          | 2005-08-04 08:41:30 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7911        | 2005-07-28 11:46:45 | 390           | 3          | LINDA          | 2005-07-29 07:19:45 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8086        | 2005-07-28 18:17:14 | 1182          | 3          | LINDA          | 2005-07-30 18:22:14 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8545        | 2005-07-29 11:07:04 | 3261          | 3          | LINDA          | 2005-08-06 13:30:04 | 2           | Jon             | 2006-02-15 21:30:53  |
| 9226        | 2005-07-30 13:31:20 | 4315          | 3          | LINDA          | 2005-08-06 16:42:20 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9443        | 2005-07-30 21:45:46 | 1675          | 3          | LINDA          | 2005-08-05 21:22:46 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9595        | 2005-07-31 03:27:58 | 2829          | 3          | LINDA          | 2005-08-03 05:58:58 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9816        | 2005-07-31 11:32:58 | 4560          | 3          | LINDA          | 2005-08-04 17:12:58 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10597       | 2005-08-01 14:19:48 | 3292          | 3          | LINDA          | 2005-08-08 20:01:48 | 1           | Mike            | 2006-02-15 21:30:53  |
| 12556       | 2005-08-18 14:49:55 | 1984          | 3          | LINDA          | 2005-08-24 15:20:55 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13403       | 2005-08-19 22:18:07 | 3241          | 3          | LINDA          | 2005-08-27 19:23:07 | 1           | Mike            | 2006-02-15 21:30:53  |
| 13610       | 2005-08-20 06:14:12 | 2526          | 3          | LINDA          | 2005-08-26 00:44:12 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14699       | 2005-08-21 20:50:48 | 1427          | 3          | LINDA          | 2005-08-29 18:08:48 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15038       | 2005-08-22 09:37:27 | 1685          | 3          | LINDA          | 2005-08-23 14:39:27 | 1           | Mike            | 2006-02-15 21:30:53  |
| 15619       | 2005-08-23 07:10:14 | 2468          | 3          | LINDA          | 2005-08-26 07:21:14 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1297        | 2005-06-15 09:31:28 | 1075          | 4          | BARBARA        | 2005-06-19 04:33:28 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1633        | 2005-06-16 08:08:40 | 280           | 4          | BARBARA        | 2005-06-17 11:12:40 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1707        | 2005-06-16 14:01:27 | 185           | 4          | BARBARA        | 2005-06-18 09:35:27 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1735        | 2005-06-16 15:51:52 | 97            | 4          | BARBARA        | 2005-06-20 13:27:52 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2043        | 2005-06-17 14:31:12 | 2495          | 4          | BARBARA        | 2005-06-19 11:04:12 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2642        | 2005-06-19 09:39:01 | 2065          | 4          | BARBARA        | 2005-06-25 08:33:01 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7660        | 2005-07-28 02:10:10 | 4385          | 4          | BARBARA        | 2005-07-30 04:29:10 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7718        | 2005-07-28 04:37:59 | 3587          | 4          | BARBARA        | 2005-07-29 09:20:59 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8741        | 2005-07-29 18:44:57 | 165           | 4          | BARBARA        | 2005-08-03 18:25:57 | 2           | Jon             | 2006-02-15 21:30:53  |
| 9100        | 2005-07-30 08:46:09 | 4117          | 4          | BARBARA        | 2005-08-05 10:34:09 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9371        | 2005-07-30 18:58:00 | 2980          | 4          | BARBARA        | 2005-08-03 15:14:00 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11069       | 2005-08-02 07:09:34 | 57            | 4          | BARBARA        | 2005-08-08 08:39:34 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11110       | 2005-08-02 08:20:31 | 4311          | 4          | BARBARA        | 2005-08-04 05:06:31 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11529       | 2005-08-17 00:28:01 | 3071          | 4          | BARBARA        | 2005-08-19 04:47:01 | 2           | Jon             | 2006-02-15 21:30:53  |
| 12151       | 2005-08-18 00:14:03 | 1976          | 4          | BARBARA        | 2005-08-18 23:52:03 | 2           | Jon             | 2006-02-15 21:30:53  |
| 12294       | 2005-08-18 05:14:44 | 2479          | 4          | BARBARA        | 2005-08-27 01:32:44 | 2           | Jon             | 2006-02-15 21:30:53  |
| 12856       | 2005-08-19 02:19:13 | 132           | 4          | BARBARA        | 2005-08-23 07:49:13 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13704       | 2005-08-20 09:32:04 | 3373          | 4          | BARBARA        | 2005-08-23 14:29:04 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13807       | 2005-08-20 12:55:40 | 3822          | 4          | BARBARA        | 2005-08-28 09:06:40 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14225       | 2005-08-21 04:53:37 | 984           | 4          | BARBARA        | 2005-08-25 23:39:37 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15147       | 2005-08-22 13:58:23 | 2553          | 4          | BARBARA        | 2005-08-28 14:33:23 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15635       | 2005-08-23 07:43:00 | 3308          | 4          | BARBARA        | 2005-08-27 10:47:00 | 1           | Mike            | 2006-02-15 21:30:53  |
| 731         | 2005-05-29 07:25:16 | 4124          | 5          | ELIZABETH      | 2005-05-30 05:21:16 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1085        | 2005-05-31 11:15:43 | 301           | 5          | ELIZABETH      | 2005-06-07 12:02:43 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1142        | 2005-05-31 19:46:38 | 3998          | 5          | ELIZABETH      | 2005-06-05 14:03:38 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1502        | 2005-06-15 22:03:14 | 3277          | 5          | ELIZABETH      | 2005-06-23 18:42:14 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1631        | 2005-06-16 08:01:02 | 2466          | 5          | ELIZABETH      | 2005-06-19 09:04:02 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2063        | 2005-06-17 15:56:53 | 4323          | 5          | ELIZABETH      | 2005-06-21 14:19:53 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2570        | 2005-06-19 04:20:13 | 1105          | 5          | ELIZABETH      | 2005-06-25 07:00:13 | 1           | Mike            | 2006-02-15 21:30:53  |
| 3126        | 2005-06-20 18:38:22 | 1183          | 5          | ELIZABETH      | 2005-06-26 00:00:22 | 1           | Mike            | 2006-02-15 21:30:53  |
| 3677        | 2005-07-06 09:11:58 | 600           | 5          | ELIZABETH      | 2005-07-08 10:50:58 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4889        | 2005-07-08 20:04:43 | 4463          | 5          | ELIZABETH      | 2005-07-13 17:57:43 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5016        | 2005-07-09 01:57:57 | 1871          | 5          | ELIZABETH      | 2005-07-09 22:07:57 | 1           | Mike            | 2006-02-15 21:30:53  |
| 5118        | 2005-07-09 07:13:52 | 957           | 5          | ELIZABETH      | 2005-07-18 05:18:52 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5156        | 2005-07-09 08:51:42 | 416           | 5          | ELIZABETH      | 2005-07-15 03:59:42 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5721        | 2005-07-10 11:09:35 | 2348          | 5          | ELIZABETH      | 2005-07-17 16:41:35 | 2           | Jon             | 2006-02-15 21:30:53  |
| 6042        | 2005-07-11 03:17:04 | 2153          | 5          | ELIZABETH      | 2005-07-19 07:08:04 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6663        | 2005-07-12 11:27:35 | 4364          | 5          | ELIZABETH      | 2005-07-21 16:35:35 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6685        | 2005-07-12 12:16:28 | 1434          | 5          | ELIZABETH      | 2005-07-19 17:03:28 | 1           | Mike            | 2006-02-15 21:30:53  |
| 7293        | 2005-07-27 12:37:28 | 3333          | 5          | ELIZABETH      | 2005-07-30 15:12:28 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7652        | 2005-07-28 01:50:29 | 92            | 5          | ELIZABETH      | 2005-07-30 22:23:29 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7829        | 2005-07-28 08:43:39 | 111           | 5          | ELIZABETH      | 2005-08-04 14:33:39 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8263        | 2005-07-29 01:11:23 | 28            | 5          | ELIZABETH      | 2005-07-31 01:53:23 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8978        | 2005-07-30 04:14:28 | 711           | 5          | ELIZABETH      | 2005-08-06 09:08:28 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9493        | 2005-07-30 23:52:30 | 1522          | 5          | ELIZABETH      | 2005-08-08 05:22:30 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9888        | 2005-07-31 14:00:53 | 4400          | 5          | ELIZABETH      | 2005-08-08 18:51:53 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10609       | 2005-08-01 14:48:45 | 2587          | 5          | ELIZABETH      | 2005-08-04 13:41:45 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10625       | 2005-08-01 15:27:10 | 3022          | 5          | ELIZABETH      | 2005-08-02 13:16:10 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11001       | 2005-08-02 04:56:45 | 3701          | 5          | ELIZABETH      | 2005-08-11 08:04:45 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11179       | 2005-08-02 10:50:06 | 4376          | 5          | ELIZABETH      | 2005-08-04 05:24:06 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11930       | 2005-08-17 16:28:53 | 1299          | 5          | ELIZABETH      | 2005-08-25 10:31:53 | 1           | Mike            | 2006-02-15 21:30:53  |
| 12145       | 2005-08-18 00:10:04 | 3482          | 5          | ELIZABETH      | 2005-08-26 00:51:04 | 1           | Mike            | 2006-02-15 21:30:53  |
| 12797       | 2005-08-19 00:24:08 | 1595          | 5          | ELIZABETH      | 2005-08-21 22:53:08 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13063       | 2005-08-19 09:45:41 | 1192          | 5          | ELIZABETH      | 2005-08-24 09:11:41 | 2           | Jon             | 2006-02-15 21:30:53  |
| 13209       | 2006-02-14 15:16:03 | 1574          | 5          | ELIZABETH      |                     | 2           | Jon             | 2006-02-15 21:30:53  |
| 13877       | 2005-08-20 15:16:18 | 3387          | 5          | ELIZABETH      | 2005-08-22 18:20:18 | 1           | Mike            | 2006-02-15 21:30:53  |
| 14053       | 2005-08-20 22:13:59 | 2177          | 5          | ELIZABETH      | 2005-08-26 20:50:59 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14430       | 2005-08-21 11:31:11 | 2623          | 5          | ELIZABETH      | 2005-08-26 06:29:11 | 1           | Mike            | 2006-02-15 21:30:53  |
| 14494       | 2005-08-21 14:02:50 | 169           | 5          | ELIZABETH      | 2005-08-22 16:45:50 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15232       | 2005-08-22 17:37:02 | 61            | 5          | ELIZABETH      | 2005-08-25 18:45:02 | 1           | Mike            | 2006-02-15 21:30:53  |
| 57          | 2005-05-25 08:43:32 | 3938          | 6          | JENNIFER       | 2005-05-29 06:42:32 | 2           | Jon             | 2006-02-15 21:30:53  |
| 577         | 2005-05-28 11:09:14 | 375           | 6          | JENNIFER       | 2005-06-01 13:27:14 | 2           | Jon             | 2006-02-15 21:30:53  |
| 916         | 2005-05-30 11:25:01 | 1290          | 6          | JENNIFER       | 2005-05-31 09:06:01 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1575        | 2005-06-16 03:41:38 | 3317          | 6          | JENNIFER       | 2005-06-22 03:01:38 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1841        | 2005-06-16 23:44:13 | 2363          | 6          | JENNIFER       | 2005-06-22 04:09:13 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1966        | 2005-06-17 09:19:45 | 2085          | 6          | JENNIFER       | 2005-06-20 11:19:45 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2345        | 2005-06-18 12:03:23 | 1818          | 6          | JENNIFER       | 2005-06-22 14:25:23 | 2           | Jon             | 2006-02-15 21:30:53  |
| 3983        | 2005-07-06 23:14:21 | 1261          | 6          | JENNIFER       | 2005-07-12 17:55:21 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4278        | 2005-07-07 14:53:24 | 3693          | 6          | JENNIFER       | 2005-07-13 14:21:24 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5553        | 2005-07-10 03:03:35 | 1686          | 6          | JENNIFER       | 2005-07-14 07:49:35 | 2           | Jon             | 2006-02-15 21:30:53  |
| 6211        | 2005-07-11 12:39:01 | 2699          | 6          | JENNIFER       | 2005-07-20 15:59:01 | 2           | Jon             | 2006-02-15 21:30:53  |
| 6248        | 2005-07-11 15:01:54 | 2686          | 6          | JENNIFER       | 2005-07-19 16:58:54 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6686        | 2005-07-12 12:18:38 | 3804          | 6          | JENNIFER       | 2005-07-13 17:56:38 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7099        | 2005-07-27 05:03:44 | 3136          | 6          | JENNIFER       | 2005-07-29 00:12:44 | 2           | Jon             | 2006-02-15 21:30:53  |
| 7136        | 2005-07-27 06:38:25 | 1929          | 6          | JENNIFER       | 2005-08-03 05:13:25 | 1           | Mike            | 2006-02-15 21:30:53  |
| 8101        | 2005-07-28 18:47:23 | 731           | 6          | JENNIFER       | 2005-07-31 16:23:23 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10271       | 2005-08-01 03:13:39 | 3692          | 6          | JENNIFER       | 2005-08-07 23:40:39 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11023       | 2005-08-02 05:36:38 | 3617          | 6          | JENNIFER       | 2005-08-10 05:39:38 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11398       | 2005-08-02 18:55:15 | 3952          | 6          | JENNIFER       | 2005-08-10 19:50:15 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11591       | 2005-08-17 02:29:41 | 1670          | 6          | JENNIFER       | 2005-08-23 20:47:41 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11727       | 2005-08-17 08:12:20 | 98            | 6          | JENNIFER       | 2005-08-19 12:45:20 | 1           | Mike            | 2006-02-15 21:30:53  |
| 11853       | 2005-08-17 13:39:32 | 3888          | 6          | JENNIFER       | 2005-08-23 18:44:32 | 2           | Jon             | 2006-02-15 21:30:53  |
| 12254       | 2005-08-18 04:05:29 | 2858          | 6          | JENNIFER       | 2005-08-23 04:17:29 | 1           | Mike            | 2006-02-15 21:30:53  |
| 13451       | 2005-08-20 00:18:25 | 3837          | 6          | JENNIFER       | 2005-08-29 01:08:25 | 1           | Mike            | 2006-02-15 21:30:53  |
| 14329       | 2005-08-21 08:22:56 | 3544          | 6          | JENNIFER       | 2005-08-28 02:22:56 | 2           | Jon             | 2006-02-15 21:30:53  |
| 14377       | 2005-08-21 09:49:28 | 1325          | 6          | JENNIFER       | 2005-08-29 13:34:28 | 1           | Mike            | 2006-02-15 21:30:53  |
| 15509       | 2005-08-23 02:51:24 | 1291          | 6          | JENNIFER       | 2005-08-31 06:21:24 | 2           | Jon             | 2006-02-15 21:30:53  |
| 15603       | 2005-08-23 06:41:32 | 2565          | 6          | JENNIFER       | 2005-08-28 08:51:32 | 1           | Mike            | 2006-02-15 21:30:53  |
| 46          | 2005-05-25 06:04:08 | 3318          | 7          | MARIA          | 2005-06-02 08:18:08 | 2           | Jon             | 2006-02-15 21:30:53  |
| 117         | 2005-05-25 19:30:46 | 4278          | 7          | MARIA          | 2005-05-31 23:59:46 | 2           | Jon             | 2006-02-15 21:30:53  |
| 748         | 2005-05-29 09:27:00 | 2803          | 7          | MARIA          | 2005-06-03 04:25:00 | 1           | Mike            | 2006-02-15 21:30:53  |
| 975         | 2005-05-30 21:07:15 | 3109          | 7          | MARIA          | 2005-06-03 01:48:15 | 2           | Jon             | 2006-02-15 21:30:53  |
| 1063        | 2005-05-31 08:44:29 | 2484          | 7          | MARIA          | 2005-06-09 08:00:29 | 1           | Mike            | 2006-02-15 21:30:53  |
| 1810        | 2005-06-16 21:06:00 | 2368          | 7          | MARIA          | 2005-06-21 21:24:00 | 1           | Mike            | 2006-02-15 21:30:53  |
| 2250        | 2005-06-18 05:03:36 | 4042          | 7          | MARIA          | 2005-06-22 02:25:36 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2709        | 2005-06-19 14:00:26 | 2877          | 7          | MARIA          | 2005-06-23 14:56:26 | 2           | Jon             | 2006-02-15 21:30:53  |
| 2888        | 2005-06-20 01:50:56 | 468           | 7          | MARIA          | 2005-06-22 05:05:56 | 2           | Jon             | 2006-02-15 21:30:53  |
| 3007        | 2005-06-20 10:11:53 | 1950          | 7          | MARIA          | 2005-06-25 04:51:53 | 2           | Jon             | 2006-02-15 21:30:53  |
| 3639        | 2005-07-06 07:09:17 | 2812          | 7          | MARIA          | 2005-07-15 05:12:17 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4238        | 2005-07-07 13:22:20 | 3024          | 7          | MARIA          | 2005-07-10 07:44:20 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4787        | 2005-07-08 16:16:04 | 3929          | 7          | MARIA          | 2005-07-14 18:02:04 | 2           | Jon             | 2006-02-15 21:30:53  |
| 4856        | 2005-07-08 18:47:38 | 2441          | 7          | MARIA          | 2005-07-13 15:02:38 | 2           | Jon             | 2006-02-15 21:30:53  |
| 5441        | 2005-07-09 21:52:05 | 3913          | 7          | MARIA          | 2005-07-17 02:54:05 | 1           | Mike            | 2006-02-15 21:30:53  |
| 5921        | 2005-07-10 21:35:12 | 3920          | 7          | MARIA          | 2005-07-18 19:59:12 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6174        | 2005-07-11 10:36:28 | 3123          | 7          | MARIA          | 2005-07-18 16:19:28 | 2           | Jon             | 2006-02-15 21:30:53  |
| 6295        | 2005-07-11 17:30:58 | 1393          | 7          | MARIA          | 2005-07-15 15:50:58 | 1           | Mike            | 2006-02-15 21:30:53  |
| 6761        | 2005-07-12 15:17:42 | 3645          | 7          | MARIA          | 2005-07-18 17:59:42 | 2           | Jon             | 2006-02-15 21:30:53  |
| 8422        | 2005-07-29 07:02:55 | 3104          | 7          | MARIA          | 2005-08-03 12:35:55 | 1           | Mike            | 2006-02-15 21:30:53  |
| 9624        | 2005-07-31 04:30:03 | 3480          | 7          | MARIA          | 2005-08-06 09:13:03 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10330       | 2005-08-01 04:57:04 | 1580          | 7          | MARIA          | 2005-08-07 23:00:04 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10423       | 2005-08-01 08:19:53 | 739           | 7          | MARIA          | 2005-08-08 10:25:53 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10514       | 2005-08-01 11:39:26 | 1512          | 7          | MARIA          | 2005-08-03 07:53:26 | 2           | Jon             | 2006-02-15 21:30:53  |
| 10644       | 2005-08-01 15:52:00 | 4374          | 7          | MARIA          | 2005-08-08 16:08:00 | 1           | Mike            | 2006-02-15 21:30:53  |
| 10989       | 2005-08-02 04:40:54 | 2272          | 7          | MARIA          | 2005-08-09 03:39:54 | 2           | Jon             | 2006-02-15 21:30:53  |
| 11542       | 2005-08-17 00:51:32 | 2155          | 7          | MARIA          | 2005-08-24 20:29:32 | 2           | Jon             | 2006-02-15 21:30:53  |

Encontrar todas las películas que se encuentran en un almacén específico.

```sql
SELECT i.id_almacen, f.title
FROM inventario AS i
INNER JOIN pelicula AS p ON i.id_pelicula = p.id_pelicula
INNER JOIN film_text AS f ON p.id_pelicula = f.film_id;
```



| id_almacen | title                       |
| ---------- | --------------------------- |
| 1          | ACADEMY DINOSAUR            |
| 1          | ACADEMY DINOSAUR            |
| 1          | ACADEMY DINOSAUR            |
| 1          | ACADEMY DINOSAUR            |
| 2          | ACADEMY DINOSAUR            |
| 2          | ACADEMY DINOSAUR            |
| 2          | ACADEMY DINOSAUR            |
| 2          | ACADEMY DINOSAUR            |
| 2          | ACE GOLDFINGER              |
| 2          | ACE GOLDFINGER              |
| 2          | ACE GOLDFINGER              |
| 2          | ADAPTATION HOLES            |
| 2          | ADAPTATION HOLES            |
| 2          | ADAPTATION HOLES            |
| 2          | ADAPTATION HOLES            |
| 1          | AFFAIR PREJUDICE            |
| 1          | AFFAIR PREJUDICE            |
| 1          | AFFAIR PREJUDICE            |
| 1          | AFFAIR PREJUDICE            |
| 2          | AFFAIR PREJUDICE            |
| 2          | AFFAIR PREJUDICE            |
| 2          | AFFAIR PREJUDICE            |
| 2          | AFRICAN EGG                 |
| 2          | AFRICAN EGG                 |
| 2          | AFRICAN EGG                 |
| 1          | AGENT TRUMAN                |
| 1          | AGENT TRUMAN                |
| 1          | AGENT TRUMAN                |
| 2          | AGENT TRUMAN                |
| 2          | AGENT TRUMAN                |
| 2          | AGENT TRUMAN                |
| 1          | AIRPLANE SIERRA             |
| 1          | AIRPLANE SIERRA             |
| 2          | AIRPLANE SIERRA             |
| 2          | AIRPLANE SIERRA             |
| 2          | AIRPLANE SIERRA             |
| 2          | AIRPORT POLLOCK             |
| 2          | AIRPORT POLLOCK             |
| 2          | AIRPORT POLLOCK             |
| 2          | AIRPORT POLLOCK             |
| 1          | ALABAMA DEVIL               |
| 1          | ALABAMA DEVIL               |
| 1          | ALABAMA DEVIL               |
| 2          | ALABAMA DEVIL               |
| 2          | ALABAMA DEVIL               |
| 1          | ALADDIN CALENDAR            |
| 1          | ALADDIN CALENDAR            |
| 1          | ALADDIN CALENDAR            |
| 1          | ALADDIN CALENDAR            |
| 2          | ALADDIN CALENDAR            |
| 2          | ALADDIN CALENDAR            |
| 2          | ALADDIN CALENDAR            |
| 1          | ALAMO VIDEOTAPE             |
| 1          | ALAMO VIDEOTAPE             |
| 1          | ALAMO VIDEOTAPE             |
| 1          | ALAMO VIDEOTAPE             |
| 2          | ALAMO VIDEOTAPE             |
| 2          | ALAMO VIDEOTAPE             |
| 2          | ALAMO VIDEOTAPE             |
| 1          | ALASKA PHANTOM              |
| 1          | ALASKA PHANTOM              |
| 1          | ALASKA PHANTOM              |
| 2          | ALASKA PHANTOM              |
| 2          | ALASKA PHANTOM              |
| 2          | ALASKA PHANTOM              |
| 2          | ALASKA PHANTOM              |
| 2          | ALI FOREVER                 |
| 2          | ALI FOREVER                 |
| 2          | ALI FOREVER                 |
| 2          | ALI FOREVER                 |
| 1          | ALIEN CENTER                |
| 1          | ALIEN CENTER                |
| 2          | ALIEN CENTER                |
| 2          | ALIEN CENTER                |
| 2          | ALIEN CENTER                |
| 2          | ALIEN CENTER                |
| 1          | ALLEY EVOLUTION             |
| 1          | ALLEY EVOLUTION             |
| 2          | ALLEY EVOLUTION             |
| 2          | ALLEY EVOLUTION             |
| 1          | ALONE TRIP                  |
| 1          | ALONE TRIP                  |
| 1          | ALONE TRIP                  |
| 2          | ALONE TRIP                  |
| 2          | ALONE TRIP                  |
| 2          | ALONE TRIP                  |
| 1          | ALTER VICTORY               |
| 1          | ALTER VICTORY               |
| 1          | ALTER VICTORY               |
| 2          | ALTER VICTORY               |
| 2          | ALTER VICTORY               |
| 2          | ALTER VICTORY               |
| 1          | AMADEUS HOLY                |
| 1          | AMADEUS HOLY                |
| 1          | AMADEUS HOLY                |
| 1          | AMADEUS HOLY                |
| 2          | AMADEUS HOLY                |
| 2          | AMADEUS HOLY                |
| 1          | AMELIE HELLFIGHTERS         |
| 1          | AMELIE HELLFIGHTERS         |
| 1          | AMELIE HELLFIGHTERS         |
| 1          | AMERICAN CIRCUS             |
| 1          | AMERICAN CIRCUS             |
| 2          | AMERICAN CIRCUS             |
| 2          | AMERICAN CIRCUS             |
| 2          | AMERICAN CIRCUS             |
| 2          | AMERICAN CIRCUS             |
| 1          | AMISTAD MIDSUMMER           |
| 1          | AMISTAD MIDSUMMER           |
| 1          | AMISTAD MIDSUMMER           |
| 1          | AMISTAD MIDSUMMER           |
| 2          | AMISTAD MIDSUMMER           |
| 2          | AMISTAD MIDSUMMER           |
| 2          | AMISTAD MIDSUMMER           |
| 1          | ANACONDA CONFESSIONS        |
| 1          | ANACONDA CONFESSIONS        |
| 1          | ANACONDA CONFESSIONS        |
| 2          | ANACONDA CONFESSIONS        |
| 2          | ANACONDA CONFESSIONS        |
| 1          | ANALYZE HOOSIERS            |
| 1          | ANALYZE HOOSIERS            |
| 1          | ANALYZE HOOSIERS            |
| 1          | ANALYZE HOOSIERS            |
| 1          | ANGELS LIFE                 |
| 1          | ANGELS LIFE                 |
| 1          | ANGELS LIFE                 |
| 1          | ANGELS LIFE                 |
| 2          | ANGELS LIFE                 |
| 2          | ANGELS LIFE                 |
| 1          | ANNIE IDENTITY              |
| 1          | ANNIE IDENTITY              |
| 2          | ANNIE IDENTITY              |
| 2          | ANNIE IDENTITY              |
| 2          | ANNIE IDENTITY              |
| 1          | ANONYMOUS HUMAN             |
| 1          | ANONYMOUS HUMAN             |
| 1          | ANONYMOUS HUMAN             |
| 1          | ANONYMOUS HUMAN             |
| 1          | ANTHEM LUKE                 |
| 1          | ANTHEM LUKE                 |
| 1          | ANTHEM LUKE                 |
| 1          | ANTITRUST TOMATOES          |
| 1          | ANTITRUST TOMATOES          |
| 1          | ANYTHING SAVANNAH           |
| 1          | ANYTHING SAVANNAH           |
| 1          | APACHE DIVINE               |
| 1          | APACHE DIVINE               |
| 1          | APACHE DIVINE               |
| 1          | APACHE DIVINE               |
| 2          | APACHE DIVINE               |
| 2          | APACHE DIVINE               |
| 2          | APACHE DIVINE               |
| 2          | APACHE DIVINE               |
| 2          | APOCALYPSE FLAMINGOS        |
| 2          | APOCALYPSE FLAMINGOS        |
| 2          | ARABIA DOGMA                |
| 2          | ARABIA DOGMA                |
| 2          | ARABIA DOGMA                |
| 2          | ARABIA DOGMA                |
| 1          | ARACHNOPHOBIA ROLLERCOASTER |
| 1          | ARACHNOPHOBIA ROLLERCOASTER |
| 1          | ARACHNOPHOBIA ROLLERCOASTER |
| 1          | ARACHNOPHOBIA ROLLERCOASTER |
| 2          | ARACHNOPHOBIA ROLLERCOASTER |
| 2          | ARACHNOPHOBIA ROLLERCOASTER |
| 2          | ARACHNOPHOBIA ROLLERCOASTER |
| 1          | ARIZONA BANG                |
| 1          | ARIZONA BANG                |
| 1          | ARIZONA BANG                |
| 1          | ARIZONA BANG                |
| 2          | ARIZONA BANG                |
| 2          | ARIZONA BANG                |
| 2          | ARIZONA BANG                |
| 1          | ARMAGEDDON LOST             |
| 1          | ARMAGEDDON LOST             |
| 1          | ARMAGEDDON LOST             |
| 2          | ARMAGEDDON LOST             |
| 2          | ARMAGEDDON LOST             |
| 2          | ARMAGEDDON LOST             |
| 2          | ARMAGEDDON LOST             |
| 2          | ARMY FLINTSTONES            |
| 2          | ARMY FLINTSTONES            |
| 2          | ARMY FLINTSTONES            |
| 2          | ARMY FLINTSTONES            |
| 2          | ARTIST COLDBLOODED          |
| 2          | ARTIST COLDBLOODED          |
| 2          | ARTIST COLDBLOODED          |
| 2          | ARTIST COLDBLOODED          |
| 1          | ATLANTIS CAUSE              |
| 1          | ATLANTIS CAUSE              |
| 1          | ATLANTIS CAUSE              |
| 2          | ATLANTIS CAUSE              |
| 2          | ATLANTIS CAUSE              |
| 2          | ATLANTIS CAUSE              |
| 2          | ATLANTIS CAUSE              |
| 1          | ATTACKS HATE                |
| 1          | ATTACKS HATE                |
| 2          | ATTACKS HATE                |
| 2          | ATTACKS HATE                |
| 2          | ATTACKS HATE                |

Listar los nombres y apellidos de los empleados junto con las direcciones de los almacenes en los que trabajan.

```sql
SELECT e.nombre, e.apellidos, d.direccion
FROM empleado AS e
INNER JOIN almacen AS a ON e.id_almacen = a.id_almacen
INNER JOIN direccion AS d ON a.id_direccion = d.id_direccion;
```

| nombre | apellidos | direccion          |
| ------ | --------- | ------------------ |
| Mike   | Hillyer   | 28 MySQL Boulevard |
| Jon    | Stephens  | 28 MySQL Boulevard |
| Pepe   | Spilberg  | 28 MySQL Boulevard |
| Ada    | Byron     | 47 MySakila Drive  |
| Ringo  | Rooksby   | 47 MySakila Drive  |

Obtener una lista de pagos realizados, incluyendo el cliente, elempleado que registró el pago y el alquiler correspondiente.

```sql
SELECT pg.id_pago, pg.id_cliente, c.nombre AS nombre_cliente, pg.id_empleado, e.nombre AS nombre_empleado, pg.id_alquiler
FROM pago AS pg
INNER JOIN cliente AS c ON pg.id_cliente = c.id_cliente
INNER JOIN empleado AS e ON pg.id_empleado = e.id_empleado;
```

| id_pago | id_cliente | nombre    | id_empleado | nombre | id_alquiler |
| ------- | ---------- | --------- | ----------- | ------ | ----------- |
| 1       | 1          | MARY      | 1           | Mike   | 76          |
| 2       | 1          | MARY      | 1           | Mike   | 573         |
| 3       | 1          | MARY      | 1           | Mike   | 1185        |
| 4       | 1          | MARY      | 2           | Jon    | 1422        |
| 5       | 1          | MARY      | 2           | Jon    | 1476        |
| 6       | 1          | MARY      | 1           | Mike   | 1725        |
| 7       | 1          | MARY      | 1           | Mike   | 2308        |
| 8       | 1          | MARY      | 2           | Jon    | 2363        |
| 9       | 1          | MARY      | 1           | Mike   | 3284        |
| 10      | 1          | MARY      | 2           | Jon    | 4526        |
| 11      | 1          | MARY      | 1           | Mike   | 4611        |
| 12      | 1          | MARY      | 1           | Mike   | 5244        |
| 13      | 1          | MARY      | 1           | Mike   | 5326        |
| 14      | 1          | MARY      | 1           | Mike   | 6163        |
| 15      | 1          | MARY      | 2           | Jon    | 7273        |
| 16      | 1          | MARY      | 1           | Mike   | 7841        |
| 17      | 1          | MARY      | 2           | Jon    | 8033        |
| 18      | 1          | MARY      | 1           | Mike   | 8074        |
| 19      | 1          | MARY      | 2           | Jon    | 8116        |
| 20      | 1          | MARY      | 2           | Jon    | 8326        |
| 21      | 1          | MARY      | 2           | Jon    | 9571        |
| 22      | 1          | MARY      | 2           | Jon    | 10437       |
| 23      | 1          | MARY      | 2           | Jon    | 11299       |
| 24      | 1          | MARY      | 1           | Mike   | 11367       |
| 25      | 1          | MARY      | 2           | Jon    | 11824       |
| 26      | 1          | MARY      | 1           | Mike   | 12250       |
| 27      | 1          | MARY      | 2           | Jon    | 13068       |
| 28      | 1          | MARY      | 2           | Jon    | 13176       |
| 29      | 1          | MARY      | 1           | Mike   | 14762       |
| 30      | 1          | MARY      | 1           | Mike   | 14825       |
| 31      | 1          | MARY      | 2           | Jon    | 15298       |
| 32      | 1          | MARY      | 1           | Mike   | 15315       |
| 33      | 2          | PATRICIA  | 1           | Mike   | 320         |
| 34      | 2          | PATRICIA  | 1           | Mike   | 2128        |
| 35      | 2          | PATRICIA  | 1           | Mike   | 5636        |
| 36      | 2          | PATRICIA  | 1           | Mike   | 5755        |
| 37      | 2          | PATRICIA  | 2           | Jon    | 7346        |
| 38      | 2          | PATRICIA  | 1           | Mike   | 7376        |
| 39      | 2          | PATRICIA  | 2           | Jon    | 7459        |
| 40      | 2          | PATRICIA  | 2           | Jon    | 8230        |
| 41      | 2          | PATRICIA  | 1           | Mike   | 8598        |
| 42      | 2          | PATRICIA  | 2           | Jon    | 8705        |
| 43      | 2          | PATRICIA  | 1           | Mike   | 9031        |
| 44      | 2          | PATRICIA  | 2           | Jon    | 9236        |
| 45      | 2          | PATRICIA  | 2           | Jon    | 9248        |
| 46      | 2          | PATRICIA  | 2           | Jon    | 9296        |
| 47      | 2          | PATRICIA  | 2           | Jon    | 9465        |
| 48      | 2          | PATRICIA  | 1           | Mike   | 10136       |
| 49      | 2          | PATRICIA  | 1           | Mike   | 10466       |
| 50      | 2          | PATRICIA  | 1           | Mike   | 10918       |
| 51      | 2          | PATRICIA  | 1           | Mike   | 11087       |
| 52      | 2          | PATRICIA  | 1           | Mike   | 11177       |
| 53      | 2          | PATRICIA  | 2           | Jon    | 11256       |
| 54      | 2          | PATRICIA  | 1           | Mike   | 11614       |
| 55      | 2          | PATRICIA  | 1           | Mike   | 12963       |
| 56      | 2          | PATRICIA  | 1           | Mike   | 14475       |
| 57      | 2          | PATRICIA  | 2           | Jon    | 14743       |
| 58      | 2          | PATRICIA  | 2           | Jon    | 15145       |
| 59      | 2          | PATRICIA  | 2           | Jon    | 15907       |
| 60      | 3          | LINDA     | 1           | Mike   | 435         |
| 61      | 3          | LINDA     | 1           | Mike   | 830         |
| 62      | 3          | LINDA     | 1           | Mike   | 1546        |
| 63      | 3          | LINDA     | 1           | Mike   | 1726        |
| 64      | 3          | LINDA     | 2           | Jon    | 1911        |
| 65      | 3          | LINDA     | 1           | Mike   | 2628        |
| 66      | 3          | LINDA     | 1           | Mike   | 4180        |
| 67      | 3          | LINDA     | 1           | Mike   | 4725        |
| 68      | 3          | LINDA     | 1           | Mike   | 7096        |
| 69      | 3          | LINDA     | 2           | Jon    | 7503        |
| 70      | 3          | LINDA     | 2           | Jon    | 7703        |
| 71      | 3          | LINDA     | 2           | Jon    | 7724        |
| 72      | 3          | LINDA     | 1           | Mike   | 7911        |
| 73      | 3          | LINDA     | 2           | Jon    | 8086        |
| 74      | 3          | LINDA     | 1           | Mike   | 8545        |
| 75      | 3          | LINDA     | 1           | Mike   | 9226        |
| 76      | 3          | LINDA     | 2           | Jon    | 9443        |
| 77      | 3          | LINDA     | 1           | Mike   | 9595        |
| 78      | 3          | LINDA     | 2           | Jon    | 9816        |
| 79      | 3          | LINDA     | 2           | Jon    | 10597       |
| 80      | 3          | LINDA     | 2           | Jon    | 12556       |
| 81      | 3          | LINDA     | 1           | Mike   | 13403       |
| 82      | 3          | LINDA     | 2           | Jon    | 13610       |
| 83      | 3          | LINDA     | 2           | Jon    | 14699       |
| 84      | 3          | LINDA     | 2           | Jon    | 15038       |
| 85      | 3          | LINDA     | 1           | Mike   | 15619       |
| 86      | 4          | BARBARA   | 1           | Mike   | 1297        |
| 87      | 4          | BARBARA   | 1           | Mike   | 1633        |
| 88      | 4          | BARBARA   | 2           | Jon    | 1707        |
| 89      | 4          | BARBARA   | 2           | Jon    | 1735        |
| 90      | 4          | BARBARA   | 2           | Jon    | 2043        |
| 91      | 4          | BARBARA   | 1           | Mike   | 2642        |
| 92      | 4          | BARBARA   | 1           | Mike   | 7660        |
| 93      | 4          | BARBARA   | 2           | Jon    | 7718        |
| 94      | 4          | BARBARA   | 1           | Mike   | 8741        |
| 95      | 4          | BARBARA   | 1           | Mike   | 9100        |
| 96      | 4          | BARBARA   | 1           | Mike   | 9371        |
| 97      | 4          | BARBARA   | 2           | Jon    | 11069       |
| 98      | 4          | BARBARA   | 1           | Mike   | 11110       |
| 99      | 4          | BARBARA   | 2           | Jon    | 11529       |
| 100     | 4          | BARBARA   | 1           | Mike   | 12151       |
| 101     | 4          | BARBARA   | 2           | Jon    | 12294       |
| 102     | 4          | BARBARA   | 2           | Jon    | 12856       |
| 103     | 4          | BARBARA   | 1           | Mike   | 13704       |
| 104     | 4          | BARBARA   | 1           | Mike   | 13807       |
| 105     | 4          | BARBARA   | 2           | Jon    | 14225       |
| 106     | 4          | BARBARA   | 1           | Mike   | 15147       |
| 107     | 4          | BARBARA   | 2           | Jon    | 15635       |
| 108     | 5          | ELIZABETH | 1           | Mike   | 731         |
| 109     | 5          | ELIZABETH | 1           | Mike   | 1085        |
| 110     | 5          | ELIZABETH | 1           | Mike   | 1142        |
| 111     | 5          | ELIZABETH | 1           | Mike   | 1502        |
| 112     | 5          | ELIZABETH | 2           | Jon    | 1631        |
| 113     | 5          | ELIZABETH | 2           | Jon    | 2063        |
| 114     | 5          | ELIZABETH | 2           | Jon    | 2570        |
| 115     | 5          | ELIZABETH | 2           | Jon    | 3126        |
| 116     | 5          | ELIZABETH | 2           | Jon    | 3677        |
| 117     | 5          | ELIZABETH | 2           | Jon    | 4889        |
| 118     | 5          | ELIZABETH | 1           | Mike   | 5016        |
| 119     | 5          | ELIZABETH | 2           | Jon    | 5118        |
| 120     | 5          | ELIZABETH | 2           | Jon    | 5156        |
| 121     | 5          | ELIZABETH | 2           | Jon    | 5721        |
| 122     | 5          | ELIZABETH | 1           | Mike   | 6042        |
| 123     | 5          | ELIZABETH | 1           | Mike   | 6663        |
| 124     | 5          | ELIZABETH | 2           | Jon    | 6685        |
| 125     | 5          | ELIZABETH | 2           | Jon    | 7293        |
| 126     | 5          | ELIZABETH | 2           | Jon    | 7652        |
| 127     | 5          | ELIZABETH | 2           | Jon    | 7829        |
| 128     | 5          | ELIZABETH | 1           | Mike   | 8263        |
| 129     | 5          | ELIZABETH | 1           | Mike   | 8978        |
| 130     | 5          | ELIZABETH | 1           | Mike   | 9493        |
| 131     | 5          | ELIZABETH | 1           | Mike   | 9888        |
| 132     | 5          | ELIZABETH | 2           | Jon    | 10609       |
| 133     | 5          | ELIZABETH | 1           | Mike   | 10625       |
| 134     | 5          | ELIZABETH | 2           | Jon    | 11001       |
| 135     | 5          | ELIZABETH | 1           | Mike   | 11179       |
| 136     | 5          | ELIZABETH | 2           | Jon    | 11930       |
| 137     | 5          | ELIZABETH | 1           | Mike   | 12145       |
| 138     | 5          | ELIZABETH | 1           | Mike   | 12797       |
| 139     | 5          | ELIZABETH | 1           | Mike   | 13063       |
| 140     | 5          | ELIZABETH | 2           | Jon    | 13877       |
| 141     | 5          | ELIZABETH | 2           | Jon    | 14053       |
| 142     | 5          | ELIZABETH | 1           | Mike   | 14430       |
| 143     | 5          | ELIZABETH | 2           | Jon    | 14494       |
| 144     | 5          | ELIZABETH | 2           | Jon    | 15232       |
| 145     | 5          | ELIZABETH | 2           | Jon    | 13209       |
| 146     | 6          | JENNIFER  | 2           | Jon    | 57          |
| 147     | 6          | JENNIFER  | 1           | Mike   | 577         |
| 148     | 6          | JENNIFER  | 2           | Jon    | 916         |
| 149     | 6          | JENNIFER  | 1           | Mike   | 1575        |
| 150     | 6          | JENNIFER  | 2           | Jon    | 1841        |
| 151     | 6          | JENNIFER  | 1           | Mike   | 1966        |
| 152     | 6          | JENNIFER  | 1           | Mike   | 2345        |
| 153     | 6          | JENNIFER  | 2           | Jon    | 3983        |
| 154     | 6          | JENNIFER  | 2           | Jon    | 4278        |
| 155     | 6          | JENNIFER  | 1           | Mike   | 5553        |
| 156     | 6          | JENNIFER  | 2           | Jon    | 6211        |
| 157     | 6          | JENNIFER  | 1           | Mike   | 6248        |
| 158     | 6          | JENNIFER  | 2           | Jon    | 6686        |
| 159     | 6          | JENNIFER  | 2           | Jon    | 7099        |
| 160     | 6          | JENNIFER  | 2           | Jon    | 7136        |
| 161     | 6          | JENNIFER  | 1           | Mike   | 8101        |
| 162     | 6          | JENNIFER  | 1           | Mike   | 10271       |
| 163     | 6          | JENNIFER  | 1           | Mike   | 11023       |
| 164     | 6          | JENNIFER  | 1           | Mike   | 11398       |
| 165     | 6          | JENNIFER  | 1           | Mike   | 11591       |
| 166     | 6          | JENNIFER  | 1           | Mike   | 11727       |
| 167     | 6          | JENNIFER  | 1           | Mike   | 11853       |
| 168     | 6          | JENNIFER  | 2           | Jon    | 12254       |
| 169     | 6          | JENNIFER  | 2           | Jon    | 13451       |
| 170     | 6          | JENNIFER  | 1           | Mike   | 14329       |
| 171     | 6          | JENNIFER  | 1           | Mike   | 14377       |
| 172     | 6          | JENNIFER  | 1           | Mike   | 15509       |
| 173     | 6          | JENNIFER  | 2           | Jon    | 15603       |
| 174     | 7          | MARIA     | 2           | Jon    | 46          |
| 175     | 7          | MARIA     | 2           | Jon    | 117         |
| 176     | 7          | MARIA     | 2           | Jon    | 748         |
| 177     | 7          | MARIA     | 1           | Mike   | 975         |
| 178     | 7          | MARIA     | 1           | Mike   | 1063        |
| 179     | 7          | MARIA     | 2           | Jon    | 1810        |
| 180     | 7          | MARIA     | 1           | Mike   | 2250        |
| 181     | 7          | MARIA     | 1           | Mike   | 2709        |
| 182     | 7          | MARIA     | 1           | Mike   | 2888        |
| 183     | 7          | MARIA     | 1           | Mike   | 3007        |
| 184     | 7          | MARIA     | 2           | Jon    | 3639        |
| 185     | 7          | MARIA     | 2           | Jon    | 4238        |
| 186     | 7          | MARIA     | 2           | Jon    | 4787        |
| 187     | 7          | MARIA     | 1           | Mike   | 4856        |
| 188     | 7          | MARIA     | 1           | Mike   | 5441        |
| 189     | 7          | MARIA     | 1           | Mike   | 5921        |
| 190     | 7          | MARIA     | 1           | Mike   | 6174        |
| 191     | 7          | MARIA     | 1           | Mike   | 6295        |
| 192     | 7          | MARIA     | 2           | Jon    | 6761        |
| 193     | 7          | MARIA     | 2           | Jon    | 8422        |
| 194     | 7          | MARIA     | 2           | Jon    | 9624        |
| 195     | 7          | MARIA     | 2           | Jon    | 10330       |
| 196     | 7          | MARIA     | 1           | Mike   | 10423       |
| 197     | 7          | MARIA     | 1           | Mike   | 10514       |
| 198     | 7          | MARIA     | 2           | Jon    | 10644       |
| 199     | 7          | MARIA     | 2           | Jon    | 10989       |
| 200     | 7          | MARIA     | 2           | Jon    | 11542       |

Listar las películas y los idiomas en los que están disponibles.

```sql
SELECT f.title, f.description, i.nombre AS idioma
FROM pelicula AS p
INNER JOIN idioma AS i ON p.id_idioma = i.id_idioma
INNER JOIN film_text AS f ON p.id_pelicula = f.film_id;
```

| title                       | description                                                  | nombre  |
| --------------------------- | ------------------------------------------------------------ | ------- |
| ACADEMY DINOSAUR            | A Epic Drama of a Feminist And a Mad Scientist who must Battle a Teacher in The Canadian Rockies | English |
| ACE GOLDFINGER              | A Astounding Epistle of a Database Administrator And a Explorer who must Find a Car in Ancient China | English |
| ADAPTATION HOLES            | A Astounding Reflection of a Lumberjack And a Car who must Sink a Lumberjack in A Baloon Factory | English |
| AFFAIR PREJUDICE            | A Fanciful Documentary of a Frisbee And a Lumberjack who must Chase a Monkey in A Shark Tank | English |
| AFRICAN EGG                 | A Fast-Paced Documentary of a Pastry Chef And a Dentist who must Pursue a Forensic Psychologist in The Gulf of Mexico | English |
| AGENT TRUMAN                | A Intrepid Panorama of a Robot And a Boy who must Escape a Sumo Wrestler in Ancient China | English |
| AIRPLANE SIERRA             | A Touching Saga of a Hunter And a Butler who must Discover a Butler in A Jet Boat | English |
| AIRPORT POLLOCK             | A Epic Tale of a Moose And a Girl who must Confront a Monkey in Ancient India | English |
| ALABAMA DEVIL               | A Thoughtful Panorama of a Database Administrator And a Mad Scientist who must Outgun a Mad Scientist in A Jet Boat | English |
| ALADDIN CALENDAR            | A Action-Packed Tale of a Man And a Lumberjack who must Reach a Feminist in Ancient China | English |
| ALAMO VIDEOTAPE             | A Boring Epistle of a Butler And a Cat who must Fight a Pastry Chef in A MySQL Convention | English |
| ALASKA PHANTOM              | A Fanciful Saga of a Hunter And a Pastry Chef who must Vanquish a Boy in Australia | English |
| ALI FOREVER                 | A Action-Packed Drama of a Dentist And a Crocodile who must Battle a Feminist in The Canadian Rockies | English |
| ALICE FANTASIA              | A Emotional Drama of a A Shark And a Database Administrator who must Vanquish a Pioneer in Soviet Georgia | English |
| ALIEN CENTER                | A Brilliant Drama of a Cat And a Mad Scientist who must Battle a Feminist in A MySQL Convention | English |
| ALLEY EVOLUTION             | A Fast-Paced Drama of a Robot And a Composer who must Battle a Astronaut in New Orleans | English |
| ALONE TRIP                  | A Fast-Paced Character Study of a Composer And a Dog who must Outgun a Boat in An Abandoned Fun House | English |
| ALTER VICTORY               | A Thoughtful Drama of a Composer And a Feminist who must Meet a Secret Agent in The Canadian Rockies | English |
| AMADEUS HOLY                | A Emotional Display of a Pioneer And a Technical Writer who must Battle a Man in A Baloon | English |
| AMELIE HELLFIGHTERS         | A Boring Drama of a Woman And a Squirrel who must Conquer a Student in A Baloon | English |
| AMERICAN CIRCUS             | A Insightful Drama of a Girl And a Astronaut who must Face a Database Administrator in A Shark Tank | English |
| AMISTAD MIDSUMMER           | A Emotional Character Study of a Dentist And a Crocodile who must Meet a Sumo Wrestler in California | English |
| ANACONDA CONFESSIONS        | A Lacklusture Display of a Dentist And a Dentist who must Fight a Girl in Australia | English |
| ANALYZE HOOSIERS            | A Thoughtful Display of a Explorer And a Pastry Chef who must Overcome a Feminist in The Sahara Desert | English |
| ANGELS LIFE                 | A Thoughtful Display of a Woman And a Astronaut who must Battle a Robot in Berlin | English |
| ANNIE IDENTITY              | A Amazing Panorama of a Pastry Chef And a Boat who must Escape a Woman in An Abandoned Amusement Park | English |
| ANONYMOUS HUMAN             | A Amazing Reflection of a Database Administrator And a Astronaut who must Outrace a Database Administrator in A Shark Tank | English |
| ANTHEM LUKE                 | A Touching Panorama of a Waitress And a Woman who must Outrace a Dog in An Abandoned Amusement Park | English |
| ANTITRUST TOMATOES          | A Fateful Yarn of a Womanizer And a Feminist who must Succumb a Database Administrator in Ancient India | English |
| ANYTHING SAVANNAH           | A Epic Story of a Pastry Chef And a Woman who must Chase a Feminist in An Abandoned Fun House | English |
| APACHE DIVINE               | A Awe-Inspiring Reflection of a Pastry Chef And a Teacher who must Overcome a Sumo Wrestler in A U-Boat | English |
| APOCALYPSE FLAMINGOS        | A Astounding Story of a Dog And a Squirrel who must Defeat a Woman in An Abandoned Amusement Park | English |
| APOLLO TEEN                 | A Action-Packed Reflection of a Crocodile And a Explorer who must Find a Sumo Wrestler in An Abandoned Mine Shaft | English |
| ARABIA DOGMA                | A Touching Epistle of a Madman And a Mad Cow who must Defeat a Student in Nigeria | English |
| ARACHNOPHOBIA ROLLERCOASTER | A Action-Packed Reflection of a Pastry Chef And a Composer who must Discover a Mad Scientist in The First Manned Space Station | English |
| ARGONAUTS TOWN              | A Emotional Epistle of a Forensic Psychologist And a Butler who must Challenge a Waitress in An Abandoned Mine Shaft | English |
| ARIZONA BANG                | A Brilliant Panorama of a Mad Scientist And a Mad Cow who must Meet a Pioneer in A Monastery | English |
| ARK RIDGEMONT               | A Beautiful Yarn of a Pioneer And a Monkey who must Pursue a Explorer in The Sahara Desert | English |
| ARMAGEDDON LOST             | A Fast-Paced Tale of a Boat And a Teacher who must Succumb a Composer in An Abandoned Mine Shaft | English |
| ARMY FLINTSTONES            | A Boring Saga of a Database Administrator And a Womanizer who must Battle a Waitress in Nigeria | English |
| ARSENIC INDEPENDENCE        | A Fanciful Documentary of a Mad Cow And a Womanizer who must Find a Dentist in Berlin | English |
| ARTIST COLDBLOODED          | A Stunning Reflection of a Robot And a Moose who must Challenge a Woman in California | English |
| ATLANTIS CAUSE              | A Thrilling Yarn of a Feminist And a Hunter who must Fight a Technical Writer in A Shark Tank | English |
| ATTACKS HATE                | A Fast-Paced Panorama of a Technical Writer And a Mad Scientist who must Find a Feminist in An Abandoned Mine Shaft | English |
| ATTRACTION NEWTON           | A Astounding Panorama of a Composer And a Frisbee who must Reach a Husband in Ancient Japan | English |
| AUTUMN CROW                 | A Beautiful Tale of a Dentist And a Mad Cow who must Battle a Moose in The Sahara Desert | English |
| BABY HALL                   | A Boring Character Study of a A Shark And a Girl who must Outrace a Feminist in An Abandoned Mine Shaft | English |
| BACKLASH UNDEFEATED         | A Stunning Character Study of a Mad Scientist And a Mad Cow who must Kill a Car in A Monastery | English |
| BADMAN DAWN                 | A Emotional Panorama of a Pioneer And a Composer who must Escape a Mad Scientist in A Jet Boat | English |
| BAKED CLEOPATRA             | A Stunning Drama of a Forensic Psychologist And a Husband who must Overcome a Waitress in A Monastery | English |
| BALLOON HOMEWARD            | A Insightful Panorama of a Forensic Psychologist And a Mad Cow who must Build a Mad Scientist in The First Manned Space Station | English |
| BALLROOM MOCKINGBIRD        | A Thrilling Documentary of a Composer And a Monkey who must Find a Feminist in California | English |
| BANG KWAI                   | A Epic Drama of a Madman And a Cat who must Face a A Shark in An Abandoned Amusement Park | English |
| BANGER PINOCCHIO            | A Awe-Inspiring Drama of a Car And a Pastry Chef who must Chase a Crocodile in The First Manned Space Station | English |
| BARBARELLA STREETCAR        | A Awe-Inspiring Story of a Feminist And a Cat who must Conquer a Dog in A Monastery | English |
| BAREFOOT MANCHURIAN         | A Intrepid Story of a Cat And a Student who must Vanquish a Girl in An Abandoned Amusement Park | English |
| BASIC EASY                  | A Stunning Epistle of a Man And a Husband who must Reach a Mad Scientist in A Jet Boat | English |
| BEACH HEARTBREAKERS         | A Fateful Display of a Womanizer And a Mad Scientist who must Outgun a A Shark in Soviet Georgia | English |
| BEAR GRACELAND              | A Astounding Saga of a Dog And a Boy who must Kill a Teacher in The First Manned Space Station | English |
| BEAST HUNCHBACK             | A Awe-Inspiring Epistle of a Student And a Squirrel who must Defeat a Boy in Ancient China | English |
| BEAUTY GREASE               | A Fast-Paced Display of a Composer And a Moose who must Sink a Robot in An Abandoned Mine Shaft | English |
| BED HIGHBALL                | A Astounding Panorama of a Lumberjack And a Dog who must Redeem a Woman in An Abandoned Fun House | English |
| BEDAZZLED MARRIED           | A Astounding Character Study of a Madman And a Robot who must Meet a Mad Scientist in An Abandoned Fun House | English |
| BEETHOVEN EXORCIST          | A Epic Display of a Pioneer And a Student who must Challenge a Butler in The Gulf of Mexico | English |
| BEHAVIOR RUNAWAY            | A Unbelieveable Drama of a Student And a Husband who must Outrace a Sumo Wrestler in Berlin | English |
| BENEATH RUSH                | A Astounding Panorama of a Man And a Monkey who must Discover a Man in The First Manned Space Station | English |
| BERETS AGENT                | A Taut Saga of a Crocodile And a Boy who must Overcome a Technical Writer in Ancient China | English |
| BETRAYED REAR               | A Emotional Character Study of a Boat And a Pioneer who must Find a Explorer in A Shark Tank | English |
| BEVERLY OUTLAW              | A Fanciful Documentary of a Womanizer And a Boat who must Defeat a Madman in The First Manned Space Station | English |
| BIKINI BORROWERS            | A Astounding Drama of a Astronaut And a Cat who must Discover a Woman in The First Manned Space Station | English |
| BILKO ANONYMOUS             | A Emotional Reflection of a Teacher And a Man who must Meet a Cat in The First Manned Space Station | English |
| BILL OTHERS                 | A Stunning Saga of a Mad Scientist And a Forensic Psychologist who must Challenge a Squirrel in A MySQL Convention | English |
| BINGO TALENTED              | A Touching Tale of a Girl And a Crocodile who must Discover a Waitress in Nigeria | English |
| BIRCH ANTITRUST             | A Fanciful Panorama of a Husband And a Pioneer who must Outgun a Dog in A Baloon | English |
| BIRD INDEPENDENCE           | A Thrilling Documentary of a Car And a Student who must Sink a Hunter in The Canadian Rockies | English |
| BIRDCAGE CASPER             | A Fast-Paced Saga of a Frisbee And a Astronaut who must Overcome a Feminist in Ancient India | English |
| BIRDS PERDITION             | A Boring Story of a Womanizer And a Pioneer who must Face a Dog in California | English |
| BLACKOUT PRIVATE            | A Intrepid Yarn of a Pastry Chef And a Mad Scientist who must Challenge a Secret Agent in Ancient Japan | English |
| BLADE POLISH                | A Thoughtful Character Study of a Frisbee And a Pastry Chef who must Fight a Dentist in The First Manned Space Station | English |
| BLANKET BEVERLY             | A Emotional Documentary of a Student And a Girl who must Build a Boat in Nigeria | English |
| BLINDNESS GUN               | A Touching Drama of a Robot And a Dentist who must Meet a Hunter in A Jet Boat | English |
| BLOOD ARGONAUTS             | A Boring Drama of a Explorer And a Man who must Kill a Lumberjack in A Manhattan Penthouse | English |
| BLUES INSTINCT              | A Insightful Documentary of a Boat And a Composer who must Meet a Forensic Psychologist in An Abandoned Fun House | English |
| BOILED DARES                | A Awe-Inspiring Story of a Waitress And a Dog who must Discover a Dentist in Ancient Japan | English |
| BONNIE HOLOCAUST            | A Fast-Paced Story of a Crocodile And a Robot who must Find a Moose in Ancient Japan | English |
| BOOGIE AMELIE               | A Lacklusture Character Study of a Husband And a Sumo Wrestler who must Succumb a Technical Writer in The Gulf of Mexico | English |
| BOONDOCK BALLROOM           | A Fateful Panorama of a Crocodile And a Boy who must Defeat a Monkey in The Gulf of Mexico | English |
| BORN SPINAL                 | A Touching Epistle of a Frisbee And a Husband who must Pursue a Student in Nigeria | English |
| BORROWERS BEDAZZLED         | A Brilliant Epistle of a Teacher And a Sumo Wrestler who must Defeat a Man in An Abandoned Fun House | English |
| BOULEVARD MOB               | A Fateful Epistle of a Moose And a Monkey who must Confront a Lumberjack in Ancient China | English |
| BOUND CHEAPER               | A Thrilling Panorama of a Database Administrator And a Astronaut who must Challenge a Lumberjack in A Baloon | English |
| BOWFINGER GABLES            | A Fast-Paced Yarn of a Waitress And a Composer who must Outgun a Dentist in California | English |
| BRANNIGAN SUNRISE           | A Amazing Epistle of a Moose And a Crocodile who must Outrace a Dog in Berlin | English |
| BRAVEHEART HUMAN            | A Insightful Story of a Dog And a Pastry Chef who must Battle a Girl in Berlin | English |
| BREAKFAST GOLDFINGER        | A Beautiful Reflection of a Student And a Student who must Fight a Moose in Berlin | English |
| BREAKING HOME               | A Beautiful Display of a Secret Agent And a Monkey who must Battle a Sumo Wrestler in An Abandoned Mine Shaft | English |
| BRIDE INTRIGUE              | A Epic Tale of a Robot And a Monkey who must Vanquish a Man in New Orleans | English |
| BRIGHT ENCOUNTERS           | A Fateful Yarn of a Lumberjack And a Feminist who must Conquer a Student in A Jet Boat | English |
| BRINGING HYSTERICAL         | A Fateful Saga of a A Shark And a Technical Writer who must Find a Woman in A Jet Boat | English |
| BROOKLYN DESERT             | A Beautiful Drama of a Dentist And a Composer who must Battle a Sumo Wrestler in The First Manned Space Station | English |
| BROTHERHOOD BLANKET         | A Fateful Character Study of a Butler And a Technical Writer who must Sink a Astronaut in Ancient Japan | English |
| BUBBLE GROSSE               | A Awe-Inspiring Panorama of a Crocodile And a Moose who must Confront a Girl in A Baloon | English |
| BUCKET BROTHERHOOD          | A Amazing Display of a Girl And a Womanizer who must Succumb a Lumberjack in A Baloon Factory | English |
| BUGSY SONG                  | A Awe-Inspiring Character Study of a Secret Agent And a Boat who must Find a Squirrel in The First Manned Space Station | English |
| BULL SHAWSHANK              | A Fanciful Drama of a Moose And a Squirrel who must Conquer a Pioneer in The Canadian Rockies | English |
| BULWORTH COMMANDMENTS       | A Amazing Display of a Mad Cow And a Pioneer who must Redeem a Sumo Wrestler in The Outback | English |
| BUNCH MINDS                 | A Emotional Story of a Feminist And a Feminist who must Escape a Pastry Chef in A MySQL Convention | English |
| BUTCH PANTHER               | A Lacklusture Yarn of a Feminist And a Database Administrator who must Face a Hunter in New Orleans | English |
| BUTTERFLY CHOCOLAT          | A Fateful Story of a Girl And a Composer who must Conquer a Husband in A Shark Tank | English |
| CABIN FLASH                 | A Stunning Epistle of a Boat And a Man who must Challenge a A Shark in A Baloon Factory | English |
| CADDYSHACK JEDI             | A Awe-Inspiring Epistle of a Woman And a Madman who must Fight a Robot in Soviet Georgia | English |
| CALENDAR GUNFIGHT           | A Thrilling Drama of a Frisbee And a Lumberjack who must Sink a Man in Nigeria | English |
| CALIFORNIA BIRDS            | A Thrilling Yarn of a Database Administrator And a Robot who must Battle a Database Administrator in Ancient India | English |
| CAMELOT VACATION            | A Touching Character Study of a Woman And a Waitress who must Battle a Pastry Chef in A MySQL Convention | English |
| CAMPUS REMEMBER             | A Astounding Drama of a Crocodile And a Mad Cow who must Build a Robot in A Jet Boat | English |
| CANDIDATE PERDITION         | A Brilliant Epistle of a Composer And a Database Administrator who must Vanquish a Mad Scientist in The First Manned Space Station | English |
| CANDLES GRAPES              | A Fanciful Character Study of a Monkey And a Explorer who must Build a Astronaut in An Abandoned Fun House | English |
| CANYON STOCK                | A Thoughtful Reflection of a Waitress And a Feminist who must Escape a Squirrel in A Manhattan Penthouse | English |
| CAPER MOTIONS               | A Fateful Saga of a Moose And a Car who must Pursue a Woman in A MySQL Convention | English |
| CARIBBEAN LIBERTY           | A Fanciful Tale of a Pioneer And a Technical Writer who must Outgun a Pioneer in A Shark Tank | English |
| CAROL TEXAS                 | A Astounding Character Study of a Composer And a Student who must Overcome a Composer in A Monastery | English |
| CARRIE BUNCH                | A Amazing Epistle of a Student And a Astronaut who must Discover a Frisbee in The Canadian Rockies | English |
| CASABLANCA SUPER            | A Amazing Panorama of a Crocodile And a Forensic Psychologist who must Pursue a Secret Agent in The First Manned Space Station | English |
| CASPER DRAGONFLY            | A Intrepid Documentary of a Boat And a Crocodile who must Chase a Robot in The Sahara Desert | English |
| CASSIDY WYOMING             | A Intrepid Drama of a Frisbee And a Hunter who must Kill a Secret Agent in New Orleans | English |
| CASUALTIES ENCINO           | A Insightful Yarn of a A Shark And a Pastry Chef who must Face a Boy in A Monastery | English |
| CAT CONEHEADS               | A Fast-Paced Panorama of a Girl And a A Shark who must Confront a Boy in Ancient India | English |
| CATCH AMISTAD               | A Boring Reflection of a Lumberjack And a Feminist who must Discover a Woman in Nigeria | English |
| CAUSE DATE                  | A Taut Tale of a Explorer And a Pastry Chef who must Conquer a Hunter in A MySQL Convention | English |
| CELEBRITY HORN              | A Amazing Documentary of a Secret Agent And a Astronaut who must Vanquish a Hunter in A Shark Tank | English |
| CENTER DINOSAUR             | A Beautiful Character Study of a Sumo Wrestler And a Dentist who must Find a Dog in California | English |
| CHAINSAW UPTOWN             | A Beautiful Documentary of a Boy And a Robot who must Discover a Squirrel in Australia | English |
| CHAMBER ITALIAN             | A Fateful Reflection of a Moose And a Husband who must Overcome a Monkey in Nigeria | English |
| CHAMPION FLATLINERS         | A Amazing Story of a Mad Cow And a Dog who must Kill a Husband in A Monastery | English |
| CHANCE RESURRECTION         | A Astounding Story of a Forensic Psychologist And a Forensic Psychologist who must Overcome a Moose in Ancient China | English |
| CHAPLIN LICENSE             | A Boring Drama of a Dog And a Forensic Psychologist who must Outrace a Explorer in Ancient India | English |
| CHARADE DUFFEL              | A Action-Packed Display of a Man And a Waitress who must Build a Dog in A MySQL Convention | English |
| CHARIOTS CONSPIRACY         | A Unbelieveable Epistle of a Robot And a Husband who must Chase a Robot in The First Manned Space Station | English |
| CHASING FIGHT               | A Astounding Saga of a Technical Writer And a Butler who must Battle a Butler in A Shark Tank | English |
| CHEAPER CLYDE               | A Emotional Character Study of a Pioneer And a Girl who must Discover a Dog in Ancient Japan | English |
| CHICAGO NORTH               | A Fateful Yarn of a Mad Cow And a Waitress who must Battle a Student in California | English |
| CHICKEN HELLFIGHTERS        | A Emotional Drama of a Dog And a Explorer who must Outrace a Technical Writer in Australia | English |
| CHILL LUCK                  | A Lacklusture Epistle of a Boat And a Technical Writer who must Fight a A Shark in The Canadian Rockies | English |
| CHINATOWN GLADIATOR         | A Brilliant Panorama of a Technical Writer And a Lumberjack who must Escape a Butler in Ancient India | English |
| CHISUM BEHAVIOR             | A Epic Documentary of a Sumo Wrestler And a Butler who must Kill a Car in Ancient India | English |
| CHITTY LOCK                 | A Boring Epistle of a Boat And a Database Administrator who must Kill a Sumo Wrestler in The First Manned Space Station | English |
| CHOCOLAT HARRY              | A Action-Packed Epistle of a Dentist And a Moose who must Meet a Mad Cow in Ancient Japan | English |
| CHOCOLATE DUCK              | A Unbelieveable Story of a Mad Scientist And a Technical Writer who must Discover a Composer in Ancient China | English |
| CHRISTMAS MOONSHINE         | A Action-Packed Epistle of a Feminist And a Astronaut who must Conquer a Boat in A Manhattan Penthouse | English |
| CIDER DESIRE                | A Stunning Character Study of a Composer And a Mad Cow who must Succumb a Cat in Soviet Georgia | English |
| CINCINATTI WHISPERER        | A Brilliant Saga of a Pastry Chef And a Hunter who must Confront a Butler in Berlin | English |
| CIRCUS YOUTH                | A Thoughtful Drama of a Pastry Chef And a Dentist who must Pursue a Girl in A Baloon | English |
| CITIZEN SHREK               | A Fanciful Character Study of a Technical Writer And a Husband who must Redeem a Robot in The Outback | English |
| CLASH FREDDY                | A Amazing Yarn of a Composer And a Squirrel who must Escape a Astronaut in Australia | English |
| CLEOPATRA DEVIL             | A Fanciful Documentary of a Crocodile And a Technical Writer who must Fight a A Shark in A Baloon | English |
| CLERKS ANGELS               | A Thrilling Display of a Sumo Wrestler And a Girl who must Confront a Man in A Baloon | English |
| CLOCKWORK PARADISE          | A Insightful Documentary of a Technical Writer And a Feminist who must Challenge a Cat in A Baloon | English |
| CLONES PINOCCHIO            | A Amazing Drama of a Car And a Robot who must Pursue a Dentist in New Orleans | English |
| CLOSER BANG                 | A Unbelieveable Panorama of a Frisbee And a Hunter who must Vanquish a Monkey in Ancient India | English |
| CLUB GRAFFITI               | A Epic Tale of a Pioneer And a Hunter who must Escape a Girl in A U-Boat | English |
| CLUE GRAIL                  | A Taut Tale of a Butler And a Mad Scientist who must Build a Crocodile in Ancient China | English |
| CLUELESS BUCKET             | A Taut Tale of a Car And a Pioneer who must Conquer a Sumo Wrestler in An Abandoned Fun House | English |
| CLYDE THEORY                | A Beautiful Yarn of a Astronaut And a Frisbee who must Overcome a Explorer in A Jet Boat | English |
| COAST RAINBOW               | A Astounding Documentary of a Mad Cow And a Pioneer who must Challenge a Butler in The Sahara Desert | English |
| COLDBLOODED DARLING         | A Brilliant Panorama of a Dentist And a Moose who must Find a Student in The Gulf of Mexico | English |
| COLOR PHILADELPHIA          | A Thoughtful Panorama of a Car And a Crocodile who must Sink a Monkey in The Sahara Desert | English |
| COMA HEAD                   | A Awe-Inspiring Drama of a Boy And a Frisbee who must Escape a Pastry Chef in California | English |
| COMANCHEROS ENEMY           | A Boring Saga of a Lumberjack And a Monkey who must Find a Monkey in The Gulf of Mexico | English |
| COMFORTS RUSH               | A Unbelieveable Panorama of a Pioneer And a Husband who must Meet a Mad Cow in An Abandoned Mine Shaft | English |
| COMMAND DARLING             | A Awe-Inspiring Tale of a Forensic Psychologist And a Woman who must Challenge a Database Administrator in Ancient Japan | English |
| COMMANDMENTS EXPRESS        | A Fanciful Saga of a Student And a Mad Scientist who must Battle a Hunter in An Abandoned Mine Shaft | English |
| CONEHEADS SMOOCHY           | A Touching Story of a Womanizer And a Composer who must Pursue a Husband in Nigeria | English |
| CONFESSIONS MAGUIRE         | A Insightful Story of a Car And a Boy who must Battle a Technical Writer in A Baloon | English |
| CONFIDENTIAL INTERVIEW      | A Stunning Reflection of a Cat And a Woman who must Find a Astronaut in Ancient Japan | English |
| CONFUSED CANDLES            | A Stunning Epistle of a Cat And a Forensic Psychologist who must Confront a Pioneer in A Baloon | English |
| CONGENIALITY QUEST          | A Touching Documentary of a Cat And a Pastry Chef who must Find a Lumberjack in A Baloon | English |
| CONNECTICUT TRAMP           | A Unbelieveable Drama of a Crocodile And a Mad Cow who must Reach a Dentist in A Shark Tank | English |
| CONNECTION MICROCOSMOS      | A Fateful Documentary of a Crocodile And a Husband who must Face a Husband in The First Manned Space Station | English |
| CONQUERER NUTS              | A Taut Drama of a Mad Scientist And a Man who must Escape a Pioneer in An Abandoned Mine Shaft | English |
| CONSPIRACY SPIRIT           | A Awe-Inspiring Story of a Student And a Frisbee who must Conquer a Crocodile in An Abandoned Mine Shaft | English |
| CONTACT ANONYMOUS           | A Insightful Display of a A Shark And a Monkey who must Face a Database Administrator in Ancient India | English |
| CONTROL ANTHEM              | A Fateful Documentary of a Robot And a Student who must Battle a Cat in A Monastery | English |
| CONVERSATION DOWNHILL       | A Taut Character Study of a Husband And a Waitress who must Sink a Squirrel in A MySQL Convention | English |
| CORE SUIT                   | A Unbelieveable Tale of a Car And a Explorer who must Confront a Boat in A Manhattan Penthouse | English |
| COWBOY DOOM                 | A Astounding Drama of a Boy And a Lumberjack who must Fight a Butler in A Baloon | English |
| CRAFT OUTFIELD              | A Lacklusture Display of a Explorer And a Hunter who must Succumb a Database Administrator in A Baloon Factory | English |
| CRANES RESERVOIR            | A Fanciful Documentary of a Teacher And a Dog who must Outgun a Forensic Psychologist in A Baloon Factory | English |
| CRAZY HOME                  | A Fanciful Panorama of a Boy And a Woman who must Vanquish a Database Administrator in The Outback | English |
| CREATURES SHAKESPEARE       | A Emotional Drama of a Womanizer And a Squirrel who must Vanquish a Crocodile in Ancient India | English |
| CREEPERS KANE               | A Awe-Inspiring Reflection of a Squirrel And a Boat who must Outrace a Car in A Jet Boat | English |
| CROOKED FROGMEN             | A Unbelieveable Drama of a Hunter And a Database Administrator who must Battle a Crocodile in An Abandoned Amusement Park | English |
| CROSSING DIVORCE            | A Beautiful Documentary of a Dog And a Robot who must Redeem a Womanizer in Berlin | English |
| CROSSROADS CASUALTIES       | A Intrepid Documentary of a Sumo Wrestler And a Astronaut who must Battle a Composer in The Outback | English |
| CROW GREASE                 | A Awe-Inspiring Documentary of a Woman And a Husband who must Sink a Database Administrator in The First Manned Space Station | English |
| CROWDS TELEMARK             | A Intrepid Documentary of a Astronaut And a Forensic Psychologist who must Find a Frisbee in An Abandoned Fun House | English |
| CRUELTY UNFORGIVEN          | A Brilliant Tale of a Car And a Moose who must Battle a Dentist in Nigeria | English |
| CRUSADE HONEY               | A Fast-Paced Reflection of a Explorer And a Butler who must Battle a Madman in An Abandoned Amusement Park | English |
| CRYSTAL BREAKING            | A Fast-Paced Character Study of a Feminist And a Explorer who must Face a Pastry Chef in Ancient Japan | English |
| CUPBOARD SINNERS            | A Emotional Reflection of a Frisbee And a Boat who must Reach a Pastry Chef in An Abandoned Amusement Park | English |
| CURTAIN VIDEOTAPE           | A Boring Reflection of a Dentist And a Mad Cow who must Chase a Secret Agent in A Shark Tank | English |

Encontrar todos los empleados y los almacenes que gestionan.

```sql
SELECT e.nombre, e.apellidos, e.id_almacen
FROM empleado AS e
INNER JOIN almacen AS a ON e.id_empleado = a.id_empleado_jefe;
```

| nombre | apellidos | id_almacen |
| ------ | --------- | ---------- |
| Jon    | Stephens  | 2          |
| Ringo  | Rooksby   | 1          |

Obtener los títulos de las películas que nunca han sido alquiladas.

```sql
SELECT f.title
FROM film_text AS f
INNER JOIN pelicula AS p ON f.film_id = p.id_pelicula
INNER JOIN inventario AS i ON p.id_pelicula = i.id_pelicula
LEFT JOIN alquiler AS a ON i.id_inventario = a.id_inventario
WHERE a.id_alquiler IS NULL;
```

| title            |
| ---------------- |
| ACADEMY DINOSAUR |

Listar los empleados que trabajan en el mismo almacén que el empleado con id_empleado = 1.

```sql
SELECT id_empleado, nombre, apellidos
FROM empleado
WHERE id_almacen IN (SELECT id_almacen FROM empleado WHERE id_empleado = 1);
```

| id_empleado | nombre | apellidos |
| ----------- | ------ | --------- |
| 1           | Mike   | Hillyer   |
| 2           | Jon    | Stephens  |
| 3           | Pepe   | Spilberg  |

Encontrar el nombre de las ciudades que no tienen ningún cliente registrado.

```sql
SELECT DISTINCT c.nombre AS ciudad
FROM ciudad AS c
INNER JOIN direccion AS d ON c.id_ciudad = d.id_ciudad
LEFT JOIN cliente AS cl ON d.id_direccion = cl.id_direccion
WHERE cl.id_cliente IS NULL;
```

| nombre     |
| ---------- |
| Lethbridge |
| Woodridge  |



Obtener los nombres y apellidos de los actores que han participado en más de 10 películas.(having)

```sql
SELECT a.nombre, a.apellidos, COUNT(pa.id_pelicula) AS cantidad_pelicula
FROM actor AS a
INNER JOIN pelicula_actor AS pa ON a.id_actor = pa.id_actor
GROUP BY a.nombre, a.apellidos 
HAVING cantidad_pelicula > 10;
```

| nombre      | apellidos    | cantidad_pelicula |
| ----------- | ------------ | ----------------- |
| PENELOPE    | GUINESS      | 19                |
| NICK        | WAHLBERG     | 25                |
| ED          | CHASE        | 22                |
| JENNIFER    | DAVIS        | 22                |
| JOHNNY      | LOLLOBRIGIDA | 29                |
| BETTE       | NICHOLSON    | 20                |
| GRACE       | MOSTEL       | 30                |
| MATTHEW     | JOHANSSON    | 20                |
| JOE         | SWANK        | 25                |
| CHRISTIAN   | GABLE        | 22                |
| ZERO        | CAGE         | 25                |
| KARL        | BERRY        | 31                |
| UMA         | WOOD         | 35                |
| VIVIEN      | BERGEN       | 30                |
| CUBA        | OLIVIER      | 28                |
| FRED        | COSTNER      | 27                |
| HELEN       | VOIGHT       | 32                |
| DAN         | TORN         | 22                |
| BOB         | FAWCETT      | 25                |
| LUCILLE     | TRACY        | 30                |
| KIRSTEN     | PALTROW      | 27                |
| ELVIS       | MARX         | 26                |
| SANDRA      | KILMER       | 37                |
| CAMERON     | STREEP       | 24                |
| KEVIN       | BLOOM        | 21                |
| RIP         | CRAWFORD     | 33                |
| JULIA       | MCQUEEN      | 33                |
| WOODY       | HOFFMAN      | 31                |
| ALEC        | WAYNE        | 29                |
| SANDRA      | PECK         | 19                |
| SISSY       | SOBIESKI     | 18                |
| TIM         | HACKMAN      | 23                |
| MILLA       | PECK         | 24                |
| AUDREY      | OLIVIER      | 25                |
| JUDY        | DEAN         | 15                |
| BURT        | DUKAKIS      | 29                |
| VAL         | BOLGER       | 35                |
| TOM         | MCKELLEN     | 25                |
| GOLDIE      | BRODY        | 28                |
| JOHNNY      | CAGE         | 29                |
| JODIE       | DEGENERES    | 29                |
| TOM         | MIRANDA      | 27                |
| KIRK        | JOVOVICH     | 26                |
| NICK        | STALLONE     | 30                |
| REESE       | KILMER       | 32                |
| PARKER      | GOLDBERG     | 24                |
| JULIA       | BARRYMORE    | 24                |
| FRANCES     | DAY-LEWIS    | 26                |
| ANNE        | CRONYN       | 27                |
| NATALIE     | HOPKINS      | 32                |
| GARY        | PHOENIX      | 25                |
| CARMEN      | HUNT         | 26                |
| MENA        | TEMPLE       | 30                |
| PENELOPE    | PINKETT      | 25                |
| FAY         | KILMER       | 20                |
| DAN         | HARRIS       | 28                |
| JUDE        | CRUISE       | 30                |
| CHRISTIAN   | AKROYD       | 32                |
| DUSTIN      | TAUTOU       | 27                |
| HENRY       | BERRY        | 35                |
| CHRISTIAN   | NEESON       | 25                |
| JAYNE       | NEESON       | 29                |
| CAMERON     | WRAY         | 19                |
| RAY         | JOHANSSON    | 30                |
| ANGELA      | HUDSON       | 34                |
| MARY        | TANDY        | 31                |
| JESSICA     | BAILEY       | 23                |
| RIP         | WINSLET      | 30                |
| KENNETH     | PALTROW      | 21                |
| MICHELLE    | MCCONAUGHEY  | 23                |
| ADAM        | GRANT        | 18                |
| SEAN        | WILLIAMS     | 26                |
| GARY        | PENN         | 26                |
| MILLA       | KEITEL       | 28                |
| BURT        | POSEY        | 24                |
| ANGELINA    | ASTAIRE      | 31                |
| CARY        | MCCONAUGHEY  | 24                |
| GROUCHO     | SINATRA      | 26                |
| MAE         | HOFFMAN      | 28                |
| RALPH       | CRUZ         | 28                |
| SCARLETT    | DAMON        | 36                |
| WOODY       | JOLIE        | 31                |
| BEN         | WILLIS       | 33                |
| JAMES       | PITT         | 31                |
| MINNIE      | ZELLWEGER    | 31                |
| GREG        | CHAPLIN      | 27                |
| SPENCER     | PECK         | 21                |
| KENNETH     | PESCI        | 20                |
| CHARLIZE    | DENCH        | 24                |
| SEAN        | GUINESS      | 33                |
| CHRISTOPHER | BERRY        | 20                |
| KIRSTEN     | AKROYD       | 34                |
| ELLEN       | PRESLEY      | 25                |
| KENNETH     | TORN         | 33                |
| DARYL       | WAHLBERG     | 31                |
| GENE        | WILLIS       | 23                |
| MEG         | HAWKE        | 27                |
| CHRIS       | BRIDGES      | 27                |
| JIM         | MOSTEL       | 26                |
| SPENCER     | DEPP         | 24                |
| SUSAN       | DAVIS        | 54                |
| WALTER      | TORN         | 41                |
| MATTHEW     | LEIGH        | 30                |
| PENELOPE    | CRONYN       | 31                |
| SIDNEY      | CROWE        | 34                |
| GROUCHO     | DUNST        | 35                |
| GINA        | DEGENERES    | 42                |
| WARREN      | NOLTE        | 34                |
| SYLVESTER   | DERN         | 22                |
| CAMERON     | ZELLWEGER    | 33                |
| RUSSELL     | BACALL       | 25                |
| MORGAN      | HOPKINS      | 27                |
| MORGAN      | MCDORMAND    | 25                |
| HARRISON    | BALE         | 28                |
| DAN         | STREEP       | 24                |
| RENEE       | TRACY        | 33                |
| CUBA        | ALLEN        | 25                |
| WARREN      | JACKMAN      | 32                |
| PENELOPE    | MONROE       | 27                |
| LIZA        | BERGMAN      | 25                |
| SALMA       | NOLTE        | 25                |
| JULIANNE    | DENCH        | 32                |
| SCARLETT    | BENING       | 26                |
| ALBERT      | NOLTE        | 31                |
| FRANCES     | TOMEI        | 23                |
| KEVIN       | GARLAND      | 33                |
| CATE        | MCQUEEN      | 30                |
| DARYL       | CRAWFORD     | 30                |
| GRETA       | KEITEL       | 27                |
| JANE        | JACKMAN      | 25                |
| ADAM        | HOPPER       | 22                |
| RICHARD     | PENN         | 30                |
| GENE        | HOPKINS      | 22                |
| RITA        | REYNOLDS     | 20                |
| ED          | MANSFIELD    | 32                |
| MORGAN      | WILLIAMS     | 27                |
| LUCILLE     | DEE          | 24                |
| EWAN        | GOODING      | 33                |
| WHOOPI      | HURT         | 32                |
| CATE        | HARRIS       | 28                |
| JADA        | RYDER        | 31                |
| RIVER       | DEAN         | 31                |
| ANGELA      | WITHERSPOON  | 35                |
| KIM         | ALLEN        | 28                |
| ALBERT      | JOHANSSON    | 33                |
| FAY         | WINSLET      | 31                |
| EMILY       | DEE          | 14                |
| RUSSELL     | TEMPLE       | 31                |
| JAYNE       | NOLTE        | 34                |
| GEOFFREY    | HESTON       | 26                |
| BEN         | HARRIS       | 23                |
| MINNIE      | KILMER       | 20                |
| MERYL       | GIBSON       | 28                |
| IAN         | TANDY        | 31                |
| FAY         | WOOD         | 22                |
| GRETA       | MALDEN       | 32                |
| VIVIEN      | BASINGER     | 35                |
| LAURA       | BRODY        | 26                |
| CHRIS       | DEPP         | 20                |
| HARVEY      | HOPE         | 32                |
| OPRAH       | KILMER       | 25                |
| CHRISTOPHER | WEST         | 21                |
| HUMPHREY    | WILLIS       | 26                |
| AL          | GARLAND      | 26                |
| NICK        | DEGENERES    | 22                |
| LAURENCE    | BULLOCK      | 26                |
| WILL        | WILSON       | 31                |
| KENNETH     | HOFFMAN      | 29                |
| MENA        | HOPPER       | 24                |
| OLYMPIA     | PFEIFFER     | 28                |
| GROUCHO     | WILLIAMS     | 25                |
| ALAN        | DREYFUSS     | 27                |
| MICHAEL     | BENING       | 24                |
| WILLIAM     | HACKMAN      | 27                |
| JON         | CHASE        | 29                |
| GENE        | MCKELLEN     | 27                |
| LISA        | MONROE       | 23                |
| ED          | GUINESS      | 29                |
| JEFF        | SILVERSTONE  | 25                |
| MATTHEW     | CARREY       | 39                |
| DEBBIE      | AKROYD       | 24                |
| RUSSELL     | CLOSE        | 19                |
| HUMPHREY    | GARLAND      | 29                |
| MICHAEL     | BOLGER       | 30                |
| JULIA       | ZELLWEGER    | 16                |
| RENEE       | BALL         | 33                |
| ROCK        | DUKAKIS      | 30                |
| CUBA        | BIRCH        | 24                |
| AUDREY      | BAILEY       | 27                |
| GREGORY     | GOODING      | 30                |
| JOHN        | SUVARI       | 29                |
| BURT        | TEMPLE       | 23                |
| MERYL       | ALLEN        | 22                |
| JAYNE       | SILVERSTONE  | 27                |
| BELA        | WALKEN       | 30                |
| REESE       | WEST         | 33                |
| MARY        | KEITEL       | 40                |
| JULIA       | FAWCETT      | 15                |
| THORA       | TEMPLE       | 20                |

Encontrar los nombres y apellidos de los clientes que han realizado un pago mayor a 100.

```sql
SELECT c.nombre, c.apellidos, SUM(pg.total) AS total_pago
FROM cliente AS c
INNER JOIN pago AS pg ON c.id_cliente = pg.id_cliente
GROUP BY c.nombre, c.apellidos
HAVING total_pago > 100;
```

| nombre      | apellidos    | total_pago |
| ----------- | ------------ | ---------- |
| MARY        | SMITH        | 118.68     |
| PATRICIA    | JOHNSON      | 128.73     |
| LINDA       | WILLIAMS     | 135.74     |
| ELIZABETH   | BROWN        | 144.62     |
| MARIA       | MILLER       | 151.67     |
| LISA        | ANDERSON     | 106.76     |
| NANCY       | THOMAS       | 103.72     |
| KAREN       | JACKSON      | 131.73     |
| BETTY       | WHITE        | 117.72     |
| HELEN       | HARRIS       | 134.68     |
| SANDRA      | MARTIN       | 120.71     |
| RUTH        | MARTINEZ     | 125.76     |
| SHARON      | ROBINSON     | 115.70     |
| MICHELLE    | CLARK        | 155.65     |
| LAURA       | RODRIGUEZ    | 113.78     |
| SARAH       | LEWIS        | 119.70     |
| DEBORAH     | WALKER       | 115.71     |
| JESSICA     | HALL         | 152.66     |
| SHIRLEY     | ALLEN        | 126.69     |
| CYNTHIA     | YOUNG        | 111.68     |
| ANGELA      | HERNANDEZ    | 140.64     |
| MELISSA     | KING         | 123.66     |
| BRENDA      | WRIGHT       | 104.74     |
| AMY         | LOPEZ        | 127.71     |
| VIRGINIA    | GREEN        | 129.68     |
| MARTHA      | GONZALEZ     | 127.66     |
| DEBRA       | NELSON       | 141.71     |
| AMANDA      | CARTER       | 110.73     |
| STEPHANIE   | MITCHELL     | 118.75     |
| CAROLYN     | PEREZ        | 117.70     |
| MARIE       | TURNER       | 114.74     |
| JANET       | PHILLIPS     | 127.73     |
| CATHERINE   | CAMPBELL     | 142.66     |
| FRANCES     | PARKER       | 108.78     |
| JOYCE       | EDWARDS      | 130.72     |
| DIANE       | COLLINS      | 169.65     |
| ALICE       | STEWART      | 138.67     |
| JULIE       | SANCHEZ      | 107.71     |
| HEATHER     | MORRIS       | 115.70     |
| TERESA      | ROGERS       | 128.71     |
| DORIS       | REED         | 100.78     |
| GLORIA      | COOK         | 135.70     |
| EVELYN      | MORGAN       | 114.72     |
| JEAN        | BELL         | 115.73     |
| CHERYL      | MURPHY       | 133.73     |
| ASHLEY      | RICHARDSON   | 112.75     |
| JUDITH      | COX          | 100.67     |
| ROSE        | HOWARD       | 103.78     |
| JANICE      | WARD         | 144.66     |
| KATHY       | JAMES        | 129.70     |
| DENISE      | KELLY        | 103.73     |
| TAMMY       | SANDERS      | 155.59     |
| JANE        | BENNETT      | 100.72     |
| LORI        | WOOD         | 141.69     |
| MARILYN     | ROSS         | 137.70     |
| KATHRYN     | COLEMAN      | 130.74     |
| LOUISE      | JENKINS      | 101.75     |
| SARA        | PERRY        | 141.67     |
| JACQUELINE  | LONG         | 148.67     |
| WANDA       | PATTERSON    | 145.70     |
| JULIA       | FLORES       | 134.68     |
| RUBY        | WASHINGTON   | 110.72     |
| LOIS        | BUTLER       | 113.65     |
| TINA        | SIMMONS      | 133.72     |
| DIANA       | ALEXANDER    | 105.73     |
| LILLIAN     | GRIFFIN      | 106.75     |
| ROBIN       | HAYES        | 102.76     |
| CRYSTAL     | FORD         | 137.67     |
| GLADYS      | HAMILTON     | 146.69     |
| DAWN        | SULLIVAN     | 120.74     |
| CONNIE      | WALLACE      | 100.77     |
| FLORENCE    | WOODS        | 126.70     |
| TRACY       | COLE         | 132.70     |
| EDNA        | WEST         | 107.74     |
| ROSA        | REYNOLDS     | 133.70     |
| CINDY       | FISHER       | 113.71     |
| GRACE       | ELLIS        | 139.67     |
| VICTORIA    | GIBSON       | 111.73     |
| SHERRY      | MARSHALL     | 153.66     |
| SYLVIA      | ORTIZ        | 143.68     |
| JOSEPHINE   | GOMEZ        | 109.74     |
| THELMA      | MURRAY       | 126.68     |
| SHANNON     | FREEMAN      | 100.76     |
| ETHEL       | WEBB         | 135.68     |
| ELLEN       | SIMPSON      | 117.72     |
| ELAINE      | STEVENS      | 107.76     |
| MARJORIE    | TUCKER       | 127.68     |
| CARRIE      | PORTER       | 124.66     |
| MONICA      | HICKS        | 128.70     |
| JUANITA     | MASON        | 110.70     |
| RHONDA      | KENNEDY      | 194.61     |
| HAZEL       | WARREN       | 110.66     |
| AMBER       | DIXON        | 113.73     |
| DEBBIE      | REYES        | 130.68     |
| CLARA       | SHAW         | 195.58     |
| LUCILLE     | HOLMES       | 108.72     |
| JAMIE       | RICE         | 139.71     |
| JOANNE      | ROBERTSON    | 127.66     |
| ELEANOR     | HUNT         | 216.54     |
| VALERIE     | BLACK        | 121.74     |
| DANIELLE    | DANIELS      | 105.75     |
| MICHELE     | GRANT        | 130.70     |
| GAIL        | KNIGHT       | 109.75     |
| BERTHA      | FERGUSON     | 101.75     |
| DARLENE     | ROSE         | 113.69     |
| VERONICA    | STONE        | 126.68     |
| ERIN        | DUNN         | 106.73     |
| GERALDINE   | PERKINS      | 112.70     |
| CATHY       | SPENCER      | 122.71     |
| LYNN        | PAYNE        | 123.72     |
| SALLY       | PIERCE       | 119.68     |
| REGINA      | BERRY        | 135.66     |
| BEATRICE    | ARNOLD       | 119.74     |
| DOLORES     | WAGNER       | 114.74     |
| BERNICE     | WILLIS       | 145.67     |
| AUDREY      | RAY          | 119.71     |
| JUNE        | CARROLL      | 173.63     |
| MARION      | SNYDER       | 194.61     |
| DANA        | HART         | 133.71     |
| ANA         | BRADLEY      | 174.66     |
| HOLLY       | FOX          | 114.69     |
| BRITTANY    | RILEY        | 159.72     |
| YOLANDA     | WEAVER       | 110.73     |
| KATIE       | ELLIOTT      | 109.75     |
| ALMA        | AUSTIN       | 151.65     |
| SUE         | PETERS       | 154.60     |
| ELSIE       | KELLEY       | 141.63     |
| BETH        | FRANKLIN     | 103.75     |
| JEANNE      | LAWSON       | 136.73     |
| VICKI       | FIELDS       | 108.75     |
| CARLA       | GUTIERREZ    | 103.74     |
| ROSEMARY    | SCHMIDT      | 147.65     |
| TERRI       | VASQUEZ      | 126.73     |
| GERTRUDE    | CASTILLO     | 137.66     |
| TONYA       | CHAPMAN      | 161.68     |
| ELLA        | OLIVER       | 137.69     |
| STACEY      | MONTGOMERY   | 151.66     |
| GINA        | WILLIAMSON   | 111.72     |
| KRISTIN     | JOHNSTON     | 116.69     |
| WILLIE      | HOWELL       | 101.74     |
| CHARLENE    | ALVAREZ      | 114.73     |
| BESSIE      | MORRISON     | 132.72     |
| ARLENE      | HARVEY       | 120.74     |
| JOY         | GEORGE       | 124.67     |
| GEORGIA     | JACOBS       | 110.74     |
| CLAUDIA     | FULLER       | 111.74     |
| MARCIA      | DEAN         | 175.58     |
| TANYA       | GILBERT      | 144.67     |
| MINNIE      | ROMERO       | 142.66     |
| MARLENE     | WELCH        | 117.74     |
| HEIDI       | LARSON       | 122.66     |
| GLENDA      | FRAZIER      | 140.68     |
| VIOLA       | HANSON       | 129.68     |
| COURTNEY    | DAY          | 132.68     |
| MARIAN      | MENDOZA      | 107.77     |
| STELLA      | MORENO       | 104.78     |
| DORA        | MEDINA       | 107.77     |
| VICKIE      | BREWER       | 120.69     |
| TERRY       | CARLSON      | 127.71     |
| MAXINE      | SILVA        | 116.68     |
| MABEL       | HOLLAND      | 112.70     |
| MARSHA      | DOUGLAS      | 151.63     |
| MYRTLE      | FLEMING      | 110.76     |
| LENA        | JENSEN       | 170.67     |
| CHRISTY     | VARGAS       | 122.69     |
| DEANNA      | BYRD         | 107.74     |
| PATSY       | DAVIDSON     | 119.72     |
| HILDA       | HOPKINS      | 122.71     |
| JENNIE      | TERRY        | 133.71     |
| NORA        | HERRERA      | 118.72     |
| MARGIE      | WADE         | 159.64     |
| NINA        | SOTO         | 123.71     |
| CASSANDRA   | WALTERS      | 129.70     |
| LEAH        | CURTIS       | 104.75     |
| PRISCILLA   | LOWE         | 157.65     |
| NAOMI       | JENNINGS     | 152.65     |
| CAROLE      | BARNETT      | 108.70     |
| BRANDY      | GRAVES       | 122.72     |
| OLGA        | JIMENEZ      | 144.68     |
| DIANNE      | SHELTON      | 135.69     |
| TRACEY      | BARRETT      | 118.73     |
| JENNY       | CASTRO       | 103.73     |
| SONIA       | GREGORY      | 126.72     |
| MIRIAM      | MCKINNEY     | 135.74     |
| VELMA       | LUCAS        | 117.73     |
| BECKY       | MILES        | 115.71     |
| VIOLET      | RODRIQUEZ    | 142.70     |
| KRISTINA    | CHAMBERS     | 109.72     |
| MISTY       | LAMBERT      | 118.73     |
| MAE         | FLETCHER     | 158.69     |
| SHELLY      | WATTS        | 113.74     |
| DAISY       | BATES        | 162.62     |
| RAMONA      | HALE         | 129.70     |
| SHERRI      | RHODES       | 128.67     |
| ERIKA       | PENA         | 101.74     |
| JAMES       | GANNON       | 131.70     |
| JOHN        | FARNSWORTH   | 137.69     |
| MICHAEL     | SILVERMAN    | 127.71     |
| WILLIAM     | SATTERFIELD  | 100.74     |
| DAVID       | ROYAL        | 115.74     |
| RICHARD     | MCCRARY      | 109.75     |
| CHARLES     | KOWALSKI     | 138.68     |
| JOSEPH      | JOY          | 134.70     |
| THOMAS      | GRIGSBY      | 105.75     |
| CHRISTOPHER | GRECO        | 147.69     |
| PAUL        | TROUT        | 120.77     |
| MARK        | RINEHART     | 104.74     |
| GEORGE      | LINTON       | 131.67     |
| STEVEN      | CURLEY       | 132.71     |
| EDWARD      | BAUGH        | 114.72     |
| RONALD      | WEINER       | 132.70     |
| KEVIN       | SCHULER      | 116.78     |
| JASON       | MORRISSEY    | 128.72     |
| MATTHEW     | MAHAN        | 114.69     |
| GARY        | COY          | 103.75     |
| LARRY       | THRASHER     | 112.74     |
| FRANK       | WAGGONER     | 127.68     |
| ERIC        | ROBERT       | 122.73     |
| STEPHEN     | QUALLS       | 118.72     |
| ANDREW      | PURDY        | 109.73     |
| RAYMOND     | MCWHORTER    | 135.70     |
| JOSHUA      | MARK         | 119.70     |
| JERRY       | JORDON       | 143.71     |
| DENNIS      | GILMAN       | 114.72     |
| WALTER      | PERRYMAN     | 127.70     |
| PATRICK     | NEWSOM       | 119.69     |
| PETER       | MENARD       | 106.77     |
| HAROLD      | MARTINO      | 130.68     |
| DOUGLAS     | GRAF         | 114.75     |
| CARL        | ARTIS        | 106.77     |
| ARTHUR      | SIMPKINS     | 155.68     |
| RYAN        | SALISBURY    | 142.70     |
| ROGER       | QUINTANILLA  | 146.64     |
| JOE         | GILLILAND    | 138.71     |
| JUSTIN      | NGO          | 129.64     |
| GERALD      | FULTZ        | 121.70     |
| WILLIE      | MARKHAM      | 101.75     |
| RALPH       | MADRIGAL     | 150.66     |
| LAWRENCE    | LAWTON       | 100.69     |
| NICHOLAS    | BARFIELD     | 145.68     |
| ROY         | WHITING      | 143.71     |
| BRUCE       | SCHWARZ      | 103.77     |
| BRANDON     | HUEY         | 152.63     |
| ADAM        | GOOCH        | 101.78     |
| HARRY       | ARCE         | 157.65     |
| BILLY       | POULIN       | 149.65     |
| STEVE       | MACKENZIE    | 158.66     |
| LOUIS       | LEONE        | 161.65     |
| JEREMY      | HURTADO      | 103.72     |
| AARON       | SELBY        | 110.76     |
| RANDY       | GAITHER      | 110.72     |
| CARLOS      | COUGHLIN     | 106.77     |
| RUSSELL     | BRINSON      | 136.64     |
| BOBBY       | BOUDREAU     | 106.65     |
| MARTIN      | BALES        | 103.73     |
| PHILLIP     | HOLM         | 101.74     |
| TODD        | TAN          | 117.71     |
| JESSE       | SCHILLING    | 101.74     |
| CRAIG       | MORRELL      | 124.70     |
| ALAN        | KAHN         | 124.74     |
| SHAWN       | HEATON       | 152.67     |
| CLARENCE    | GAMEZ        | 104.70     |
| PHILIP      | CAUSEY       | 121.69     |
| EARL        | SHANKS       | 111.73     |
| JIMMY       | SCHRADER     | 105.71     |
| BRYAN       | HARDISON     | 124.72     |
| MIKE        | WAY          | 166.65     |
| STANLEY     | SCROGGINS    | 139.70     |
| LEONARD     | SCHOFIELD    | 109.68     |
| NATHAN      | RUNYON       | 122.68     |
| DALE        | RATCLIFF     | 112.73     |
| MANUEL      | MURRELL      | 116.70     |
| RODNEY      | MOELLER      | 104.77     |
| CURTIS      | IRBY         | 167.62     |
| VINCENT     | RALSTON      | 105.75     |
| JEFFERY     | PINSON       | 121.69     |
| TRAVIS      | ESTEP        | 110.75     |
| JEFF        | EAST         | 107.70     |
| LEE         | HAWKS        | 119.73     |
| ALFRED      | CASILLAS     | 120.74     |
| KYLE        | SPURLOCK     | 110.70     |
| FRANCIS     | SIKES        | 104.74     |
| BRADLEY     | MOTLEY       | 126.73     |
| JESUS       | MCCARTNEY    | 114.76     |
| FREDERICK   | ISBELL       | 105.79     |
| EDWIN       | BURK         | 116.77     |
| DON         | BONE         | 133.75     |
| EDDIE       | TOMLIN       | 128.73     |
| TROY        | QUIGLEY      | 144.70     |
| BARRY       | LOVELACE     | 134.67     |
| ALEXANDER   | FENNELL      | 151.64     |
| MARIO       | CHEATHAM     | 112.72     |
| LEROY       | BUSTAMANTE   | 118.68     |
| MARCUS      | HIDALGO      | 115.70     |
| MICHEAL     | FORMAN       | 102.74     |
| THEODORE    | CULP         | 116.69     |
| CLIFFORD    | BOWENS       | 113.71     |
| MIGUEL      | BETANCOURT   | 135.71     |
| JIM         | REA          | 128.67     |
| TOM         | MILNER       | 107.68     |
| CALVIN      | MARTEL       | 111.77     |
| ALEX        | GRESHAM      | 151.67     |
| RONNIE      | RICKETTS     | 100.75     |
| BILL        | GAVIN        | 114.72     |
| TOMMY       | COLLAZO      | 186.62     |
| LEON        | BOSTIC       | 109.75     |
| WARREN      | SHERROD      | 159.67     |
| LEO         | EBERT        | 104.77     |
| ALVIN       | DELOACH      | 139.71     |
| TIM         | CARY         | 175.61     |
| WESLEY      | BULL         | 177.60     |
| GORDON      | ALLARD       | 160.68     |
| DEAN        | SAUER        | 109.73     |
| GREG        | ROBINS       | 141.70     |
| JORGE       | OLIVARES     | 134.66     |
| DUSTIN      | GILLETTE     | 100.74     |
| PEDRO       | CHESTNUT     | 103.76     |
| DAN         | PAINE        | 109.78     |
| ZACHARY     | HITE         | 146.69     |
| COREY       | HAUSER       | 101.78     |
| HERMAN      | DEVORE       | 115.71     |
| MAURICE     | CRAWLEY      | 138.71     |
| ROBERTO     | VU           | 139.70     |
| CLYDE       | TOBIAS       | 115.71     |
| GLEN        | TALBERT      | 113.74     |
| HECTOR      | POINDEXTER   | 119.74     |
| SAM         | MCDUFFIE     | 117.76     |
| RICK        | MATTOX       | 124.73     |
| BRENT       | HARKINS      | 112.77     |
| RAMON       | CHOATE       | 140.69     |
| CHARLIE     | BESS         | 120.74     |
| GILBERT     | SLEDGE       | 129.72     |
| MARC        | OUTLAW       | 123.70     |
| REGINALD    | KINDER       | 115.72     |
| BRETT       | CORNWELL     | 138.66     |
| ANGEL       | BARCLAY      | 115.68     |
| NATHANIEL   | ADAM         | 133.72     |
| LESLIE      | SEWARD       | 152.65     |
| MILTON      | HOWLAND      | 127.75     |
| RAUL        | FORTIER      | 100.80     |
| BEN         | EASTER       | 122.74     |
| CECIL       | VINES        | 115.74     |
| DUANE       | TUBBS        | 148.69     |
| ANDRE       | RAPP         | 126.72     |
| BRAD        | MCCURDY      | 105.75     |
| GABRIEL     | HARDER       | 111.74     |
| RON         | DELUCA       | 103.77     |
| MITCHELL    | WESTMORELAND | 134.68     |
| ARNOLD      | HAVENS       | 167.67     |
| KARL        | SEAL         | 221.55     |
| CLAUDE      | HERZOG       | 111.75     |
| ERIK        | GUILLEN      | 118.71     |
| JAMIE       | WAUGH        | 118.75     |
| NEIL        | RENNER       | 152.68     |
| JESSIE      | MILAM        | 141.67     |
| JAVIER      | ELROD        | 135.68     |
| FERNANDO    | CHURCHILL    | 117.75     |
| CLINTON     | BUFORD       | 103.75     |
| TED         | BREAUX       | 117.71     |
| TYRONE      | ASHER        | 112.76     |
| DARREN      | WINDHAM      | 108.76     |
| KELLY       | KNOTT        | 107.74     |
| GUY         | BROWNLEE     | 159.68     |
| MAX         | PITT         | 107.76     |
| DWAYNE      | OLVERA       | 101.78     |
| JIMMIE      | EGGLESTON    | 135.72     |
| EVERETT     | BANDA        | 110.72     |
| JORDAN      | ARCHULETA    | 132.70     |
| WALLACE     | SLONE        | 109.75     |
| KEN         | PREWITT      | 110.71     |
| JAIME       | NETTLES      | 126.71     |
| CASEY       | MENA         | 141.66     |
| DAVE        | GARDINER     | 134.68     |
| JOHNNIE     | CHISHOLM     | 121.76     |
| SIDNEY      | BURLESON     | 108.75     |
| BYRON       | BOX          | 120.71     |
| JULIAN      | VEST         | 109.72     |
| ISAAC       | OGLESBY      | 126.71     |
| MORRIS      | MCCARTER     | 139.66     |
| CLIFTON     | MALCOLM      | 118.72     |
| DARYL       | LARUE        | 111.73     |
| VIRGIL      | WOFFORD      | 107.73     |
| ANDY        | VANHORN      | 113.75     |
| MARSHALL    | THORN        | 117.77     |
| SALVADOR    | TEEL         | 129.70     |
| PERRY       | SWAFFORD     | 117.76     |
| SERGIO      | STANFIELD    | 108.74     |
| MARION      | OCAMPO       | 115.71     |
| TRACY       | HERRMANN     | 129.72     |
| SETH        | HANNON       | 112.75     |
| KENT        | ARSENAULT    | 134.73     |
| TERRANCE    | ROUSH        | 111.71     |
| RENE        | MCALISTER    | 113.74     |
| EDUARDO     | HIATT        | 130.73     |
| TERRENCE    | GUNDERSON    | 117.70     |

Listar los títulos de las películas lanzadas en el mismo año que la película con id_pelicula = 2.

```sql
SELECT f.title, p.anyo_lanzamiento
FROM pelicula AS p
INNER JOIN film_text AS f ON p.id_pelicula = f.film_id
WHERE anyo_lanzamiento IN (SELECT anyo_lanzamiento FROM pelicula WHERE id_pelicula = 2);
```

| title                       | anyo_lanzamiento |
| --------------------------- | ---------------- |
| ACADEMY DINOSAUR            | 2006             |
| ACE GOLDFINGER              | 2006             |
| ADAPTATION HOLES            | 2006             |
| AFFAIR PREJUDICE            | 2006             |
| AFRICAN EGG                 | 2006             |
| AGENT TRUMAN                | 2006             |
| AIRPLANE SIERRA             | 2006             |
| AIRPORT POLLOCK             | 2006             |
| ALABAMA DEVIL               | 2006             |
| ALADDIN CALENDAR            | 2006             |
| ALAMO VIDEOTAPE             | 2006             |
| ALASKA PHANTOM              | 2006             |
| ALI FOREVER                 | 2006             |
| ALICE FANTASIA              | 2006             |
| ALIEN CENTER                | 2006             |
| ALLEY EVOLUTION             | 2006             |
| ALONE TRIP                  | 2006             |
| ALTER VICTORY               | 2006             |
| AMADEUS HOLY                | 2006             |
| AMELIE HELLFIGHTERS         | 2006             |
| AMERICAN CIRCUS             | 2006             |
| AMISTAD MIDSUMMER           | 2006             |
| ANACONDA CONFESSIONS        | 2006             |
| ANALYZE HOOSIERS            | 2006             |
| ANGELS LIFE                 | 2006             |
| ANNIE IDENTITY              | 2006             |
| ANONYMOUS HUMAN             | 2006             |
| ANTHEM LUKE                 | 2006             |
| ANTITRUST TOMATOES          | 2006             |
| ANYTHING SAVANNAH           | 2006             |
| APACHE DIVINE               | 2006             |
| APOCALYPSE FLAMINGOS        | 2006             |
| APOLLO TEEN                 | 2006             |
| ARABIA DOGMA                | 2006             |
| ARACHNOPHOBIA ROLLERCOASTER | 2006             |
| ARGONAUTS TOWN              | 2006             |
| ARIZONA BANG                | 2006             |
| ARK RIDGEMONT               | 2006             |
| ARMAGEDDON LOST             | 2006             |
| ARMY FLINTSTONES            | 2006             |
| ARSENIC INDEPENDENCE        | 2006             |
| ARTIST COLDBLOODED          | 2006             |
| ATLANTIS CAUSE              | 2006             |
| ATTACKS HATE                | 2006             |
| ATTRACTION NEWTON           | 2006             |
| AUTUMN CROW                 | 2006             |
| BABY HALL                   | 2006             |
| BACKLASH UNDEFEATED         | 2006             |
| BADMAN DAWN                 | 2006             |
| BAKED CLEOPATRA             | 2006             |
| BALLOON HOMEWARD            | 2006             |
| BALLROOM MOCKINGBIRD        | 2006             |
| BANG KWAI                   | 2006             |
| BANGER PINOCCHIO            | 2006             |
| BARBARELLA STREETCAR        | 2006             |
| BAREFOOT MANCHURIAN         | 2006             |
| BASIC EASY                  | 2006             |
| BEACH HEARTBREAKERS         | 2006             |
| BEAR GRACELAND              | 2006             |
| BEAST HUNCHBACK             | 2006             |
| BEAUTY GREASE               | 2006             |
| BED HIGHBALL                | 2006             |
| BEDAZZLED MARRIED           | 2006             |
| BEETHOVEN EXORCIST          | 2006             |
| BEHAVIOR RUNAWAY            | 2006             |
| BENEATH RUSH                | 2006             |
| BERETS AGENT                | 2006             |
| BETRAYED REAR               | 2006             |
| BEVERLY OUTLAW              | 2006             |
| BIKINI BORROWERS            | 2006             |
| BILKO ANONYMOUS             | 2006             |
| BILL OTHERS                 | 2006             |
| BINGO TALENTED              | 2006             |
| BIRCH ANTITRUST             | 2006             |
| BIRD INDEPENDENCE           | 2006             |
| BIRDCAGE CASPER             | 2006             |
| BIRDS PERDITION             | 2006             |
| BLACKOUT PRIVATE            | 2006             |
| BLADE POLISH                | 2006             |
| BLANKET BEVERLY             | 2006             |
| BLINDNESS GUN               | 2006             |
| BLOOD ARGONAUTS             | 2006             |
| BLUES INSTINCT              | 2006             |
| BOILED DARES                | 2006             |
| BONNIE HOLOCAUST            | 2006             |
| BOOGIE AMELIE               | 2006             |
| BOONDOCK BALLROOM           | 2006             |
| BORN SPINAL                 | 2006             |
| BORROWERS BEDAZZLED         | 2006             |
| BOULEVARD MOB               | 2006             |
| BOUND CHEAPER               | 2006             |
| BOWFINGER GABLES            | 2006             |
| BRANNIGAN SUNRISE           | 2006             |
| BRAVEHEART HUMAN            | 2006             |
| BREAKFAST GOLDFINGER        | 2006             |
| BREAKING HOME               | 2006             |
| BRIDE INTRIGUE              | 2006             |
| BRIGHT ENCOUNTERS           | 2006             |
| BRINGING HYSTERICAL         | 2006             |
| BROOKLYN DESERT             | 2006             |
| BROTHERHOOD BLANKET         | 2006             |
| BUBBLE GROSSE               | 2006             |
| BUCKET BROTHERHOOD          | 2006             |
| BUGSY SONG                  | 2006             |
| BULL SHAWSHANK              | 2006             |
| BULWORTH COMMANDMENTS       | 2006             |
| BUNCH MINDS                 | 2006             |
| BUTCH PANTHER               | 2006             |
| BUTTERFLY CHOCOLAT          | 2006             |
| CABIN FLASH                 | 2006             |
| CADDYSHACK JEDI             | 2006             |
| CALENDAR GUNFIGHT           | 2006             |
| CALIFORNIA BIRDS            | 2006             |
| CAMELOT VACATION            | 2006             |
| CAMPUS REMEMBER             | 2006             |
| CANDIDATE PERDITION         | 2006             |
| CANDLES GRAPES              | 2006             |
| CANYON STOCK                | 2006             |
| CAPER MOTIONS               | 2006             |
| CARIBBEAN LIBERTY           | 2006             |
| CAROL TEXAS                 | 2006             |
| CARRIE BUNCH                | 2006             |
| CASABLANCA SUPER            | 2006             |
| CASPER DRAGONFLY            | 2006             |
| CASSIDY WYOMING             | 2006             |
| CASUALTIES ENCINO           | 2006             |
| CAT CONEHEADS               | 2006             |
| CATCH AMISTAD               | 2006             |
| CAUSE DATE                  | 2006             |
| CELEBRITY HORN              | 2006             |
| CENTER DINOSAUR             | 2006             |
| CHAINSAW UPTOWN             | 2006             |
| CHAMBER ITALIAN             | 2006             |
| CHAMPION FLATLINERS         | 2006             |
| CHANCE RESURRECTION         | 2006             |
| CHAPLIN LICENSE             | 2006             |
| CHARADE DUFFEL              | 2006             |
| CHARIOTS CONSPIRACY         | 2006             |
| CHASING FIGHT               | 2006             |
| CHEAPER CLYDE               | 2006             |
| CHICAGO NORTH               | 2006             |
| CHICKEN HELLFIGHTERS        | 2006             |
| CHILL LUCK                  | 2006             |
| CHINATOWN GLADIATOR         | 2006             |
| CHISUM BEHAVIOR             | 2006             |
| CHITTY LOCK                 | 2006             |
| CHOCOLAT HARRY              | 2006             |
| CHOCOLATE DUCK              | 2006             |
| CHRISTMAS MOONSHINE         | 2006             |
| CIDER DESIRE                | 2006             |
| CINCINATTI WHISPERER        | 2006             |
| CIRCUS YOUTH                | 2006             |
| CITIZEN SHREK               | 2006             |
| CLASH FREDDY                | 2006             |
| CLEOPATRA DEVIL             | 2006             |
| CLERKS ANGELS               | 2006             |
| CLOCKWORK PARADISE          | 2006             |
| CLONES PINOCCHIO            | 2006             |
| CLOSER BANG                 | 2006             |
| CLUB GRAFFITI               | 2006             |
| CLUE GRAIL                  | 2006             |
| CLUELESS BUCKET             | 2006             |
| CLYDE THEORY                | 2006             |
| COAST RAINBOW               | 2006             |
| COLDBLOODED DARLING         | 2006             |
| COLOR PHILADELPHIA          | 2006             |
| COMA HEAD                   | 2006             |
| COMANCHEROS ENEMY           | 2006             |
| COMFORTS RUSH               | 2006             |
| COMMAND DARLING             | 2006             |
| COMMANDMENTS EXPRESS        | 2006             |
| CONEHEADS SMOOCHY           | 2006             |
| CONFESSIONS MAGUIRE         | 2006             |
| CONFIDENTIAL INTERVIEW      | 2006             |
| CONFUSED CANDLES            | 2006             |
| CONGENIALITY QUEST          | 2006             |
| CONNECTICUT TRAMP           | 2006             |
| CONNECTION MICROCOSMOS      | 2006             |
| CONQUERER NUTS              | 2006             |
| CONSPIRACY SPIRIT           | 2006             |
| CONTACT ANONYMOUS           | 2006             |
| CONTROL ANTHEM              | 2006             |
| CONVERSATION DOWNHILL       | 2006             |
| CORE SUIT                   | 2006             |
| COWBOY DOOM                 | 2006             |
| CRAFT OUTFIELD              | 2006             |
| CRANES RESERVOIR            | 2006             |
| CRAZY HOME                  | 2006             |
| CREATURES SHAKESPEARE       | 2006             |
| CREEPERS KANE               | 2006             |
| CROOKED FROGMEN             | 2006             |
| CROSSING DIVORCE            | 2006             |
| CROSSROADS CASUALTIES       | 2006             |
| CROW GREASE                 | 2006             |
| CROWDS TELEMARK             | 2006             |
| CRUELTY UNFORGIVEN          | 2006             |
| CRUSADE HONEY               | 2006             |
| CRYSTAL BREAKING            | 2006             |
| CUPBOARD SINNERS            | 2006             |
| CURTAIN VIDEOTAPE           | 2006             |
| CYCLONE FAMILY              | 2006             |
| DADDY PITTSBURGH            | 2006             |
| DAISY MENAGERIE             | 2006             |
| DALMATIONS SWEDEN           | 2006             |
| DANCES NONE                 | 2006             |
| DANCING FEVER               | 2006             |
| DANGEROUS UPTOWN            | 2006             |
| DARES PLUTO                 | 2006             |
| DARKNESS WAR                | 2006             |
| DARKO DORADO                | 2006             |
| DARLING BREAKING            | 2006             |
| DARN FORRESTER              | 2006             |
| DATE SPEED                  | 2006             |
| DAUGHTER MADIGAN            | 2006             |
| DAWN POND                   | 2006             |
| DAY UNFAITHFUL              | 2006             |
| DAZED PUNK                  | 2006             |
| DECEIVER BETRAYED           | 2006             |
| DEEP CRUSADE                | 2006             |
| DEER VIRGINIAN              | 2006             |
| DELIVERANCE MULHOLLAND      | 2006             |
| DESERT POSEIDON             | 2006             |
| DESIRE ALIEN                | 2006             |
| DESPERATE TRAINSPOTTING     | 2006             |
| DESTINATION JERK            | 2006             |
| DESTINY SATURDAY            | 2006             |
| DETAILS PACKER              | 2006             |
| DETECTIVE VISION            | 2006             |
| DEVIL DESIRE                | 2006             |
| DIARY PANIC                 | 2006             |
| DINOSAUR SECRETARY          | 2006             |
| DIRTY ACE                   | 2006             |
| DISCIPLE MOTHER             | 2006             |
| DISTURBING SCARFACE         | 2006             |
| DIVIDE MONSTER              | 2006             |
| DIVINE RESURRECTION         | 2006             |
| DIVORCE SHINING             | 2006             |
| DOCTOR GRAIL                | 2006             |
| DOGMA FAMILY                | 2006             |
| DOLLS RAGE                  | 2006             |
| DONNIE ALLEY                | 2006             |
| DOOM DANCING                | 2006             |
| DOORS PRESIDENT             | 2006             |
| DORADO NOTTING              | 2006             |
| DOUBLE WRATH                | 2006             |
| DOUBTFIRE LABYRINTH         | 2006             |
| DOWNHILL ENOUGH             | 2006             |
| DOZEN LION                  | 2006             |
| DRACULA CRYSTAL             | 2006             |
| DRAGON SQUAD                | 2006             |
| DRAGONFLY STRANGERS         | 2006             |
| DREAM PICKUP                | 2006             |
| DRIFTER COMMANDMENTS        | 2006             |
| DRIVER ANNIE                | 2006             |
| DRIVING POLISH              | 2006             |
| DROP WATERFRONT             | 2006             |
| DRUMLINE CYCLONE            | 2006             |
| DRUMS DYNAMITE              | 2006             |
| DUCK RACER                  | 2006             |
| DUDE BLINDNESS              | 2006             |
| DUFFEL APOCALYPSE           | 2006             |
| DUMBO LUST                  | 2006             |
| DURHAM PANKY                | 2006             |
| DWARFS ALTER                | 2006             |
| DYING MAKER                 | 2006             |
| DYNAMITE TARZAN             | 2006             |
| EAGLES PANKY                | 2006             |
| EARLY HOME                  | 2006             |
| EARRING INSTINCT            | 2006             |
| EARTH VISION                | 2006             |
| EASY GLADIATOR              | 2006             |
| EDGE KISSING                | 2006             |
| EFFECT GLADIATOR            | 2006             |
| EGG IGBY                    | 2006             |
| EGYPT TENENBAUMS            | 2006             |
| ELEMENT FREDDY              | 2006             |
| ELEPHANT TROJAN             | 2006             |
| ELF MURDER                  | 2006             |
| ELIZABETH SHANE             | 2006             |
| EMPIRE MALKOVICH            | 2006             |
| ENCINO ELF                  | 2006             |
| ENCOUNTERS CURTAIN          | 2006             |
| ENDING CROWDS               | 2006             |
| ENEMY ODDS                  | 2006             |
| ENGLISH BULWORTH            | 2006             |
| ENOUGH RAGING               | 2006             |
| ENTRAPMENT SATISFACTION     | 2006             |
| ESCAPE METROPOLIS           | 2006             |
| EVE RESURRECTION            | 2006             |
| EVERYONE CRAFT              | 2006             |
| EVOLUTION ALTER             | 2006             |
| EXCITEMENT EVE              | 2006             |
| EXORCIST STING              | 2006             |
| EXPECATIONS NATURAL         | 2006             |
| EXPENDABLE STALLION         | 2006             |
| EXPRESS LONELY              | 2006             |
| EXTRAORDINARY CONQUERER     | 2006             |
| EYES DRIVING                | 2006             |
| FACTORY DRAGON              | 2006             |
| FALCON VOLUME               | 2006             |
| FAMILY SWEET                | 2006             |
| FANTASIA PARK               | 2006             |
| FANTASY TROOPERS            | 2006             |
| FARGO GANDHI                | 2006             |
| FATAL HAUNTED               | 2006             |
| FEATHERS METAL              | 2006             |
| FELLOWSHIP AUTUMN           | 2006             |
| FERRIS MOTHER               | 2006             |
| FEUD FROGMEN                | 2006             |
| FEVER EMPIRE                | 2006             |
| FICTION CHRISTMAS           | 2006             |
| FIDDLER LOST                | 2006             |
| FIDELITY DEVIL              | 2006             |
| FIGHT JAWBREAKER            | 2006             |
| FINDING ANACONDA            | 2006             |
| FIRE WOLVES                 | 2006             |
| FIREBALL PHILADELPHIA       | 2006             |
| FIREHOUSE VIETNAM           | 2006             |
| FISH OPUS                   | 2006             |
| FLAMINGOS CONNECTICUT       | 2006             |
| FLASH WARS                  | 2006             |
| FLATLINERS KILLER           | 2006             |
| FLIGHT LIES                 | 2006             |
| FLINTSTONES HAPPINESS       | 2006             |
| FLOATS GARDEN               | 2006             |
| FLYING HOOK                 | 2006             |
| FOOL MOCKINGBIRD            | 2006             |
| FOREVER CANDIDATE           | 2006             |
| FORREST SONS                | 2006             |
| FORRESTER COMANCHEROS       | 2006             |
| FORWARD TEMPLE              | 2006             |
| FRANKENSTEIN STRANGER       | 2006             |
| FREAKY POCUS                | 2006             |
| FREDDY STORM                | 2006             |
| FREEDOM CLEOPATRA           | 2006             |
| FRENCH HOLIDAY              | 2006             |
| FRIDA SLIPPER               | 2006             |
| FRISCO FORREST              | 2006             |
| FROGMEN BREAKING            | 2006             |
| FRONTIER CABIN              | 2006             |
| FROST HEAD                  | 2006             |
| FUGITIVE MAGUIRE            | 2006             |
| FULL FLATLINERS             | 2006             |
| FURY MURDER                 | 2006             |
| GABLES METROPOLIS           | 2006             |
| GALAXY SWEETHEARTS          | 2006             |
| GAMES BOWFINGER             | 2006             |
| GANDHI KWAI                 | 2006             |
| GANGS PRIDE                 | 2006             |
| GARDEN ISLAND               | 2006             |
| GASLIGHT CRUSADE            | 2006             |
| GATHERING CALENDAR          | 2006             |
| GENTLEMEN STAGE             | 2006             |
| GHOST GROUNDHOG             | 2006             |
| GHOSTBUSTERS ELF            | 2006             |
| GIANT TROOPERS              | 2006             |
| GILBERT PELICAN             | 2006             |
| GILMORE BOILED              | 2006             |
| GLADIATOR WESTWARD          | 2006             |
| GLASS DYING                 | 2006             |
| GLEAMING JAWBREAKER         | 2006             |
| GLORY TRACY                 | 2006             |
| GO PURPLE                   | 2006             |
| GODFATHER DIARY             | 2006             |
| GOLD RIVER                  | 2006             |
| GOLDFINGER SENSIBILITY      | 2006             |
| GOLDMINE TYCOON             | 2006             |
| GONE TROUBLE                | 2006             |
| GOODFELLAS SALUTE           | 2006             |
| GORGEOUS BINGO              | 2006             |
| GOSFORD DONNIE              | 2006             |
| GRACELAND DYNAMITE          | 2006             |
| GRADUATE LORD               | 2006             |
| GRAFFITI LOVE               | 2006             |
| GRAIL FRANKENSTEIN          | 2006             |
| GRAPES FURY                 | 2006             |
| GREASE YOUTH                | 2006             |
| GREATEST NORTH              | 2006             |
| GREEDY ROOTS                | 2006             |
| GREEK EVERYONE              | 2006             |
| GRINCH MASSAGE              | 2006             |
| GRIT CLOCKWORK              | 2006             |
| GROOVE FICTION              | 2006             |
| GROSSE WONDERFUL            | 2006             |
| GROUNDHOG UNCUT             | 2006             |
| GUMP DATE                   | 2006             |
| GUN BONNIE                  | 2006             |
| GUNFIGHT MOON               | 2006             |
| GUNFIGHTER MUSSOLINI        | 2006             |
| GUYS FALCON                 | 2006             |
| HALF OUTFIELD               | 2006             |
| HALL CASSIDY                | 2006             |
| HALLOWEEN NUTS              | 2006             |
| HAMLET WISDOM               | 2006             |
| HANDICAP BOONDOCK           | 2006             |
| HANGING DEEP                | 2006             |
| HANKY OCTOBER               | 2006             |
| HANOVER GALAXY              | 2006             |
| HAPPINESS UNITED            | 2006             |
| HARDLY ROBBERS              | 2006             |
| HAROLD FRENCH               | 2006             |
| HARPER DYING                | 2006             |
| HARRY IDAHO                 | 2006             |
| HATE HANDICAP               | 2006             |
| HAUNTED ANTITRUST           | 2006             |
| HAUNTING PIANIST            | 2006             |
| HAWK CHILL                  | 2006             |
| HEAD STRANGER               | 2006             |
| HEARTBREAKERS BRIGHT        | 2006             |
| HEAVEN FREEDOM              | 2006             |
| HEAVENLY GUN                | 2006             |
| HEAVYWEIGHTS BEAST          | 2006             |
| HEDWIG ALTER                | 2006             |
| HELLFIGHTERS SIERRA         | 2006             |
| HIGH ENCINO                 | 2006             |
| HIGHBALL POTTER             | 2006             |
| HILLS NEIGHBORS             | 2006             |
| HOBBIT ALIEN                | 2006             |
| HOCUS FRIDA                 | 2006             |
| HOLES BRANNIGAN             | 2006             |
| HOLIDAY GAMES               | 2006             |
| HOLLOW JEOPARDY             | 2006             |
| HOLLYWOOD ANONYMOUS         | 2006             |
| HOLOCAUST HIGHBALL          | 2006             |
| HOLY TADPOLE                | 2006             |
| HOME PITY                   | 2006             |
| HOMEWARD CIDER              | 2006             |
| HOMICIDE PEACH              | 2006             |
| HONEY TIES                  | 2006             |
| HOOK CHARIOTS               | 2006             |
| HOOSIERS BIRDCAGE           | 2006             |
| HOPE TOOTSIE                | 2006             |
| HORN WORKING                | 2006             |
| HORROR REIGN                | 2006             |
| HOTEL HAPPINESS             | 2006             |
| HOURS RAGE                  | 2006             |
| HOUSE DYNAMITE              | 2006             |
| HUMAN GRAFFITI              | 2006             |
| HUNCHBACK IMPOSSIBLE        | 2006             |
| HUNGER ROOF                 | 2006             |
| HUNTER ALTER                | 2006             |
| HUNTING MUSKETEERS          | 2006             |
| HURRICANE AFFAIR            | 2006             |
| HUSTLER PARTY               | 2006             |
| HYDE DOCTOR                 | 2006             |
| HYSTERICAL GRAIL            | 2006             |
| ICE CROSSING                | 2006             |
| IDAHO LOVE                  | 2006             |
| IDENTITY LOVER              | 2006             |
| IDOLS SNATCHERS             | 2006             |
| IGBY MAKER                  | 2006             |
| ILLUSION AMELIE             | 2006             |
| IMAGE PRINCESS              | 2006             |
| IMPACT ALADDIN              | 2006             |
| IMPOSSIBLE PREJUDICE        | 2006             |
| INCH JET                    | 2006             |
| INDEPENDENCE HOTEL          | 2006             |
| INDIAN LOVE                 | 2006             |
| INFORMER DOUBLE             | 2006             |
| INNOCENT USUAL              | 2006             |
| INSECTS STONE               | 2006             |
| INSIDER ARIZONA             | 2006             |
| INSTINCT AIRPORT            | 2006             |
| INTENTIONS EMPIRE           | 2006             |
| INTERVIEW LIAISONS          | 2006             |
| INTOLERABLE INTENTIONS      | 2006             |
| INTRIGUE WORST              | 2006             |
| INVASION CYCLONE            | 2006             |
| IRON MOON                   | 2006             |
| ISHTAR ROCKETEER            | 2006             |
| ISLAND EXORCIST             | 2006             |
| ITALIAN AFRICAN             | 2006             |
| JACKET FRISCO               | 2006             |
| JADE BUNCH                  | 2006             |
| JAPANESE RUN                | 2006             |
| JASON TRAP                  | 2006             |
| JAWBREAKER BROOKLYN         | 2006             |
| JAWS HARRY                  | 2006             |
| JEDI BENEATH                | 2006             |
| JEEPERS WEDDING             | 2006             |
| JEKYLL FROGMEN              | 2006             |
| JEOPARDY ENCINO             | 2006             |
| JERICHO MULAN               | 2006             |
| JERK PAYCHECK               | 2006             |
| JERSEY SASSY                | 2006             |
| JET NEIGHBORS               | 2006             |
| JINGLE SAGEBRUSH            | 2006             |
| JOON NORTHWEST              | 2006             |
| JUGGLER HARDLY              | 2006             |
| JUMANJI BLADE               | 2006             |
| JUMPING WRATH               | 2006             |
| JUNGLE CLOSER               | 2006             |
| KANE EXORCIST               | 2006             |
| KARATE MOON                 | 2006             |
| KENTUCKIAN GIANT            | 2006             |
| KICK SAVANNAH               | 2006             |
| KILL BROTHERHOOD            | 2006             |
| KILLER INNOCENT             | 2006             |
| KING EVOLUTION              | 2006             |
| KISS GLORY                  | 2006             |
| KISSING DOLLS               | 2006             |
| KNOCK WARLOCK               | 2006             |
| KRAMER CHOCOLATE            | 2006             |
| KWAI HOMEWARD               | 2006             |
| LABYRINTH LEAGUE            | 2006             |
| LADY STAGE                  | 2006             |
| LADYBUGS ARMAGEDDON         | 2006             |
| LAMBS CINCINATTI            | 2006             |
| LANGUAGE COWBOY             | 2006             |
| LAWLESS VISION              | 2006             |
| LAWRENCE LOVE               | 2006             |
| LEAGUE HELLFIGHTERS         | 2006             |
| LEATHERNECKS DWARFS         | 2006             |
| LEBOWSKI SOLDIERS           | 2006             |
| LEGALLY SECRETARY           | 2006             |
| LEGEND JEDI                 | 2006             |
| LESSON CLEOPATRA            | 2006             |
| LIAISONS SWEET              | 2006             |
| LIBERTY MAGNIFICENT         | 2006             |
| LICENSE WEEKEND             | 2006             |
| LIES TREATMENT              | 2006             |
| LIFE TWISTED                | 2006             |
| LIGHTS DEER                 | 2006             |
| LION UNCUT                  | 2006             |
| LOATHING LEGALLY            | 2006             |
| LOCK REAR                   | 2006             |
| LOLA AGENT                  | 2006             |
| LOLITA WORLD                | 2006             |
| LONELY ELEPHANT             | 2006             |
| LORD ARIZONA                | 2006             |
| LOSE INCH                   | 2006             |
| LOSER HUSTLER               | 2006             |
| LOST BIRD                   | 2006             |
| LOUISIANA HARRY             | 2006             |
| LOVE SUICIDES               | 2006             |
| LOVELY JINGLE               | 2006             |
| LOVER TRUMAN                | 2006             |
| LOVERBOY ATTACKS            | 2006             |
| LUCK OPUS                   | 2006             |
| LUCKY FLYING                | 2006             |
| LUKE MUMMY                  | 2006             |
| LUST LOCK                   | 2006             |
| MADIGAN DORADO              | 2006             |
| MADISON TRAP                | 2006             |
| MADNESS ATTACKS             | 2006             |
| MADRE GABLES                | 2006             |
| MAGIC MALLRATS              | 2006             |
| MAGNIFICENT CHITTY          | 2006             |
| MAGNOLIA FORRESTER          | 2006             |
| MAGUIRE APACHE              | 2006             |
| MAIDEN HOME                 | 2006             |
| MAJESTIC FLOATS             | 2006             |
| MAKER GABLES                | 2006             |
| MALKOVICH PET               | 2006             |
| MALLRATS UNITED             | 2006             |
| MALTESE HOPE                | 2006             |
| MANCHURIAN CURTAIN          | 2006             |
| MANNEQUIN WORST             | 2006             |
| MARRIED GO                  | 2006             |
| MARS ROMAN                  | 2006             |
| MASK PEACH                  | 2006             |
| MASKED BUBBLE               | 2006             |
| MASSACRE USUAL              | 2006             |
| MASSAGE IMAGE               | 2006             |
| MATRIX SNOWMAN              | 2006             |
| MAUDE MOD                   | 2006             |
| MEET CHOCOLATE              | 2006             |
| MEMENTO ZOOLANDER           | 2006             |
| MENAGERIE RUSHMORE          | 2006             |
| MERMAID INSECTS             | 2006             |
| METAL ARMAGEDDON            | 2006             |
| METROPOLIS COMA             | 2006             |
| MICROCOSMOS PARADISE        | 2006             |
| MIDNIGHT WESTWARD           | 2006             |
| MIDSUMMER GROUNDHOG         | 2006             |
| MIGHTY LUCK                 | 2006             |
| MILE MULAN                  | 2006             |
| MILLION ACE                 | 2006             |
| MINDS TRUMAN                | 2006             |
| MINE TITANS                 | 2006             |
| MINORITY KISS               | 2006             |
| MIRACLE VIRTUAL             | 2006             |
| MISSION ZOOLANDER           | 2006             |
| MIXED DOORS                 | 2006             |
| MOB DUFFEL                  | 2006             |
| MOCKINGBIRD HOLLYWOOD       | 2006             |
| MOD SECRETARY               | 2006             |
| MODEL FISH                  | 2006             |
| MODERN DORADO               | 2006             |
| MONEY HAROLD                | 2006             |
| MONSOON CAUSE               | 2006             |
| MONSTER SPARTACUS           | 2006             |
| MONTEREY LABYRINTH          | 2006             |
| MONTEZUMA COMMAND           | 2006             |
| MOON BUNCH                  | 2006             |
| MOONSHINE CABIN             | 2006             |
| MOONWALKER FOOL             | 2006             |
| MOSQUITO ARMAGEDDON         | 2006             |
| MOTHER OLEANDER             | 2006             |
| MOTIONS DETAILS             | 2006             |
| MOULIN WAKE                 | 2006             |
| MOURNING PURPLE             | 2006             |
| MOVIE SHAKESPEARE           | 2006             |
| MULAN MOON                  | 2006             |
| MULHOLLAND BEAST            | 2006             |
| MUMMY CREATURES             | 2006             |
| MUPPET MILE                 | 2006             |
| MURDER ANTITRUST            | 2006             |
| MUSCLE BRIGHT               | 2006             |
| MUSIC BOONDOCK              | 2006             |
| MUSKETEERS WAIT             | 2006             |
| MUSSOLINI SPOILERS          | 2006             |
| MYSTIC TRUMAN               | 2006             |
| NAME DETECTIVE              | 2006             |
| NASH CHOCOLAT               | 2006             |
| NATIONAL STORY              | 2006             |
| NATURAL STOCK               | 2006             |
| NECKLACE OUTBREAK           | 2006             |
| NEIGHBORS CHARADE           | 2006             |
| NEMO CAMPUS                 | 2006             |
| NETWORK PEAK                | 2006             |
| NEWSIES STORY               | 2006             |
| NEWTON LABYRINTH            | 2006             |
| NIGHTMARE CHILL             | 2006             |
| NONE SPIKING                | 2006             |
| NOON PAPI                   | 2006             |
| NORTH TEQUILA               | 2006             |
| NORTHWEST POLISH            | 2006             |
| NOTORIOUS REUNION           | 2006             |
| NOTTING SPEAKEASY           | 2006             |
| NOVOCAINE FLIGHT            | 2006             |
| NUTS TIES                   | 2006             |
| OCTOBER SUBMARINE           | 2006             |
| ODDS BOOGIE                 | 2006             |
| OKLAHOMA JUMANJI            | 2006             |
| OLEANDER CLUE               | 2006             |
| OPEN AFRICAN                | 2006             |
| OPERATION OPERATION         | 2006             |
| OPPOSITE NECKLACE           | 2006             |
| OPUS ICE                    | 2006             |
| ORANGE GRAPES               | 2006             |
| ORDER BETRAYED              | 2006             |
| ORIENT CLOSER               | 2006             |
| OSCAR GOLD                  | 2006             |
| OTHERS SOUP                 | 2006             |
| OUTBREAK DIVINE             | 2006             |
| OUTFIELD MASSACRE           | 2006             |
| OUTLAW HANKY                | 2006             |
| OZ LIAISONS                 | 2006             |
| PACIFIC AMISTAD             | 2006             |
| PACKER MADIGAN              | 2006             |
| PAJAMA JAWBREAKER           | 2006             |
| PANIC CLUB                  | 2006             |
| PANKY SUBMARINE             | 2006             |
| PANTHER REDS                | 2006             |
| PAPI NECKLACE               | 2006             |
| PARADISE SABRINA            | 2006             |
| PARIS WEEKEND               | 2006             |
| PARK CITIZEN                | 2006             |
| PARTY KNOCK                 | 2006             |
| PAST SUICIDES               | 2006             |
| PATHS CONTROL               | 2006             |
| PATIENT SISTER              | 2006             |
| PATRIOT ROMAN               | 2006             |
| PATTON INTERVIEW            | 2006             |
| PAYCHECK WAIT               | 2006             |
| PEACH INNOCENT              | 2006             |
| PEAK FOREVER                | 2006             |
| PEARL DESTINY               | 2006             |
| PELICAN COMFORTS            | 2006             |
| PERDITION FARGO             | 2006             |
| PERFECT GROOVE              | 2006             |
| PERSONAL LADYBUGS           | 2006             |
| PET HAUNTING                | 2006             |
| PHANTOM GLORY               | 2006             |
| PHILADELPHIA WIFE           | 2006             |
| PIANIST OUTFIELD            | 2006             |
| PICKUP DRIVING              | 2006             |
| PILOT HOOSIERS              | 2006             |
| PINOCCHIO SIMON             | 2006             |
| PIRATES ROXANNE             | 2006             |
| PITTSBURGH HUNCHBACK        | 2006             |
| PITY BOUND                  | 2006             |
| PIZZA JUMANJI               | 2006             |
| PLATOON INSTINCT            | 2006             |
| PLUTO OLEANDER              | 2006             |
| POCUS PULP                  | 2006             |
| POLISH BROOKLYN             | 2006             |
| POLLOCK DELIVERANCE         | 2006             |
| POND SEATTLE                | 2006             |
| POSEIDON FOREVER            | 2006             |
| POTLUCK MIXED               | 2006             |
| POTTER CONNECTICUT          | 2006             |
| PREJUDICE OLEANDER          | 2006             |
| PRESIDENT BANG              | 2006             |
| PRIDE ALAMO                 | 2006             |
| PRIMARY GLASS               | 2006             |
| PRINCESS GIANT              | 2006             |
| PRIVATE DROP                | 2006             |
| PRIX UNDEFEATED             | 2006             |
| PSYCHO SHRUNK               | 2006             |
| PULP BEVERLY                | 2006             |
| PUNK DIVORCE                | 2006             |
| PURE RUNNER                 | 2006             |
| PURPLE MOVIE                | 2006             |
| QUEEN LUKE                  | 2006             |
| QUEST MUSSOLINI             | 2006             |
| QUILLS BULL                 | 2006             |
| RACER EGG                   | 2006             |
| RAGE GAMES                  | 2006             |
| RAGING AIRPLANE             | 2006             |
| RAIDERS ANTITRUST           | 2006             |
| RAINBOW SHOCK               | 2006             |
| RANDOM GO                   | 2006             |
| RANGE MOONWALKER            | 2006             |
| REAP UNFAITHFUL             | 2006             |
| REAR TRADING                | 2006             |
| REBEL AIRPORT               | 2006             |
| RECORDS ZORRO               | 2006             |
| REDEMPTION COMFORTS         | 2006             |
| REDS POCUS                  | 2006             |
| REEF SALUTE                 | 2006             |
| REIGN GENTLEMEN             | 2006             |
| REMEMBER DIARY              | 2006             |
| REQUIEM TYCOON              | 2006             |
| RESERVOIR ADAPTATION        | 2006             |
| RESURRECTION SILVERADO      | 2006             |
| REUNION WITCHES             | 2006             |
| RIDER CADDYSHACK            | 2006             |
| RIDGEMONT SUBMARINE         | 2006             |
| RIGHT CRANES                | 2006             |
| RINGS HEARTBREAKERS         | 2006             |
| RIVER OUTLAW                | 2006             |
| ROAD ROXANNE                | 2006             |
| ROBBERS JOON                | 2006             |
| ROBBERY BRIGHT              | 2006             |
| ROCK INSTINCT               | 2006             |
| ROCKETEER MOTHER            | 2006             |
| ROCKY WAR                   | 2006             |
| ROLLERCOASTER BRINGING      | 2006             |
| ROMAN PUNK                  | 2006             |
| ROOF CHAMPION               | 2006             |
| ROOM ROMAN                  | 2006             |
| ROOTS REMEMBER              | 2006             |
| ROSES TREASURE              | 2006             |
| ROUGE SQUAD                 | 2006             |
| ROXANNE REBEL               | 2006             |
| RUGRATS SHAKESPEARE         | 2006             |
| RULES HUMAN                 | 2006             |
| RUN PACIFIC                 | 2006             |
| RUNAWAY TENENBAUMS          | 2006             |
| RUNNER MADIGAN              | 2006             |
| RUSH GOODFELLAS             | 2006             |
| RUSHMORE MERMAID            | 2006             |
| SABRINA MIDNIGHT            | 2006             |
| SADDLE ANTITRUST            | 2006             |
| SAGEBRUSH CLUELESS          | 2006             |
| SAINTS BRIDE                | 2006             |
| SALUTE APOLLO               | 2006             |
| SAMURAI LION                | 2006             |
| SANTA PARIS                 | 2006             |
| SASSY PACKER                | 2006             |
| SATISFACTION CONFIDENTIAL   | 2006             |
| SATURDAY LAMBS              | 2006             |
| SATURN NAME                 | 2006             |
| SAVANNAH TOWN               | 2006             |
| SCALAWAG DUCK               | 2006             |
| SCARFACE BANG               | 2006             |
| SCHOOL JACKET               | 2006             |
| SCISSORHANDS SLUMS          | 2006             |
| SCORPION APOLLO             | 2006             |
| SEA VIRGIN                  | 2006             |
| SEABISCUIT PUNK             | 2006             |
| SEARCHERS WAIT              | 2006             |
| SEATTLE EXPECATIONS         | 2006             |
| SECRET GROUNDHOG            | 2006             |
| SECRETARY ROUGE             | 2006             |
| SECRETS PARADISE            | 2006             |
| SENSE GREEK                 | 2006             |
| SENSIBILITY REAR            | 2006             |
| SEVEN SWARM                 | 2006             |
| SHAKESPEARE SADDLE          | 2006             |
| SHANE DARKNESS              | 2006             |
| SHANGHAI TYCOON             | 2006             |
| SHAWSHANK BUBBLE            | 2006             |
| SHEPHERD MIDSUMMER          | 2006             |
| SHINING ROSES               | 2006             |
| SHIP WONDERLAND             | 2006             |
| SHOCK CABIN                 | 2006             |
| SHOOTIST SUPERFLY           | 2006             |
| SHOW LORD                   | 2006             |
| SHREK LICENSE               | 2006             |
| SHRUNK DIVINE               | 2006             |
| SIDE ARK                    | 2006             |
| SIEGE MADRE                 | 2006             |
| SIERRA DIVIDE               | 2006             |
| SILENCE KANE                | 2006             |
| SILVERADO GOLDFINGER        | 2006             |
| SIMON NORTH                 | 2006             |
| SINNERS ATLANTIS            | 2006             |