# leapt
leapt (pronounced 'Lee-P-T') is an attempt to get GPT to formalize lean proofs

# Dependencies
To run leapt, you will need python along with the `python-openai` package. You
will also need an OpenAI key, see below. The default editor is `nano`.

# OpenAI key
To use leapt, you need to have an openai API key (which you can get from yout
openai account page). Store the key in a file called "openai.key" in the same
directory as the `leapt` executable.

# Usage
Run `leapt`. This will send the first prompt to GPT, extract the appropriate
lean code, have lean compile it, and send the errors back to GPT.

leapt will prompt for confirmation throughout the process, and will allow you
to edit the prompts, and the lean code. By default, it uses the `nano` editor.

To exit leapt, reply `n` to the `Continue` prompt. This will save the current
history to a file in the `history` directory for future use.

The latest lean code obtained from GPT is saved in the `gpt.lean` file.

Several options can be changed by editing the top of the `leapt` file.
* To change the first prompt, edit `first_prompt`.
* To change the behaviour of GPT, edit `gpt_instructions`.
* By default, leapt runs on gpt-3.5. To change this, edit `gpt_ver`:
  - `3` for gpt-3.5-turbo
  - `4` for gpt-4
* To change the default editor, edit `editor`.
* Various paths can be changed as well.
