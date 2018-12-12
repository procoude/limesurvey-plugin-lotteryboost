# LotteryBoost

The LimeSurvey-plugin LotteryBoost helps you to randomly choose a winner for your lottery at the end of your LimeSurvey online-survey. The participants will provide their email-addresses at the end of the experiment which will be saved in an extra data base to guarantee the participants' anonymity. At the end of the survey, you can choose the number of winners for your lottery and the plugin will send you an email including the addresses of the lucky-ones. 

## Getting Started

LimeSurvey is a service for online-surveys. The data can be stored local which allows control over the examined data. Even though LimeSurvey provides many benefits, it lacks - without LotteryBoost - in including a lottery at the end of an online-survey. So far, to guarantee anonymity, LimeSurvey users had to create an extra survey for the lottery which they had to attach to their survey. The data for the lottery was saved in a new table which was not intuitive to find. Further, anonymity used to be slightly restricted because the data of the original survey was in the same order as the data for the lottery. 
The Plugin addresses these problems. The lottery can be easily included in the original online-survey. The email-addresses for the lottery are automatically saved in a new, separate table in an alphabetically order. By that, anonymity is fully guaranteed. At the end of the survey, LotteryBoost will pick out randomly the winners whereby the users can determine the amount of winners. 

## How to use it

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

## Authors

The plugin has been developed by the research chair [Professional Communication in Electronic Media / Social Media, University of Duisburg Essen](https://www.uni-due.de/proco/index_en.php)

    Prof. Dr. Stefan Stieglitz - Professor
    Tobias Kroll - initial work
    Eric 
    Melina Paßfeld
    Andere Studenten

## License

See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).
