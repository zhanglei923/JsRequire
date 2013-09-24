About
=======
JsRequire is a agilor js dependent loading util.

Browser Support: IE6+, FireFox, Chrome, Opera, Safari and more.

License
=======
MIT: [http://www.opensource.org/licenses/mit-license.php](http://www.opensource.org/licenses/mit-license.php)


How to use:
=======
Download and include into your page:

        <script src="/jsrequire-latest.min.js"></script>


API
=======

### Define dependence defination and load them:

        jsrequire.define({
                 script: {
                        'step1':'step1.js'
                        ,'step2':'step2.js'
                        ,'step3':'step3.js'
                        ,'step4':'step4.js'
                        ,'step5':'step5.js'
                }
                ,dependents: {
                        'step5': ['step4']
                        ,'step4': ['step2', 'step3']
                        ,'step2': ['step1']
                }
                ,css: [
                        'stylesheet1.css'
                        ,'stylesheet2.css'
                        ,'stylesheet3.css'
                ]
        });
        jsrequire.ready(['step5'], function (){
        	console.debug('done!');
        });


### another way:


        jsrequire.load('script1.js');
        jsrequire.load('script2.js');
        jsrequire.load('script3.js');
        //
        jsrequire.load('stylesheet1.css');
        jsrequire.load('stylesheet2.css');
        jsrequire.load('stylesheet3.css');
        
        jsrequire.ready(function (){
        	console.debug('done!');
        });
        
### or you can do it like this:

        jsrequire.load('a.js').load('b.js').load('c.js').load('d.js').ready(function (){
        	console.debug('done!');
        });
