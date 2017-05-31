Git rebase flow from ArchDaily

http://archdaily.github.io/softwre-engineering/git/gitflow/2014/03/19/our-gitflow.html

	# First, create a new branch from master.
	$ git pull origin master
	$ git checkout -b new-feature

	# Make changes and commits.
	$ git add .
	$ git commit -m "Changes"

	# When finishing the new feature you should bring the code inside master to the branch.
	# It's a good practice to make it frequently during the development of the feature.
	$ git fetch origin master
	$ git rebase origin/master
	$ git push origin new-feature
	# Sometimes, when there are conflits at rebasing, you should make git push -f origin new-feature.

	# After finishing, you should merge and push the new features to master.
	$ git checkout master
	$ git pull origin master
	$ git merge --no-ff new-feature
	$ git push origin master
