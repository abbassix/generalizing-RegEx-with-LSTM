# generalizing-RegEx-with-LSTM
I tried to teach an LSTM to learn how to generalize the pattern from a list of strings and put out the corresponding RegEx

regex_generator function, creates random RegExes. For example, y = [regex_generator(length=5, nails_length=2) for _ in range(3)] will generate ['g[ph]jyikl', 'd[lv]ipy[vc]c', 'f[ht]xa'].

Then regex_decoder function will generate some samples for the generated RegExes. For example, X = [list(set([regex_decoder(regex) for _ in range(100)])) for regex in y] will generate [['gpjyikl', 'ghjyikl'], ['dvipyvc', 'dlipycc', 'dvipycc', 'dlipyvc'], ['fhxa', 'ftxa']].

Then we will train an LSTM using X as input and y as target.
