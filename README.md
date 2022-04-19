# ngram_scraper
This ngram scraper uses the web inteface for Google Ngrams to extract basic chart data to create your own plots. The Google Ngrams dataset is very large, and although there are options for interrogating and iterating over those files using Python, this script assumes that the user will have performed a search on the web first. Details of this process are set out on the following website: https://www.geeksforgeeks.org/scrape-google-ngram-viewer-using-python/ 

## Obtaining Google Ngram data
A simple way to obtain the basic data for an ngram plot is to alter the URL. For example, https://books.google.com/ngrams/graph?content=Tom+Peters&year_start=1800&year_end=2019&corpus=26&smoothing=3&direct_url=t1%3B%2CTom%20Peters%3B%2Cc0 would become https://books.google.com/ngrams/json?content=Tom+Peters&year_start=1800&year_end=2019&corpus=26&smoothing=3&direct_url=t1%3B%2CTom%20Peters%3B%2Cc0 

This should provide the following data:
[{"ngram": "Tom Peters", "parent": "", "type": "NGRAM", "timeseries": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.815494738670915e-10, 1.815494738670915e-10, 1.815494738670915e-10, 3.2507255617478647e-10, 3.2507255617478647e-10, 4.4771345361230685e-10, 4.4771345361230685e-10, 2.6616397974521533e-10, 2.6616397974521533e-10, 2.6616397974521533e-10, 1.2264089743752038e-10, 1.2264089743752038e-10, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 3.9677991051486773e-10, 2.3996197092860226e-09, 2.3996197092860226e-09, 2.3996197092860226e-09, 3.05650270173073e-09, 3.418758831585933e-09, 3.418758831585933e-09, 3.0219789210710654e-09, 1.4257518657753314e-09, 1.989876105160501e-09, 1.989876105160501e-09, 1.8434300752545596e-09, 1.4811739453993562e-09, 1.4811739453993562e-09, 1.6378679999564027e-09, 1.3339357951558384e-09, 7.698115557706688e-10, 7.698115557706688e-10, 5.974797878671723e-10, 6.895923197548979e-10, 8.341261173835538e-10, 8.276926604417716e-10, 9.619110032309054e-10, 1.0995359464186345e-09, 1.4292283467831624e-09, 1.1491999732779083e-09, 1.5226612748442392e-09, 1.6474367505102195e-09, 1.4971761528949555e-09, 1.3513286362914251e-09, 1.213703693103696e-09, 1.1369666953951553e-09, 1.2053741021184855e-09, 7.398002686644287e-10, 4.704909953697925e-10, 6.212411537579296e-10, 1.0935675777621968e-09, 1.1708585053885452e-09, 1.2300775160361305e-09, 1.3636968935034792e-09, 1.4015472790277324e-09, 1.6688898715358898e-09, 1.5911347755232746e-09, 1.0277569866585473e-09, 9.850056762302932e-10, 8.72147572415573e-10, 7.372186948208435e-10, 9.096008866750691e-10, 8.890043463288017e-10, 1.0604954454278876e-09, 1.1765732435950076e-09, 1.2800487178158244e-09, 1.0807324083269724e-09, 1.0344490978094915e-09, 1.0552815605484917e-09, 9.57851686855804e-10, 3.7689096605524645e-09, 4.0667332834587455e-09, 3.971437995924682e-09, 4.36600983144686e-09, 4.371082971767391e-09, 5.327170910745289e-09, 5.546380069506743e-09, 4.3791324376231594e-09, 4.119402787137818e-09, 4.145863874427391e-09, 3.922923763610697e-09, 4.636575782043398e-09, 3.5638761386458384e-09, 3.270995522061274e-09, 1.5934314978593989e-09, 6.0267149683466775e-09, 6.414235674347322e-09, 8.190356765818457e-09, 7.49699573849532e-09, 7.500275242148088e-09, 7.581559134463487e-09, 9.016125663523816e-09, 7.125279580641067e-09, 7.048718918069495e-09, 5.337043307296341e-09, 5.293366931288393e-09, 5.504646242794818e-09, 5.852059499687558e-09, 4.657574385692951e-09, 2.23093321197584e-09, 2.0930615296510524e-09, 2.0170842734185915e-09, 2.7818022012888424e-09, 2.732664332911432e-09, 3.643014065016611e-09, 3.410634267072713e-09, 3.2277122324104415e-09, 3.1365750869610007e-09, 3.3660918576293243e-09, 2.5648091706020892e-09, 2.5435475749434134e-09, 1.228541819862729e-09, 1.1224334675993423e-09, 1.1674335268338103e-09, 1.421776438644987e-09, 1.3277617695793354e-09, 1.6021567802607502e-09, 1.471432190377645e-09, 1.4957193182420424e-09, 1.5490227830586685e-09, 1.71121581983767e-09, 1.4106312308724357e-09, 1.1150291800987588e-09, 9.390334700297232e-10, 8.652980950810526e-10, 8.483770352896158e-10, 2.3820152199911196e-09, 2.1507453120049392e-09, 2.0783591930806367e-09, 2.2400489974832335e-09, 2.5036283621667923e-09, 2.732727379701443e-09, 2.8791645833343385e-09, 1.4632926874171203e-09, 1.8834239981105736e-09, 3.0638913787025703e-09, 3.0431653863516317e-09, 2.814766071017922e-09, 2.644736525019604e-09, 2.5417197394414106e-09, 2.3993330021200775e-09, 2.1624776096779944e-09, 1.124212580170893e-09, 1.1529084195264057e-09, 1.2435917692446959e-09, 1.66723587316905e-09, 1.8264940988237705e-09, 1.870678659595829e-09, 1.7509065705237754e-09, 1.781313231839578e-09, 2.0790230568858347e-09, 2.205690400166763e-09, 1.933749279750937e-09, 1.985460391334166e-09, 2.203473046881653e-09, 2.5705074735427047e-09, 2.6635172321677813e-09, 2.5703158490486544e-09, 2.901692299138249e-09, 3.5953416117300615e-09, 4.66518347762092e-09, 6.8746949085810425e-09, 1.268273118272743e-08, 1.9846594431375105e-08, 2.8687705798193164e-08, 3.9248070254111715e-08, 5.144322225346189e-08, 6.472166142706165e-08, 7.784945107606031e-08, 8.661285783822287e-08, 9.60091637937564e-08, 1.0511053716300012e-07, 1.1177029892093873e-07, 1.1576564519698098e-07, 1.1843710317244976e-07, 1.192939831997007e-07, 1.1805221841346533e-07, 1.159977399213728e-07, 1.1124554788466412e-07, 1.0609155103631046e-07, 1.0034011767499709e-07, 9.442126521922286e-08, 9.132684246943817e-08, 8.902930862372419e-08, 8.991500115891021e-08, 8.812719341579265e-08, 8.82138085752818e-08, 8.873025641215853e-08, 8.864413558740125e-08, 8.504789812085229e-08, 8.216685338473845e-08, 7.4348253268194e-08, 6.935188677305502e-08, 6.392526482760072e-08, 5.792364835396516e-08, 5.200779438853585e-08, 4.7175704866374094e-08, 4.495294743852204e-08, 4.292426822871676e-08, 4.178983381564194e-08]}]

When you have obtained the JSON data, you can copy and paste this into the Python script.
