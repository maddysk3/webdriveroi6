# webdriveroi6

Setup your project
Before installing dependencies, you’ll need to initialize a new NPM project. This will allow you to use the CLI to install dependencies in your project.

To do this, run:

mkdir webdriverio-test && cd webdriverio-test
npm init -y
The -y will answer 'yes' to all the prompts, giving you a standard NPM project. Feel free to omit the -y if you'd like to specify your own project details.

Install WebdriverIO CLI
If you want to use WebdriverIO in your project for integration testing, we recommend using the test runner. It comes with lots of useful features that makes your life easier.

Since WebdriverIO version 5, the testrunner is in the @wdio/cli NPM package.

Now, install the CLI:

$ npm i --save-dev @wdio/cli
Generate Configuration File
Next, you’ll generate a configuration file to store your WebdriverIO settings.

To do that, just run the configuration utility:

$ npx wdio config -y
That's it! The configurator will install all required packages for you and create a config file called wdio.conf.js.

Create Spec Files
Now it's time to create your test file. You’re going to store all of your test files in a new folder.

Create the test folder like this:

Linux/Mac

mkdir -p ./test/specs
Create a new file in that folder (we'll call it basic.js):

touch ./test/specs/basic.js
On Windows, touch will not work so you can simply go to the folder and create a plain text file and name is as 'basic.js'

Open that file, and write the following code in it:

Sync Mode

const assert = require('assert')

describe('webdriver.io page', () => {
    it('should have the right title', () => {
        browser.url('https://webdriver.io')
        const title = browser.getTitle()
        assert.strictEqual(title, 'WebdriverIO · Next-gen browser automation test framework for Node.js')
    })
})
Now save the file and return to your terminal. Learn more about the differences between Sync and Async Mode.

Start the Testrunner
Now, time to run your tests!

To do so, just run:

$ npx wdio wdio.conf.js
Hurray! The test should pass, and you can start writing integration tests with WebdriverIO.
