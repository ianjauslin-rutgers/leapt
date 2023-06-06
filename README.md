# leapt
leapt (pronounced 'Lee-P-T') is an attempt to get GPT to formalize lean proofs

# Dependencies
To run leapt, you will need python along with the `python-openai` package. You
will also need an OpenAI key, see below. The default editor is `nano`.

leapt requires Lean 3 with a local copy of mathlib, which can be downloaded by
running
```bash
$ leanproject new leapt-lean
$ mv leapt-lean/* ./
$ rm -r leapt-lean
```

# OpenAI key
To use leapt, you need to have an openai API key (which you can get from yout
openai account page). Store the key in a file called "openai.key" in the same
directory as the `leapt` executable.

# Usage
Run `leapt`. This will send the first prompt to GPT, extract the appropriate
lean code, have lean compile it, and send the errors back to GPT.

Several options can be set in the `leapt.conf` file, which you can create by
copying the `leapt.conf.sample` file. To use a different configuration file,
use the `-c <config_file>` argument.

By default, leapt will prompt for confirmation throughout the process, and will
allow you to edit the prompts, and the lean code. By default, it uses the
`nano` editor. You can disable prompting by setting `interactive_freq` to 0 i
the configuration file. You can also specify how often to prompt by setting
this value to a positive integer. To exit leapt, reply `n` to the `Continue`
prompt.

By default, leapt will stop after 100 queries, or after 10000 tokens have been
exchanged. These limits can be changed in the configuration file. (If you set
these to 0, there will be no limit: use at your own risk!)

Before leapt exits, it will save the current history to a file in the `history`
directory for future use.

The latest lean code obtained from GPT is saved in the `gpt.lean` file.
