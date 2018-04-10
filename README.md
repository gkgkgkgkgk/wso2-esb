
<h1>Accessing backend SOAP services via WSO2 EI/ESB<//h1>

<h2>Mock backend server</h2>

open file SampleShop-soapui-project.xml in SoapUI and start mock service

<h2>Accessing Via REST Client</h2>

<h4>Success cases</h4>

192.168.1.212:8280/shopapi/search?text=vegetables <br/>
192.168.1.212:8280/shopapi/search?text=fruits

<h4>Failure cases</h4>

192.168.1.212:8280/shopapi/search?text=electronics

<h2>Accessing Via SOAP Client</h2>

URL - http://192.168.1.212:8280/services/ShopProxy

set content-type header as application/xml

<h4>Success cases</h4>
<pre><code class="xml">
                &lt;m0:search xmlns:m0="http://www.soapui.org/sample/" xmlns="">
                   &lt;sessionid>ABCD123&lt;/sessionid>
                   &lt;searchstring>fruits&lt;/searchstring>
                &lt;/m0:search>
</code></pre>

<pre><code class="xml">
                &lt;m0:search xmlns:m0="http://www.soapui.org/sample/" xmlns="">
                   &lt;sessionid>ABCD123&lt;/sessionid>
                   &lt;searchstring>vegetables&lt;/searchstring>
                &lt;/m0:search>
</code></pre>

<h4>Failure cases</h4>
<pre><code class="xml">
                &lt;m0:search xmlns:m0="http://www.soapui.org/sample/" xmlns="">
                   &lt;sessionid>ABCD123&lt;/sessionid>
                   &lt;searchstring>electronics&lt;/searchstring>
                &lt;/m0:search>
</code></pre>
