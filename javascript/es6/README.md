\# Promise

\`\`\`js

/\*\*

\* 1. 在正确信息的回调中使用throw进入错误信息捕获

\* 2. 在错误信息的回调中使用return进入正确信息捕获

\* 

\* success -&gt; return -&gt; success

\* success -&gt; throw -&gt; success

\* failure -&gt; return -&gt; success

\* failure -&gt; throw -&gt; failure

\*/

new Promise\(res =&gt; {

    setTimeout\(\(\) =&gt; {

        let r = 'res';

        console.log\(r\);//res

        res\(r\);

    }, 500\);

}\).then\(r =&gt; {

    r = r + ' -&gt; then';//res -&gt; then

    console.log\(r\);

    return r;

}\).then\(r =&gt; {

    r = r + ' -&gt; then';

    console.log\(r\);//res -&gt; then -&gt; then

    // throw 不会进入下一个then的第一个回调

    throw r;

}\).then\(r =&gt; {

    r = r + ' -&gt; then';

    console.log\(r\);//不会执行

    return r;

}\).then\(\(\)=&gt;{}, rej =&gt; {

    rej = rej + ' -&gt; rej';

    console.log\(rej\);//res -&gt; then -&gt; then -&gt; rej

    // return 会进入下一个then的第一个回调

    return rej;

}\).then\(r =&gt; {

    r = r + ' -&gt; then';//res -&gt; then -&gt; then -&gt; rej -&gt; then

    console.log\(r\);

    return r;

}, rej =&gt; {

    rej = rej + ' -&gt; rej';

    console.log\(rej\);//不会执行

    return r;

}\).catch\(e =&gt; {

    e = e + ' -&gt; catch';

    console.log\(e\);//不会执行

    return e;

}\).then\(r =&gt; {

    r = r + ' -&gt; then';//res -&gt; then -&gt; then -&gt; rej -&gt; then -&gt; then

    console.log\(r\);

    throw r;

}\).catch\(e =&gt; {

    e = e + ' -&gt; catch';

    console.log\(e\);//res -&gt; then -&gt; then -&gt; rej -&gt; then -&gt; then -&gt; catch

    return e;

}\)

\`\`\`

