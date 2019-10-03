# fisher-lm-srilm

The notebook in this repository documents the use of [`SRILM`](http://www.speech.sri.com/projects/srilm/manpages/) to construct an add-1 smoothed unigram model based on the Fisher corpus. It exists principally because [`kenlm`](https://github.com/kpu/kenlm) categorically does not calculate unigram models.

The variation in models tested here is more documentation of SRILM options/use than meaningful testing. (Especially in light of how little variation there is in the test set results.)

## Dependencies

 - You need a Unix-like environment, supporting basic shell/`bash` commands, `sed`, and `awk`, although all of this functionality could be easily (but tediously) replaced by pure Python commands.
 - The most essential parts of the notebook are actually bash cells calling `SRILM` shell commands. You need SRILM installed.
 - You need your own copy of the Fisher corpus, processed analogously to [my other Fisher corpus language model repository](https://github.com/emeinhardt/fisher-lm): a text file with one utterance per line (`fisher_utterances_main.txt`). The notebook currently assumes that you've also divided this into training and test sets (`fisher_training_utterances.txt`, `fisher_test_utterances.txt`).
 - At the bottom of the notebook, you'll need three modules to process and export SRILM's results:
   - `funcy` and `numpy`
   - `probdist` a module from [another repository of mine](https://github.com/emeinhardt/wr), currently assumed to be located on the path `../wr/` relative to the current repository directory.
