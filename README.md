# LotteryBoost

The LimeSurvey-plugin LotteryBoost helps you to randomly choose a winner for your lottery at the end of your LimeSurvey online-survey. The participants will provide their email-addresses at the end of the experiment which will be saved in an extra data base to guarantee the participants' anonymity. At the end of the survey, you can choose the number of winners for your lottery and the plugin will send you an email including the addresses of the lucky-ones. 

## Getting Started

How to use the plugin?
LimeSurvey is a service for online-surveys. The data can be stored local which allows control over the examined data. Even though LimeSurvey provides many benefits, it lacks - without LotteryBoost - in including a lottery at the end of an online-survey. So far, to guarantee anonymity, LimeSurvey users had to create an extra survey for the lottery which they had to attach to their survey. The data for the lottery was saved in a new table which was not intuitive to find. Further, anonymity used to be slightly restricted because the data of the original survey was in the same order as the data for the lottery. 
The Plugin addresses these problems. The lottery can be easily included in the original online-survey. The email-addresses for the lottery are automatically saved in a new, separate table in an alphabetically order. By that, anonymity is fully guaranteed. At the end of the survey, LotteryBoost will pick out randomly the winners whereby the users can determine the amount of winners. 

## Code Examples

    //SQL-Code
    //Duplication checked by PRIMARY KEY - participants cannot enter their email-addresses twice
    $this->connection->createCommand("CREATE TABLE IF NOT EXISTS $wingametable (mails VARCHAR(150) PRIMARY KEY NOT NULL);)->execute();
    
    //Move email-address from the survey table into the new created table
     $this->connection->createCommand("INSERT INTO $wingametable('mails') SELECT $sSgqaCode FROM $tableName WHERE $sSgqaCode IS NOT               NULL;")->excute();
     
     //Set email-addresses in survey table NULL
     $this->connection->createCommand("UPDATE $tableName SET $sSgqaCode = NULL;")->execute();
     
     //Order the content of the new table alphabetically
     $this->connection->createCommand("SELECT * FROM $wingametable ORDER BY 'mails';")->execute();



Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

Give the example

And repeat

until finished

End with an example of getting some data out of the system or using it for a little demo
Running the tests

Explain how to run the automated tests for this system
Break down into end to end tests

Explain what these tests test and why

Give an example

And coding style tests

Explain what these tests test and why

Give an example

Deployment

Add additional notes about how to deploy this on a live system
Built With

    Dropwizard - The web framework used
    Maven - Dependency Management
    ROME - Used to generate RSS Feeds

Contributing

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests to us.
Versioning

We use SemVer for versioning. For the versions available, see the tags on this repository.

## Authors

The plugin has been developed by the research chair [Professional Communication in Electronic Media / Social Media, University of Duisburg Essen](https://www.uni-due.de/proco/index_en.php)

    Prof. Dr. Stefan Stieglitz - Professor
    Tobias Kroll - initial work
    Eric 
    Melina Paßfeld
    Andere Studenten

## License

See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).
