# git-mystery-game

A browser-based mystery game that teaches Git by having players investigate a story and fix real Git mistakes along the way.

**Status:** Early development. The name is a working title.

## Why this exists

Many students learn basic Git in class, but not what to do when something goes wrong: a commit on the wrong branch, work that seems lost, or a secret pushed to a repository. Those skills usually get learned through trial and error or scattered pages online. This game teaches them before the panic happens.

## How it works

- **A story drives the learning.** Players investigate a mystery inside a repository, and each clue requires a Git skill to uncover.
- **Each skill is taught before it's tested.** Short lessons introduce one concept at a time, followed by a quick check.
- **Players type real Git commands** into a simulated terminal in the browser. Nothing to install.
- **A live commit map** shows what each command did to the repository.

## Current prototype

The prototype has three levels, each with a lesson:

1. **Committed too soon:** undo a commit without losing your work (`git reset`)
2. **Wrong branch:** move a commit off `main` onto its own branch (`git branch`, `git reset`, `git switch`)
3. **The vanishing commit:** recover a commit you thought was deleted (`git reflog`)

The mystery storyline is in design. These levels will become part of its first chapter.

## Run it locally

Download or clone the repository, then open `index.html` in a browser.

## Project docs

- [One-pager](docs/one-pager.md): the problem, target user, goals, and success metrics

More docs, including a decision log and research findings, will be added as the project progresses.

## License

See [LICENSE](LICENSE).

