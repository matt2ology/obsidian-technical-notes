# So You Think You Know Git - FOSDEM 2024

![rw-book-cover](https://i.ytimg.com/vi/aolI_Rz0ZqY/maxresdefault.jpg)

## Metadata

- Author: [[GitButler]]
- Full Title: So You Think You Know Git - FOSDEM 2024
- Category: #articles
- URL: <https://www.youtube.com/watch?v=aolI_Rz0ZqY&ab_channel=GitButler>

## Highlights

> So normally you run, Git blame and it blames the entire file and pages it. If you know the
> line range, then you can say just blame this line range and A it makes it faster, but B, it
> makes it more, more understandable ([View Highlight](https://read.readwise.io/read/01hpk5f9emg3qsqrfj8ty6rq1j))

Note: You can just blame a portion of the file with flag `-L` for line and the inclusive line range: `git blame -L <fromLine, toLine> path/to/file`

> Git log dash L and then give it like a function name. And it will try to figure out what that
> block is, heuristically and do the exact same thing. So if you it depends on the language.
> ([View Highlight](https://read.readwise.io/read/01hpk5vd3jgv67n04t0khgh4dq))

Note: One can also `git log` a portion of the file as one can also do with `git blame`: `git log -L <fromLine, toLine>:path/to/file`.

The command can also take in a function name and git will try to figure out what that block is heuristically `git log -L :File:path/to/file`

> GitHub and most of the GUIs don't ignore whitespace by default when when it runs Git
> blame and there's more options you can give Git blame. So you can also say dash C
> which says detect code movement. So if you delete a function and then move it
> somewhere else in the file, it will remember that and it will kind of ignore that movement.
> ([View Highlight](https://read.readwise.io/read/01hpk62atp59mrdypqa92fzaxj))

Note: Ignores Whitespace - Useful looking though what commits were made and filters though items that "matter"
`git blame -w -C`: and detect lines moved or copied in the same commit
`git blame -w -C -C`: the same as prior, but with "or the commit that created the file"
`git blame -w -C -C -C`: the same as prior, but with "or any commit at all"
`git blame -w -C -C -C -L <fromLine, toLine> path/to/file`: Outputs just a portion of a document; as a result, ignores renames and all the movement thus focusing on the actual person responsible of defined code section.

> Git log dash S how am I doing on time? I'm doing okay. Okay. Git log dash S pickax. So
> this is a way that you can say filter all my Git log output to anything that has this regular
> expression or the string in it. So if you removed a variable or added a variable, anything
> with that, that that string in it, it will just show you that this is a really nice way of seeing
> when something was changed that maybe Git grep wouldn't find because it was removed
> from the code base and you want to know when it was removed from the code base.
> ([View Highlight](https://read.readwise.io/read/01hpk6k31hccenkfdt3438f74t))

Note: `git log -S files_watcher -p`

> The other thing is reflog. So this is a log of your references. If you haven't used this, it will
> do it by default on head and you can run Git reflog and it will show you okay, you pulled
> and you did the reset before that and you did check out from a branch to another one
> and you to rebase and here's all the steps of the rebase. But if you ever want to run like
> Git reset and you think it's going to mess stuff up, don't be too afraid because you can
> run, Git reflog and see kind of what every step of that was. And you can always get back
> to where you were. So whenever the head is pointing at something, it has a log of that.
> ([View Highlight](https://read.readwise.io/read/01hpk6n8h2ac9bhx9rdwy1ghsz))

Note: `git reflog`

> Git word diff. So if you run Git diff, it will give you by default a line based diff, which
> sometimes, especially if you're, you know, using tailwind can be really difficult to figure
> out. What was the one class that was kind of added in in the middle of this line. If you
> run Git diff -- word diff, it will do it as a word diff instead. And so it makes it much easier
> to see if you know it's a word sort of a word based diff, what the difference is.
> ([View Highlight](https://read.readwise.io/read/01hpk6qevjkb6785z540z9pweq))

Note: `git diff --word-diff`

> If you have a merge conflict you can tell Git remember this merge conflict and remember
> how I fixed it and keep that in memory. It actually keeps it on disk as a as a hash. But if I
> see it again it can automatically fix it for me. ([View Highlight](https://read.readwise.io/read/01hpk6vkacfn88ytxsgdvp3v8s))

Note: REuse REcorded REsolution
`git config --global rerere.enabled true`
Useful when very useful when cherry picking or rebasing a lot, and hitting similar merge conflicts repeatedly. Git has recorded the pre-image for the conflict and fixes the solution automatically.
It's not expensive disk wise.

> dash dash column or you can set a global config column.ui auto and then if it sees this
> sort of list instead of sort of paging it as one line, it will try to put it into columns
> graphically for you. And the other one is branch.sort. So you can sort your branches by
> default by in this case reverse commiterdate. So I want to see the ones that have had the
> last commit first right the most recent commit first. ([View Highlight](https://read.readwise.io/read/01hpk7c1a1fmp6g0bb74sx0fcd))

Note: Instead of a single list in alphabetical order you can have a list of Git branches in
column and rows: `git branch --column`

Can have git display items column-row format with the following configuration: `git config --global column.ui auto`

Git branches an be ordered by reverse commiterdate: `git config --global branch.sort -committerdate`

> it's just going to make everything faster and you won't have to worry about anything. So
> if you've ever run like a Git command and you see like, you know, it's garbage collector,
> it's running. Git GC It's like garbage collecting or pruning loose objects or doing
> something like that. It's doing that but in the background. So you don't it doesn't have to
> tack it on to another command that you run because there's something running in the
> background. So this is what strategy incremental does. It does mostly these four things.
> It does commit graph generation, which I'll talk about in a second pre fetch every hour,
> which I'll talk about in a second loose object collection and incremental repacks of of
> your packs. But really all that means is shit just gets faster. ([View Highlight](https://read.readwise.io/read/01hpk80r9jzvf4zc6qg31ygxwy))

Note: `git maintenance start` appends the following to `.git/config` file

```yml
[maintenance]
    auto = false
    strategy = incremental
```

This will make thing generally faster...
`strategy = incremental` does the following:

- Commit graph generation
- prefetch every hour
- loose object collection
- incremental-repack
