# ANova Application Reader 🎉
In general, this repo contains useful tools that the officer team uses/has used (s/o kshi), but is mainly used for reading applications during recruitment.

## Running the Reader 💻
1. In your terminal, clone the repo: `git clone  https://github.com/ANovaBerkeley/anova`
2. Navigate into the `writtenapp` directory, and place `secrets.py` in there (you should receive `secrets.py` from Exec)
3. Run `python3 reader.py` and follow the given instructions (if you receive an error, run `pip install python3`)

## Updating the Reader for Recruitment 👩‍💻
There's two ways to contribute to this repo: Pull Requests or Contributing Directly.

### Pull Requests
1. Fork this repo to your own GitHub account.
2. Make any changes to the reader.
3. When you're done with your changes, create a pull request (aka a code review!). Someone in the ANova GitHub organization can then review your code, ask for revisions, correct any potential bugs, and then merge in your code.

### Contribute Directly (Not Recommended)
1. Ask a previous contributor to add you to the Berkeley ANova GitHub organization.
2. Clone this repo and make necessary changes. Try to keep the # of commits as low as possible to reduce clutter. (Tip: `git rebase`)
3. Push directly to master after testing thoroughly: `git push origin master`

## Linking the Reader with Airtable
The reader uses the Airtable API to read the responses from the application, and write to a new table called Decisions.

### Creating a new Workspace and Base
1. Login to the ANova Airtable and create a new Workspace with the semester and year as the title. (e.g. Spring 2020)
2. Create a new Airtable base from scratch. This will create a new table in `Grid` view called `Table 1`. On the bottom left under "Create a view", add a `Form` view and input the current semester's interview questions.
3. Rename `Table 1` to `All Applications`.
4. Create a new empty table in this base called `Decisions` with the columns `Applicant Name`, `Reviewer Name`, and `Interview`.
5. Now, go to `https://airtable.com/api` and click on the current semester's base. Copy the hash in the Introduction that says, "The ID of this base is app________".
6. Go to `https://airtable.com/account` and copy the API key.
7. Create a `secrets.py` file. Say the `API_KEY=key123` and `BASE_ID=appABC`, then the contents would be:
```
API_KEY='key123'
APPLICATION_BASE_ID='appABC'
DECISION_BASE_ID='appABC'
```
8. Never commit the `secrets.py` file. Instead, DM it to the officers directly (in Slack or whatever). 
9. You should be ready to go 🥳 Happy Recruitment!
