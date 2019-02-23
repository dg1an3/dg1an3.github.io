## fsasciipixels / csxasciipixels
  - ```*.jpg``` &\\&/&\> ```[..::||||::...] ```
  - ```(fun x y -> ...)``` &\\&/&\> ```[..::||:..:||:] ```
  - ```((x,y) => ...)``` &\\&/&\> ```[..::||:..:||:] ```
## plantuml F# type provider
  - ```Structure *--> Header *--> Part``` &\\&/&\> ```type Foo() = member this.Bar = 0```
## ifanimage reader
  - ```Structure *--> Header *--> TechInfo``` &\\&/&\> ```type Image() = member this.Width = 0```
  - ```Image(file)|>show``` &\\&/&\> ```<opened image viewer>```
  - ```Image(file)|>display``` &\\&/&\> ```<embedded nb viewer>```
## dicom parser xml
  - ```<dicom><spec></spec></dicom>``` &\\&/&\> ```Module *--> Sequence *--> Macro```
  - in fssom??  prolog version??
## dicom reader
  - ```Module *--> Sequence *--> Macro``` &\\&/&\> ```type DicomImage(de) = member this.Width = 0```
  - ```DicomImage(file)|>display``` &\\&/&\> ```<embedded nb viewer>```
## LambdaDicom
  - plantuml of classic = original types and modules
  - plantuml of ImageFilters / ImageStatistics / ImagePixelsPipeline
  - notebook showing unit test results
## zebrastack
  - aperture sparse match of portal: ```[.||:.:|:.]``` &\\&/&\> ```[0.2 MLC; 0.1 MLC; 0.3 GRND]```
  - radar sparse match of birds/planes/rocket: ```[.||:.:|:.]``` &\\&/&\> ```[0.2 WING; 0.1 BODY]```
## registration notebook
  - transform conversion graph
  - papermill property-based testing of same direction from graph
## FsSom/pysom
  - input -> map -> heatmap
  - papermill optimization notebook
## Blackboard radar demo
  - ns of rader code
  - puml of modified design
## ActorViewModel
  - blackboard non-mvvm -> mvvm
  
