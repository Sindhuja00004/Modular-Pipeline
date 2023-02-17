                                         Modular Pipeline
CONFIGURING PARAMETER 
1)	By configuring the parameter section in the AOB pipeline we can make the pipeline run only in a specified stage using the Boolean parameter.
2)	Inside project configuration settings enable the ‘This project is parameterized’ option and select Boolean Parameter.

![image](https://user-images.githubusercontent.com/95271479/219564263-43c90d4e-4ee6-4584-975e-ea9bf9e70233.png)

3)	Add all the stages in Boolean Parameter by clicking the ‘Add Parameter’ option and also select ‘set by default’ option.

![image](https://user-images.githubusercontent.com/95271479/219564448-db66ddcd-67a8-4349-9e3d-1fd5ebe16020.png)

4)	Inside the pipeline script add parameter syntax for all stages. We can also generate pipeline syntax. Go to Pipeline syntax  Declarative Directive Generator  parameter.parameter  Add  Boolean Parameter. Specify the stage and hit on Generate Declarative Directive.

![image](https://user-images.githubusercontent.com/95271479/219564507-93a4b8df-e298-4ad2-bb4e-a7ee3426532a.png)

5)	Repeat the same process for the rest of the stages by selecting “Add Paramter”.

6)	Add all the commands in the pipeline.

![image](https://user-images.githubusercontent.com/95271479/219564571-cb9a289d-4616-4a38-857b-2dc11948130d.png)

7)	Inside each stage pipeline use when expression to call the respective parameters at each stage.

![image](https://user-images.githubusercontent.com/95271479/219564662-7c3ec9dc-b868-49bb-90e6-6a990adf3e8d.png)

8)	Click on apply and save. Now we should be able to see an option  ‘Build with parameters. Select the stage to perform the build. Ex : For demo selected ‘Build’ stage.

![image](https://user-images.githubusercontent.com/95271479/219564730-23265de0-74be-452d-9ee1-502676cbc9f6.png)

9)	Pipeline will get successfully get executed with specific stage.

![image](https://user-images.githubusercontent.com/95271479/219564788-a51ed03e-c13f-484e-9b8f-4f93264228c5.png)

Note : We can select Multiple stages and single stage to execute by selecting the checkboxes

                                      Triggering respective jobs
                                      
1)	The main pipeline stage can trigger their respective jobs by using the “build” command.

2)	The “Checkout” stage in the main pipeline triggers a separate pipeline i.e “Checkout” pipeline which also contains stages and steps.

3)	The “Build” stage in the main pipeline triggers a separate pipeline i.e “Build The Code” pipeline which also contains stages and steps.

4)	The “Unit” stage in the main pipeline triggers a separate pipeline i.e “Unit Test Case” pipeline which also contains stages and steps.

                                  Variablization in Jenkins pipeline :

1)	Variablization is done in ASoD stage and Sonarqube stage.

2)	Open the terminal and under this path i.e /var/lib/Jenkins/.evars/variables.groovy and declare the variables in ASoD and sonarqube stage variables with their values.

![image](https://user-images.githubusercontent.com/95271479/219565287-4f7e6fed-8ff2-4d39-92f7-e08d0a7c8048.png)

3)	In the pipeline script under ASoD stage map the variables. Use the load command to Evaluate a Groovy source file into the Pipeline script. 

![image](https://user-images.githubusercontent.com/95271479/219565487-242c7eed-01d2-4969-b5a1-b1889770143b.png)

4)	In the pipeline script under the Sonarqube stage map the variables. Use the load command to Evaluate a Groovy source file into the Pipeline script. 

![image](https://user-images.githubusercontent.com/95271479/219565565-781f9500-44ff-459b-91f7-5262d9eb6428.png)

5)	Build the pipeline and the output is as follows.

![image](https://user-images.githubusercontent.com/95271479/219565653-d92ab28f-6026-4a19-9168-3df7cb010c58.png)

                                    LOADING VARIABLES FROM GITHUB
                                    
 1)	Create a file in the repository and add all the variables to the file and commit the changes.
 
 ![image](https://user-images.githubusercontent.com/95271479/219565840-acdbe6a5-5273-400b-a4dd-d540366bc512.png)

2)	In the main Jenkins pipeline clone the git repository.

![image](https://user-images.githubusercontent.com/95271479/219565921-23cae93f-3d64-47b3-9b49-6afb8198f9e6.png)

3)	Load the variables into the Jenkins pipeline.

![image](https://user-images.githubusercontent.com/95271479/219565976-11c306cb-2569-4e80-af97-1b2a16f541c4.png)

4)	The console output would be as follows.

![image](https://user-images.githubusercontent.com/95271479/219566071-589d3ccd-13e1-43f9-a49d-1382a2f1cb52.png)
