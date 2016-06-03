# udcli

A nodejs urban dictionary cli.

    git clone https://github.com/panther-js/udcli.git
    cd udcli

#### Example

    node index lgtm
    
    An acronym for "Looks Good To Me", often used as a quick response after reviewing someone's essay, 
    code, or design document.

#### Full source code

```
'use strict';

let roi = require('roi');

if (process.argv.length === 3) {

  let url = '/v0/define?term=' + process.argv[2];
  let opts = { host: 'api.urbandictionary.com' };

  roi(opts).get(url)
    .then(d => console.log(d.list[0].definition))
    .catch(e => console.log(e));

} else {
  console.log('Usage: node index search_term_here');
}
```
