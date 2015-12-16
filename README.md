# angular-fancytree
Simple angular directive for quick fancytree inclusion

# HOWTO

download it:
```
bower install angular-fancytree
```

include it:
```
<script src="bower_components/angular-fancytree/dist/angular-fancytree.min.js"></script>
```
```
(function() {
    'use strict';

    angular
        .module('exampleApp', [
            'angular-fancytree'
        ]);
})();
```


include dependencies:
```
<script src="bower_components/jquery/dist/jquery.min.js"></script>
<script src="bower_components/jquery-ui/jquery-ui.min.js"></script>
<script src="bower_components/jquery.fancytree/dist/jquery.fancytree.min.js"></script>
<!-- your fav theme: -->
<link rel="stylesheet" href="bower_components/jquery.fancytree/dist/skin-bootstrap-n/ui.fancytree.min.css">
```

use it:
* in your controller (inject fancytreeFactory and set Your data):
```
(function () {
    'use strict';

    angular
        .module('yourModule')
        .controller('ExampleController', ExampleController);

    ExampleController.$inject = ['fancytreeFactory'];

    /* @ngInject */
    function ExampleController(fancytreeFactory) {

        fancytreeFactory.setData([
            {title: "Node 1", key: "1"},
            {title: "Folder 2", key: "2", folder: true, children: [
                {title: "Node 2.1", key: "3", myOwnAttr: "abc"},
                {title: "Node 2.2", key: "4"}
            ]}
        ]);
    }

})();
```

* in your template:
```
<angular-fancytree></angular-fancytree>
```

I will be working on it, I promise!
