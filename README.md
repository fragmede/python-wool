Python-wool
---

Python-wool is a simple wrapper for python to make it easier to use venvs.

It will use the venv that is colocated in a python program's installed path.
So if you do python-wool~/projects/foo/bar/baz/example.py, it will search for a
venv dir along that path, and then activate that before trying to run the
python program, saving you grief trying to juggle multiple python venvs around.

Download this, and then

   alias python=~/path/to/python-wool

into your shell's config file (.bashrc)

Then, in a new shell you can run:

    python ~/projects/foo/bar/baz.py

and it will activate ~/projects/foo/bar/venv before running baz.py.

It will also search for venvs in directories named:
    .venv, venv, env, .env, virtualenv, .virtualenv

It will also search for those up the path (so ~/projects/foo/venv, ~/projects/venv, ~/venv), as well as up the path from currrent working directory.

It currently does not look in ~/.conda/environments.txt because I don't
have a good heuristic on how to pick one from there.

TODO:
 * Have it automatically create venvs if a requirements.txt is found.
