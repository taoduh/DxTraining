# Illumina DCP Seed

Split from [Salesforce's Version](https://github.com/forcedotcom/sfdx-simple)

[![Deploy](https://deploy-to-sfdx.com/dist/assets/images/DeployToSFDX.svg)](https://deploy-to-sfdx.com/)

The Salesforce Developer Experience (SFDX) starts with source code living in your version control system.

## Set Up the Salesforce DX Project

Our first goal is to set up a developer project which we'll use to modify our application. It starts by cloning the repository. Use the command ...

    git clone https://github.com/Illumina-SFDC/documentDX.git

… or ...

    git clone git@github.com:Illumina-SFDC/documentDX.git

… to clone the repository. Then, open the directory.

    cd documentDX
    
## Steps

Authorize to your Developer Hub (Dev Hub) org.

    sfdx force:auth:web:login -d -a "Hub Org"

If you already have an authorized Dev Hub, set it as the default:

    sfdx force:config:set defaultdevhubusername=<username|alias>

Create a scratch org.

    sfdx force:org:create -s -f config/project-scratch-def.json

If you want to use an existing scratch org, set it as the default:

    sfdx force:config:set defaultusername=<username|alias>

Push your source.

    sfdx force:source:push

Run your tests.

    sfdx force:apex:test:run
    sfdx force:apex:test:report -i <id>

Open the scratch org.

    sfdx force:org:open --path one/one.app

## Resources

For details on using sfdx-simple, please review the [Salesforce DX Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev).

## Description of Files and Directories  

* **sfdx-project.json**: Required by Salesforce DX. Configures your project.  Use this file to specify the parameters that affect your Salesforce development project.
* **config/project-scratch-def.json**: Sample file that shows how to define the shape of a scratch org.  You reference this file when you create your scratch org with the force:org:create command.   
* **ilmn-dcp**: Directory that contains the source for the sample Force.com app and tests.
* **.gitignore**:  Optional Git file. Specifies intentionally untracked files that you want Git (or in this case GitHub) to ignore.