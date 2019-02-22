### Steps to install CI configuration on local environment (https://circleci.com/docs/2.0/local-cli/)
1. **Install tools** 
    - Docker ( if not available )
       - Refer : https://docs.docker.com/docker-for-mac/install/
    - Brew ( if not available )
       - Refer : https://brew.sh/
    - CircleCI ( if not available )
       - `brew install circleci`

2. **Create config circleCI in the project ( if not available )**
    - Refer: 
       - https://circleci.com/docs/2.0/configuration-reference/ 
       - https://circleci.com/docs/2.0/sample-config/
       - `[FUNMEE-WEB]` https://github.com/tribalmedia/funmee-web/blob/master/.circleci/config.yml
       - `[FUNMEE-PROD]` https://github.com/tribalmedia/funmee-prod/blob/master/.circleci/config.yml
3. **Validate A CircleCI Config**
    - If  ` [FUNMEE-WEB]/.circleci/config.yml ` or  ` [FUNMEE-PROD]/.circleci/config.yml ` file exists
    - Run the command to validate: 
       `circleci config validate`

4. **Run A Job In A Container On Your Machine**
    - Refer: https://circleci.com/docs/2.0/local-cli/#run-a-job-in-a-container-on-your-machine

    - Run command for Funmee projects: (If during the process of running these commands there are errors then try the following.[`(notice)`](#notice))
         - `[FUNMEE-WEB]`
            - Check convention js : 
              > `circleci local execute --job check_convention_js`
            - Check convention php : 
              > `circleci local execute --job check_convention_php`
            - Check convention sass : 
              > `circleci local execute --job check_convention_sass`
            - Test : 
              > `circleci local execute --job test`

        - `[FUNMEE-PROD]`
            - Check convention js : 
              > `circleci local execute --job check_convention_js`
            - Check convention php : 
              > `circleci local execute --job check_convention_php`
            - Test : 
              > `circleci local execute --job test`
    - #### Notice: When an error occurs<a name='notice'>
        - Change the content of the file `~/.circleci/build_agent_settings.json` to :   
        
            ``` {"LatestSha256":"sha256:f340abec0d267609a4558a0ff74538227745ef350ffb664e9dbb39b1dfc20100"} ```
            
        - Then run the command again
