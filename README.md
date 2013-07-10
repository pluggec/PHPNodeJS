PHPNodeJS
=========

PHP Node JS wrapper (PHP class that brings executing JavaScript inside PHP - wrapper for NodeJS CLI)

  `<?php`
  ` `
  `include_once dirname(__FILE__) . '/PHPNodeJS.php';`
  `$debug = true;`
  `$PHPNodeJS = new PHPNodeJS($debug);`

  Example 1 (run simple script without function)
  =========
  `$PHPNodeJS->run('`
  ` var var1 = 10;`
  ` var var2 = 20;`
  ` console.log(var1+var2);');`

  Example 2 (run simple script, supply multiple arguments to function you want to call)
  =========
  `$PHPNodeJS->run('`
  `function test(var1, var2) {`
  `  if (var1 == "3" && var2 == "20") {`
  `    return true;`
  `  } else {`
  `    return false;`
  `  }`
  `}', 'test', array('3', '20'));`

  Example 3 (run script that uses jQuery as dependcy)
  =========
  `echo $PHPNodeJS->run('function test(url) {`
  ` jQuery.get(url, function(data) {`
  `   console.log(data);`
  ` });`
  ` return "";`
  `}', 'test', array('http://www.videodeck.net'), true);`
