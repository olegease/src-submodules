### Info

C++ codebase structured in independent projects that init from core project to use as submodules at another repositories.

Each project has seperate folder, branch and github project

Use C++17 standard

### Branches:
_TODO: Add gitflow diagram and add more description and sanitize wording_ 

##### MASTER

master - main branch that contains all release (tested) code, contain some usefull info (such as README and another text files) and global stuff (gitignore etc), 

    merge [project] stable branches to this
    from this only init core and dev branches

##### PROJECT FAMILY

[project] - each project (include specific, see core and dev above) have own branch, folder and github project:

    init from core
    merge core to this on core updates
    from this init only release (version) branches
    merge this to -[project]/[feature|issue] branches

[project]-dev - test and other utility files for develop project that not needed in release but require for building testing etc

    init from [project]
    merge dev to this
    not merge this to dev

-[project]/[feature|issue] - any added code to project must be in some feature/issue

    init from [project]
    merge to [project]
    merge to [project]-dev

[project]_[VERSION] - release brances

    only init from [project] after testing
    no other branch operations after creating it (maybe reconsider later)

[project]-dev - almost testing branch that contains test files for project

    init from [project]
    never merge to any other branch

#### SPECIFIC PROJECTS (BRANCHES)

    Have almost same gitflow as PROJECRS FAMILY section with some changes.

##### DEV
dev - specific project, contains tests, debug and other tools to check project stability etc...,

    init from master (from first README commit)
    never merge to master
    never merge master to this
    merge this to [project]-dev to test project
    never merge this to branches that haven't -dev suffix

##### CORE

core - specific project, from what init all another projects

    init from master
    on update merge this to [project] branches
    merge this to master

### Additional Info

