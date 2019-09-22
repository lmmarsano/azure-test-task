# Azure DevOps Custom Pipeline Task

[The tutorial example][tutorial] fails to build.

``` shellsession
$ cd azure-test-task
$ npm i
$ cd buildAndReleaseTask
$ npx tsc --noEmit
../node_modules/azure-pipelines-task-lib/internal.ts:4:28 - error TS7016: Could not find a declaration file for module 'minimatch'. '/home/LOM0227/project/azure-test-task/node_modules/minimatch/minimatch.js' implicitly has an 'any' type.
  Try `npm install @types/minimatch` if it exists or add a new declaration (.d.ts) file containing `declare module 'minimatch';`

4 import minimatch = require('minimatch');
                             ~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:8:25 - error TS7016: Could not find a declaration file for module 'semver'. '/home/LOM0227/project/azure-test-task/node_modules/semver/semver.js' implicitly has an 'any' type.
  Try `npm install @types/semver` if it exists or add a new declaration (.d.ts) file containing `declare module 'semver';`

8 import semver = require('semver');
                          ~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:30:10 - error TS7017: Element implicitly has an 'any' type because type 'typeof globalThis' has no index signature.

30     this.warning('Tasks require a new agent.  Upgrade your agent or node to 4.2.0 or later');
            ~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:56:31 - error TS7006: Parameter 'stdStream' implicitly has an 'any' type.

56 export function _setStdStream(stdStream): void {
                                 ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:60:31 - error TS7006: Parameter 'errStream' implicitly has an 'any' type.

60 export function _setErrStream(errStream): void {
                                 ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:209:34 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

209         return util.format.apply(this, [locString].concat(param));
                                     ~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:209:40 - error TS2345: Argument of type 'string[]' is not assignable to parameter of type '[any, ...any[]]'.
  Property '0' is missing in type 'string[]' but required in type '[any, ...any[]]'.

209         return util.format.apply(this, [locString].concat(param));
                                           ~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:724:44 - error TS2345: Argument of type 'string | undefined' is not assignable to parameter of type 'string'.
  Type 'undefined' is not assignable to type 'string'.

724                 _vault.storeSecret(envvar, process.env[envvar]);
                                               ~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:759:5 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_loaded"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_loaded' does not exist on type 'Global'.

759     global['_vsts_task_lib_loaded'] = true;
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:932:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_proxy_url"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_proxy_url' does not exist on type 'Global'.

932         global['_vsts_task_lib_proxy_url'] = proxyUrl;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:933:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_proxy_username"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_proxy_username' does not exist on type 'Global'.

933         global['_vsts_task_lib_proxy_username'] = proxyUsername;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:934:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_proxy_bypass"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_proxy_bypass' does not exist on type 'Global'.

934         global['_vsts_task_lib_proxy_bypass'] = proxyBypassHostsJson;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:935:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_proxy_password"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_proxy_password' does not exist on type 'Global'.

935         global['_vsts_task_lib_proxy_password'] = _exposeTaskLibSecret('proxy', proxyPassword || '');
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:938:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_proxy"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_proxy' does not exist on type 'Global'.

938         global['_vsts_task_lib_proxy'] = true;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:948:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert_ca"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert_ca' does not exist on type 'Global'.

948         global['_vsts_task_lib_cert_ca'] = ca;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:957:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert_clientcert"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert_clientcert' does not exist on type 'Global'.

957         global['_vsts_task_lib_cert_clientcert'] = clientCert;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:958:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert_key"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert_key' does not exist on type 'Global'.

958         global['_vsts_task_lib_cert_key'] = clientCertKey;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:959:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert_archive"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert_archive' does not exist on type 'Global'.

959         global['_vsts_task_lib_cert_archive'] = clientCertArchive;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:960:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert_passphrase"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert_passphrase' does not exist on type 'Global'.

960         global['_vsts_task_lib_cert_passphrase'] = _exposeTaskLibSecret('cert', clientCertPassword || '');
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:965:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_cert"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_cert' does not exist on type 'Global'.

965         global['_vsts_task_lib_cert'] = true;
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/internal.ts:970:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_skip_cert_validation"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_skip_cert_validation' does not exist on type 'Global'.

970         global['_vsts_task_lib_skip_cert_validation'] = skipCertValidation.toUpperCase() === 'TRUE';
            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:2:24 - error TS7016: Could not find a declaration file for module 'shelljs'. '/home/LOM0227/project/azure-test-task/node_modules/shelljs/shell.js' implicitly has an 'any' type.
  Try `npm install @types/shelljs` if it exists or add a new declaration (.d.ts) file containing `declare module 'shelljs';`

2 import shell = require('shelljs');
                         ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:7:28 - error TS7016: Could not find a declaration file for module 'minimatch'. '/home/LOM0227/project/azure-test-task/node_modules/minimatch/minimatch.js' implicitly has an 'any' type.
  Try `npm install @types/minimatch` if it exists or add a new declaration (.d.ts) file containing `declare module 'minimatch';`

7 import minimatch = require('minimatch');
                             ~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:11:25 - error TS7016: Could not find a declaration file for module 'semver'. '/home/LOM0227/project/azure-test-task/node_modules/semver/semver.js' implicitly has an 'any' type.
  Try `npm install @types/semver` if it exists or add a new declaration (.d.ts) file containing `declare module 'semver';`

11 import semver = require('semver');
                           ~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:91:9 - error TS7053: Element implicitly has an 'any' type because expression of type '"done"' can't be used to index type '{ 'result': string; }'.
  Property 'done' does not exist on type '{ 'result': string; }'.

91         properties['done'] = 'true';
           ~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:285:21 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

285     var pathValue = this.resolve(this.getPathInput(name) || '');
                        ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:285:34 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

285     var pathValue = this.resolve(this.getPathInput(name) || '');
                                     ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:286:20 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

286     var repoRoot = this.resolve(getVariable('build.sourcesDirectory') || getVariable('system.defaultWorkingDirectory') || '');
                       ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:335:5 - error TS2322: Type 'string | undefined' is not assignable to type 'string'.
  Type 'undefined' is not assignable to type 'string'.

335     return urlval;
        ~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:355:5 - error TS2322: Type 'string | undefined' is not assignable to type 'string'.
  Type 'undefined' is not assignable to type 'string'.

355     return dataParamVal;
        ~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:454:5 - error TS2322: Type 'string | undefined' is not assignable to type 'string'.
  Type 'undefined' is not assignable to type 'string'.

454     return name;
        ~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:721:43 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

721     var absolutePath = path.resolve.apply(this, pathSegments);
                                              ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:1239:30 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

1239     let tr: trm.ToolRunner = this.tool(tool);
                                  ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:1267:30 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

1267     let tr: trm.ToolRunner = this.tool(tool);
                                  ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:1508:34 - error TS2683: 'this' implicitly has type 'any' because it does not have a type annotation.

1508     defaultRoot = defaultRoot || this.getVariable('system.defaultWorkingDirectory') || process.cwd();
                                      ~~~~

../node_modules/azure-pipelines-task-lib/task.ts:1708:38 - error TS7006: Parameter 'bypassHost' implicitly has an 'any' type.

1708             proxyBypassHosts.forEach(bypassHost => {
                                          ~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:2106:10 - error TS7017: Element implicitly has an 'any' type because type 'typeof globalThis' has no index signature.

2106     this.warning('Tasks require a new agent.  Upgrade your agent or node to 4.2.0 or later');
              ~~~~~~~

../node_modules/azure-pipelines-task-lib/task.ts:2114:6 - error TS7053: Element implicitly has an 'any' type because expression of type '"_vsts_task_lib_loaded"' can't be used to index type 'Global'.
  Property '_vsts_task_lib_loaded' does not exist on type 'Global'.

2114 if (!global['_vsts_task_lib_loaded']) {
          ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:12:17 - error TS7006: Parameter 'command' implicitly has an 'any' type.

12     constructor(command, properties, message) {
                   ~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:12:26 - error TS7006: Parameter 'properties' implicitly has an 'any' type.

12     constructor(command, properties, message) {
                            ~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:12:38 - error TS7006: Parameter 'message' implicitly has an 'any' type.

12     constructor(command, properties, message) {
                                        ~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:54:35 - error TS7006: Parameter 'commandLine' implicitly has an 'any' type.

54 export function commandFromString(commandLine) {
                                     ~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:83:17 - error TS7053: Element implicitly has an 'any' type because expression of type 'string' can't be used to index type '{}'.
  No index signature with a parameter of type 'string' was found on type '{}'.

83                 properties[key] = unescape(val);
                   ~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:93:21 - error TS7006: Parameter 's' implicitly has an 'any' type.

93 function escapedata(s) : string {
                       ~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:99:23 - error TS7006: Parameter 's' implicitly has an 'any' type.

99 function unescapedata(s) : string {
                         ~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:105:17 - error TS7006: Parameter 's' implicitly has an 'any' type.

105 function escape(s) : string {
                    ~

../node_modules/azure-pipelines-task-lib/taskcommand.ts:113:19 - error TS7006: Parameter 's' implicitly has an 'any' type.

113 function unescape(s) : string {
                      ~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:578:9 - error TS2531: Object is possibly 'null'.

578         cpFirst.stdout.on('data', (data: Buffer) => {
            ~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:583:17 - error TS2531: Object is possibly 'null'.

583                 cp.stdin.write(data);
                    ~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:589:9 - error TS2531: Object is possibly 'null'.

589         cpFirst.stderr.on('data', (data: Buffer) => {
            ~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:604:13 - error TS2531: Object is possibly 'null'.

604             cp.stdin.end();
                ~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:621:13 - error TS2531: Object is possibly 'null'.

621             cp.stdin.end();
                ~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:632:9 - error TS2531: Object is possibly 'null'.

632         cp.stdout.on('data', (data: Buffer) => {
            ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:645:9 - error TS2531: Object is possibly 'null'.

645         cp.stderr.on('data', (data: Buffer) => {
            ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:812:9 - error TS2531: Object is possibly 'null'.

812         cp.stdout.on('finish', () => {
            ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:819:9 - error TS2531: Object is possibly 'null'.

819         cp.stdout.on('data', (data: Buffer) => {
            ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:833:9 - error TS2531: Object is possibly 'null'.

833         cp.stderr.on('data', (data: Buffer) => {
            ~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:951:5 - error TS2564: Property 'processClosed' has no initializer and is not definitely assigned in the constructor.

951     processClosed: boolean; // tracks whether the process has exited and stdio is closed
        ~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:952:5 - error TS2564: Property 'processError' has no initializer and is not definitely assigned in the constructor.

952     processError: string;
        ~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:953:5 - error TS2564: Property 'processExitCode' has no initializer and is not definitely assigned in the constructor.

953     processExitCode: number;
        ~~~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:954:5 - error TS2564: Property 'processExited' has no initializer and is not definitely assigned in the constructor.

954     processExited: boolean; // tracks whether the process has exited
        ~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:955:5 - error TS2564: Property 'processStderr' has no initializer and is not definitely assigned in the constructor.

955     processStderr: boolean; // tracks whether stderr was written to
        ~~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:957:13 - error TS2564: Property 'done' has no initializer and is not definitely assigned in the constructor.

957     private done: boolean;
                ~~~~

../node_modules/azure-pipelines-task-lib/toolrunner.ts:971:13 - error TS2322: Type 'number' is not assignable to type 'Timer | null'.

971             this.timeout = setTimeout(ExecState.HandleTimeout, this.delay, this);
                ~~~~~~~~~~~~

../node_modules/azure-pipelines-task-lib/vault.ts:70:23 - error TS2769: No overload matches this call.
  Overload 1 of 4, '(data: Binary, input_encoding: undefined, output_encoding: Utf8AsciiBinaryEncoding): string', gave the following error.
    Argument of type '"hex"' is not assignable to parameter of type 'undefined'.
  Overload 2 of 4, '(data: string, input_encoding: "hex" | "base64" | "binary" | undefined, output_encoding: Utf8AsciiBinaryEncoding): string', gave the following error.
    Argument of type 'Buffer' is not assignable to parameter of type 'string'.

70             var dec = decipher.update(encryptedText,encryptEncoding,unencryptedEncoding);
                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Found 65 errors.
```

[tutorial]: https://docs.microsoft.com/en-us/azure/devops/extend/develop/add-build-task
