# LotteryBoost

The LimeSurvey-plugin LotteryBoost helps you to randomly choose a winner for your lottery at the end of your LimeSurvey online survey.
The participants will provide their email addresses at the end of the experiment which will be saved in an separate database to guarantee the participants' anonymity.
At the end of the survey, you can choose the number of winners for your lottery and the plugin will send you an email including the addresses of the lucky-ones. 

## Getting Started

LimeSurvey is a web software for online surveys. The data can be stored on-premise which allows control as regards data safety and privacy requirements.

Even though LimeSurvey provides many benefits, it lacks a lottery at the end of an online-survey. So far, to guarantee anonymity, LimeSurvey users had to create an extra survey for the lottery which they had to attach to their survey.
The data for the lottery was saved in a new table which was not intuitive to find.
Further, anonymity used to be slightly restricted because the data of the original survey was in the same order as the data of the lottery. 

The Plugin addresses these problems.
The lottery can be easily included in the original online survey.
The email addresses for the lottery are automatically saved in a new, separate table in an alphabetically order.
By that, anonymity is fully guaranteed.
At the end of the survey, LotteryBoost will pick out randomly the winners whereby the users can determine the amount of winners. 

## How to use it

To use this Plugin, you can either download LotteryBoost in one zip file and then unzip it in your LimeSurvey installation. Or, if you prefer, you can use GitHub and fork LotteryBoost via GIT to use it. At the end, make sure that you activate the PluginManager in your Limesurvey settings.

Via ZIP dowload

    Get the LotteryBoost file and unzip it
    Move the file included to plugins/limesurvey-plugin-lotteryboost directory

Via GIT

    Go to your LimeSurvey Directory 
    Clone in plugins/limesurvey-plugin-lotteryboost directory

## Disclaimer / Status of the plugin

In case you decide to use this Plugin, you understand that LotteryBoost is not suitable for a productoin environment. Further, you understand and agree that we will not be liable to you or any third party for any loss of profits, use, goodwill, or - in this case especially important - data, or for any incidental, indirect, special, consequential or exemplary damages, however arising.

Our liability is limited whether or not we have been informed of the possibility of such damages, and even if a remedy set forth in this Agreement is found to have failed of its essential purpose. We will have no liability for any failure or delay due to matters beyond our reasonable control.

## Code Examples
```php
	 /**
	 * check if the plugin should be used in certain survey
	 * 
	 * @param string $sSurveyId
	 * @return boolean
	 */
	private function isWingameEnabled($sSurveyId)
	{
	    return ($this->get('bUse','Survey',$sSurveyId)==0)||($this->get('bUse',null,null,$this->settings['bUse'])==0);
	}

	/**
	 *  check if the admin would like to receive an e-mail
	 *  
	 *  @param string $sSurveyId
	 *  @return boolean 
	 */
	private function isAdminEmailEnabled($sSurveyId){
	    return ($this->get('bAdminReceive','Survey',$sSurveyId)==0);
	}
```

## Authors

The plugin has been developed by students at the chair of [Professional Communication in Electronic Media / Social Media, University of Duisburg Essen](https://www.uni-due.de/proco/index_en.php).

## License

This plugin is licenced under the GPL 2.0.
The LimeSurvey Logo is a registered trademarks of LimeSurvey GmbH, Hamburg, Germany.

