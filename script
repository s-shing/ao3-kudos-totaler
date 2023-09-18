javascript: (() => {
    var words = 0;
    var matches = document.querySelectorAll("dd.words");
    for (var x in matches) {
        if ((matches[x]).innerText != undefined) {
            words += parseInt((matches[x]).innerText.replace(",", ""));
        }
    }
    var doc = document;
      async function caller(doc) {
        
              var pages =  document.querySelectorAll("dd.words")
                 setTimeout(() => {
                    try{
                    const fetcher =  doc.querySelectorAll("li.next > a")[0].getAttribute('href');
                    console.log(fetcher);
                     fetch("https://archiveofourown.org" + fetcher).then(res => res.text()).then((responseText) => {
                        const doc = new DOMParser().parseFromString(responseText, 'text/html');
                        matches = doc.querySelectorAll("dd.words");
                        for (var x in matches) {
                            if ((matches[x]).innerText != undefined) {
                                words += parseInt((matches[x]).innerText.replace(",", ""));
                            }
                        }
                        caller(doc);
                    })
                 }
                
             catch(err) {
               
               console.log("total word count:" + words);
                window.alert("total word count: " + words);
            }}, 1500);  
        }
caller(doc);        
    
})();
