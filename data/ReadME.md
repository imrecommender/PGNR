### Data Explaination
#### train folder: 
- train_infor_his
  - JSON file for user clicked history
  - format: {user id: LIST[clicked articles' textual content]}
  - example: {'2': ["newscrime 'Habitual stowaway' arrested again at O'Hare, Chicago police say",
              'newsus Search resumes for worker missing in New Orleans Hard Rock Hotel building site collapse that killed 2',
              'newscrime Coroner IDs man found dead in Klondike neighborhood']}
  - USAGE: line 27 in pretrain_data.py

- train_interaction
  - format: LIST[(user id, clicked/positive news id, non-clicked/negative news id)] for training using negative sampling
  - example: [('663', 'N52471', 'N63106'),
 ('18131', 'N53585', 'N63550')]
  - USAGE: line 31 in pretrain_data.py

#### val folder: 
- val_id_history 
  - JSON file for user clicked history
  - format: {user id: LIST[historical clicked article ids]}
  - example: {'U80234': ['N55189',
                        'N46039',
                        'N51741',
                        'N53234']}
  - USAGE: line 292 in pretrain_data.py

- val_interaction
  - format: LIST[(raw user id, impression id, item id, ground truth)] 
  - example: [('U80234', 1, 'N28682', 'no'),
               ('U80234', 1, 'N48740', 'no')]
  - USAGE: line 295 in pretrain_data.py

#### test folder: 
- test_interaction
  - same format as val_interaction
- test_infor_his
  - same format as train_infor_his
- USAGE: line 292 & 295 in pretrain_data.py
    
#### news_infor: 
- format: JSON file for news id and textual content matching
- example: {'N55528': 'lifestyleroyals The Brands Queen Elizabeth, Prince Charles, and Prince Philip Swear By',
 'N19639': 'weightloss 50 Worst Habits For Belly Fat'}
- USAGE: line 34 & 298 in pretrain_data.py

## Note: 
The original MIND news dataset can be downloaded from https://msnews.github.io and can be processed to the expected format

