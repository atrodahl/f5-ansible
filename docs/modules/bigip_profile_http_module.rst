:source: bigip_profile_http.py

:orphan:

.. _bigip_profile_http_module:


bigip_profile_http - Manage HTTP profiles on a BIG-IP
+++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.7

.. contents::
   :local:
   :depth: 2


Synopsis
--------
- Manage HTTP profiles on a BIG-IP.




Parameters
----------

.. raw:: html

    <table  border=0 cellpadding=0 class="documentation-table">
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                    <tr>
            <th colspan="2">Parameter</th>
            <th>Choices/<font color="blue">Defaults</font></th>
                        <th width="100%">Comments</th>
        </tr>
                    <tr>
                                                                <td colspan="2">
                    <b>accept_xff</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Enables or disables trusting the client IP address, and statistics from the client IP address, based on the request&#x27;s XFF (X-forwarded-for) headers, if they exist.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>description</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Description of the profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>dns_resolver</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the name of a configured DNS resolver, this option is mandatory when <code>proxy_type</code> is set to <code>explicit</code>.</div>
                                                    <div>Format of the name can be either be prepended by partition (<code>/Common/foo</code>), or specified just as an object name (<code>foo</code>).</div>
                                                    <div>To remove the entry a value of <code>none</code> or <code>&#x27;&#x27;</code> can be set, however the profile <code>proxy_type</code> must not be set as <code>explicit</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>encrypt_cookie_secret</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Passphrase for cookie encryption.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>encrypt_cookies</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Cookie names for the system to encrypt.</div>
                                                    <div>To remove the entry completely a value of <code>none</code> or <code>&#x27;&#x27;</code> should be set.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>enforcement</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies protocol enforcement settings for the HTTP profile.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                                            <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>truncated_redirects</b>
                                                        </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies what happens if a truncated redirect is seen from a server.</div>
                                                    <div>If <code>yes</code>, the redirect will be forwarded to the client, otherwise the malformed HTTP will be silently ignored.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>excess_client_headers</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the behavior when too many client headers are received.</div>
                                                    <div>If set to <code>pass-through</code>, will switch to pass through mode, when <code>reject</code> the connection will be rejected.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>excess_server_headers</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the behavior when too many server headers are received.</div>
                                                    <div>If set to <code>pass-through</code>, will switch to pass through mode, when <code>reject</code> the connection will be rejected.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>oversize_client_headers</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the behavior when too-large client headers are received.</div>
                                                    <div>If set to <code>pass-through</code>, will switch to pass through mode, when <code>reject</code> the connection will be rejected.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>oversize_server_headers</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the behavior when too-large server headers are received.</div>
                                                    <div>If set to <code>pass-through</code>, will switch to pass through mode, when <code>reject</code> the connection will be rejected.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>pipeline</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>allow</li>
                                                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Enables HTTP/1.1 pipelining, allowing clients to make requests even when prior requests have not received a response.</div>
                                                    <div>In order for this to succeed, however, destination servers must include support for pipelining.</div>
                                                    <div>If set to <code>pass-through</code>, pipelined data will cause the BIG-IP to immediately switch to pass-through mode and disable the HTTP filter.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>unknown_method</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>allow</li>
                                                                                                                                                                                                <li>reject</li>
                                                                                                                                                                                                <li>pass-through</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies whether to allow, reject or switch to pass-through mode when an unknown HTTP method is parsed.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>max_header_count</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the maximum number of headers allowed in HTTP request/response.</div>
                                                    <div>The valid value range is between 16 and 4096 inclusive.</div>
                                                    <div>When set to <code>default</code> the value of this parameter will be <code>64</code></div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>max_header_size</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the maximum header size specified in bytes.</div>
                                                    <div>The valid value range is between 0 and 4294967295 inclusive.</div>
                                                    <div>When set to <code>default</code> the value of this parameter will be <code>32768</code> bytes</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>max_requests</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the number of requests that the system accepts on a per-connection basis.</div>
                                                    <div>The valid value range is between 0 and 4294967295 inclusive.</div>
                                                    <div>When set to <code>default</code> the value of this parameter will be <code>0</code>, which means the system will not limit the number of requests per connection.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>known_methods</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies which HTTP methods count as being known, removing RFC-defined methods from this list will cause the HTTP filter to not recognize them.</div>
                                                    <div>The default list provided with the system include: <code>CONNECT</code>, <code>DELETE</code>, <code>GET</code>, <code>HEAD</code>, <code>LOCK</code>, <code>OPTIONS</code>, <code>POST</code>, <code>PROPFIND</code>, <code>PUT</code>, <code>TRACE</code> ,<code>UNLOCK</code>. The list can be appended by by specifying <code>default</code> keyword as one of the list elements.</div>
                                                    <div>The <code>default</code> keyword can also be used to restore the default <code>known_methods</code> on the system.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                    
                                                <tr>
                                                                <td colspan="2">
                    <b>fallback_host</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies an HTTP fallback host.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>fallback_status_codes</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies one or more HTTP error codes from server responses that should trigger a redirection to the fallback host.</div>
                                                    <div>The accepted valid error codes are as defined by rfc2616.</div>
                                                    <div>The codes can be specified as individual items or as valid ranges e.g. <code>400-417</code> or <code>500-505</code>.</div>
                                                    <div>Mixing response code range across error types is invalid e.g. defining <code>400-505</code> will raise an error.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>header_erase</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The name of a header, in an HTTP request, which the system removes from request.</div>
                                                    <div>To remove the entry completely a value of <code>none</code> or <code>&#x27;&#x27;</code> should be set.</div>
                                                    <div>The format of the header must be in <code>KEY:VALUE</code> format, otherwise error is raised.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>header_insert</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>A string that the system inserts as a header in an HTTP request.</div>
                                                    <div>To remove the entry completely a value of <code>none</code> or <code>&#x27;&#x27;</code> should be set.</div>
                                                    <div>The format of the header must be in <code>KEY:VALUE</code> format, otherwise error is raised.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>hsts_mode</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>When set to <code>yes</code>, enables the HSTS settings.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>include_subdomains</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>When set to <code>yes</code>, applies the HSTS policy to the HSTS host and its sub-domains.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>insert_xforwarded_for</b>
                                                        </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>When specified system inserts an X-Forwarded-For header in an HTTP request with the client IP address, to use with connection pooling.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>maximum_age</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the maximum length of time, in seconds, that HSTS functionality requests that clients only use HTTPS to connect to the current host and any sub-domains of the current host&#x27;s domain name.</div>
                                                    <div>The accepted value range is <code>0 - 4294967295</code> seconds, a value of <code>0</code> seconds re-enables plaintext HTTP access, while specifying <code>indefinite</code> will set it to the maximum value.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>name</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the name of the profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>oneconnect_transformations</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Enables the system to perform HTTP header transformations for the purpose of keeping server-side connections open. This feature requires configuration of a OneConnect profile.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>parent</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">/Common/http</div>
                                    </td>
                                                                <td>
                                                                        <div>Specifies the profile from which this profile inherits settings.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is the system-supplied <code>http</code> profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>partition</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">Common</div>
                                    </td>
                                                                <td>
                                                                        <div>Device partition to manage resources on.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>provider</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.5)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>A dict object containing connection details.</div>
                                                                                </td>
            </tr>
                                                            <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>password</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The password for the user account used to connect to the BIG-IP.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_PASSWORD</code>.</div>
                                                                                        <div style="font-size: small; color: darkgreen"><br/>aliases: pass, pwd</div>
                                    </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>server</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The BIG-IP host.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_SERVER</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>server_port</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">443</div>
                                    </td>
                                                                <td>
                                                                        <div>The BIG-IP server port.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_SERVER_PORT</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>user</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The username to connect to the BIG-IP with. This user must have administrative privileges on the device.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_USER</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>validate_certs</b>
                                                        </td>
                                <td>
                                                                                                                                                                                                                    <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li><div style="color: blue"><b>yes</b>&nbsp;&larr;</div></li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>If <code>no</code>, SSL certificates are not validated. Use this only on personally controlled sites using self-signed certificates.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_VALIDATE_CERTS</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>timeout</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the timeout in seconds for communicating with the network device for either connecting or sending commands.  If the timeout is exceeded before the operation is completed, the module will error.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>ssh_keyfile</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the SSH keyfile to use to authenticate the connection to the remote device.  This argument is only used for <em>cli</em> transports.</div>
                                                    <div>You may omit this option by setting the environment variable <code>ANSIBLE_NET_SSH_KEYFILE</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>transport</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>cli</li>
                                                                                                                                                                                                <li><div style="color: blue"><b>rest</b>&nbsp;&larr;</div></li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Configures the transport connection to use when connecting to the remote device.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>auth_provider</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Configures the auth provider for to obtain authentication tokens from the remote device.</div>
                                                    <div>This option is really used when working with BIG-IQ devices.</div>
                                                                                </td>
            </tr>
                    
                                                <tr>
                                                                <td colspan="2">
                    <b>proxy_type</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>reverse</li>
                                                                                                                                                                                                <li>transparent</li>
                                                                                                                                                                                                <li>explicit</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the proxy mode for the profile.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>redirect_rewrite</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>none</li>
                                                                                                                                                                                                <li>all</li>
                                                                                                                                                                                                <li>matching</li>
                                                                                                                                                                                                <li>nodes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies whether the system rewrites the URIs that are part of HTTP redirect (3XX) responses.</div>
                                                    <div>When set to <code>none</code> the system will not rewrite the URI in any HTTP redirect responses.</div>
                                                    <div>When set to <code>all</code> the system rewrites the URI in all HTTP redirect responses.</div>
                                                    <div>When set to <code>matching</code> the system rewrites the URI in any HTTP redirect responses that match the request URI.</div>
                                                    <div>When set to <code>nodes</code> if the URI contains a node IP address instead of a host name, the system changes it to the virtual server address.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>request_chunking</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>rechunk</li>
                                                                                                                                                                                                <li>selective</li>
                                                                                                                                                                                                <li>preserve</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies how to handle chunked and unchunked requests.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>response_chunking</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>rechunk</li>
                                                                                                                                                                                                <li>selective</li>
                                                                                                                                                                                                <li>preserve</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies how to handle chunked and unchunked responses.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>server_agent_name</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.8)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the string used as the server name in traffic generated by BIG-IP.</div>
                                                    <div>To remove the entry completely a value of <code>none</code> or <code>&#x27;&#x27;</code> should be set.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>sflow</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies sFlow settings for the HTTP profile.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                                            <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>poll_interval</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the maximum interval in seconds between two pollings.</div>
                                                    <div>The valid value range is between 0 and 4294967295 seconds inclusive.</div>
                                                    <div>For this setting to take effect the <code>poll_interval_global</code> parameter must be set to <code>no</code>.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>poll_interval_global</b>
                                                        </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies whether the global HTTP poll-interval setting overrides the object-level Cpoll-interval setting.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>sampling_rate</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the ratio of packets observed to the samples generated. For example, a sampling rate of <code>2000</code> specifies that 1 sample will be randomly generated for every 2000 packets observed.</div>
                                                    <div>The valid value range is between 0 and 4294967295 packets inclusive.</div>
                                                    <div>For this setting to take effect the <code>sampling_rate_global</code> parameter must be set to <code>no</code>.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>sampling_rate_global</b>
                                                        </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Specifies whether the global HTTP sampling-rate setting overrides the object-level sampling-rate setting.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                    
                                                <tr>
                                                                <td colspan="2">
                    <b>state</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li><div style="color: blue"><b>present</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                                <li>absent</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>When <code>present</code>, ensures that the profile exists.</div>
                                                    <div>When <code>absent</code>, ensures the profile is removed.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>update_password</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li><div style="color: blue"><b>always</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                                <li>on_create</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div><code>always</code> will update passwords if the <code>encrypt_cookie_secret</code> is specified.</div>
                                                    <div><code>on_create</code> will only set the password for newly created profiles.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>xff_alternative_names</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.9)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies alternative XFF headers instead of the default X-forwarded-for header.</div>
                                                    <div>When creating a new profile, if this parameter is not specified, the default is provided by the parent profile.</div>
                                                                                </td>
            </tr>
                        </table>
    <br/>


Notes
-----

.. note::
    - For more information on using Ansible to manage F5 Networks devices see https://www.ansible.com/integrations/networks/f5.
    - Requires BIG-IP software version >= 12.
    - The F5 modules only manipulate the running configuration of the F5 product. To ensure that BIG-IP specific configuration persists to disk, be sure to include at least one task that uses the :ref:`bigip_config <bigip_config_module>` module to save the running configuration. Refer to the module's documentation for the correct usage of the module to save your running configuration.


Examples
--------

.. code-block:: yaml

    
    - name: Create HTTP profile
      bigip_profile_http:
        name: my_profile
        insert_xforwarded_for: yes
        redirect_rewrite: all
        state: present
        provider:
          user: admin
          password: secret
          server: lb.mydomain.com
      delegate_to: localhost

    - name: Remove HTTP profile
      bigip_profile_http:
        name: my_profile
        state: absent
        provider:
          server: lb.mydomain.com
          user: admin
          password: secret
      delegate_to: localhost

    - name: Add HTTP profile for transparent proxy
      bigip_profile_http:
        name: my_profile
        proxy_type: transparent
        provider:
          password: secret
          server: lb.mydomain.com
          user: admin
      delegate_to: localhost




Return Values
-------------
Common return values are documented `here <https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html>`_, the following are the fields unique to this module:

.. raw:: html

    <table border=0 cellpadding=0 class="documentation-table">
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                            <tr>
            <th colspan="2">Key</th>
            <th>Returned</th>
            <th width="100%">Description</th>
        </tr>
                    <tr>
                                <td colspan="2">
                    <b>accept_xff</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Enables or disables trusting the client IP address, and statistics from the client IP address.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>description</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Description of the profile.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">My profile</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>dns_resolver</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Configured dns resolver.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">/Common/FooBar</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>encrypt_cookies</b>
                    <br/><div style="font-size: small; color: red">list</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Cookie names to encrypt.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">[&#x27;MyCookie1&#x27;, &#x27;MyCookie2&#x27;]</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>enforcement</b>
                    <br/><div style="font-size: small; color: red">complex</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies protocol enforcement settings for the HTTP profile.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">hash/dictionary of values</div>
                                    </td>
            </tr>
                                                            <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>truncated_redirects</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies what happens if a truncated redirect is seen from a server.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>excess_server_headers</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the behavior when too many server headers are received.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">pass-through</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>oversize_client_headers</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the behavior when too-large client headers are received.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">reject</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>oversize_server_headers</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the behavior when too-large server headers are received.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">reject</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>pipeline</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Allows, rejects or switches to pass-through mode when dealing with pipelined data.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">allow</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>unknown_method</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Allows, rejects or switches to pass-through mode when an unknown HTTP method is parsed.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">allow</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>max_header_count</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The maximum number of headers allowed in HTTP request/response.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">4096</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>max_header_size</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The maximum header size specified in bytes.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">default</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>max_requests</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The number of requests that the system accepts on a per-connection basis.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">default</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>known_methods</b>
                    <br/><div style="font-size: small; color: red">list</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The list of known HTTP methods.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">[&#x27;default&#x27;, &#x27;FOO&#x27;, &#x27;BAR&#x27;]</div>
                                    </td>
            </tr>
                    
                                                <tr>
                                <td colspan="2">
                    <b>fallback_host</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies an HTTP fallback host.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">foobar.com</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>fallback_status_codes</b>
                    <br/><div style="font-size: small; color: red">list</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>HTTP error codes from server responses that should trigger a redirection to the fallback host.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">[&#x27;400-404&#x27;, &#x27;500&#x27;, &#x27;501&#x27;]</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>header_erase</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The name of a header, in an HTTP request, which the system removes from request.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">FOO:BAR</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>header_insert</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The string that the system inserts as a header in an HTTP request.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">FOO:BAR</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>hsts_mode</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Enables the HSTS settings.</div>
                                        <br/>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>include_subdomains</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Applies the HSTS policy to the HSTS host and its sub-domains.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>insert_xforwarded_for</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Insert X-Forwarded-For-Header.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>maximum_age</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The maximum length of time, in seconds, that HSTS functionality requests that clients only use HTTPS.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">indefinite</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>oneconnect_transformations</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Enables or disables HTTP header transformations.</div>
                                        <br/>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>parent</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the profile from which this profile inherits settings.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">/Common/http</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>proxy_type</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specify proxy mode of the profile.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">explicit</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>redirect_rewrite</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Rewrite URI that are part of 3xx responses.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">all</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>request_chunking</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies how to handle chunked and unchunked requests.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">rechunk</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>response_chunking</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies how to handle chunked and unchunked responses.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">rechunk</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>server_agent_name</b>
                    <br/><div style="font-size: small; color: red">str</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>The string used as the server name in traffic generated by BIG-IP.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">foobar</div>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="2">
                    <b>sflow</b>
                    <br/><div style="font-size: small; color: red">complex</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies sFlow settings for the HTTP profile.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">hash/dictionary of values</div>
                                    </td>
            </tr>
                                                            <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>poll_interval</b>
                    <br/><div style="font-size: small; color: red">int</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the maximum interval in seconds between two pollings.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">30</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>poll_interval_global</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Enables/Disables overriding HTTP poll-interval setting.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>sampling_rate</b>
                    <br/><div style="font-size: small; color: red">int</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies the ratio of packets observed to the samples generated.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">2000</div>
                                    </td>
            </tr>
                                <tr>
                                    <td class="elbow-placeholder">&nbsp;</td>
                                <td colspan="1">
                    <b>sampling_rate_global</b>
                    <br/><div style="font-size: small; color: red">bool</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Enables/Disables overriding HTTP sampling-rate setting.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">True</div>
                                    </td>
            </tr>
                    
                                                <tr>
                                <td colspan="2">
                    <b>xff_alternative_names</b>
                    <br/><div style="font-size: small; color: red">list</div>
                </td>
                <td>changed</td>
                <td>
                                            <div>Specifies alternative XFF headers instead of the default X-forwarded-for header.</div>
                                        <br/>
                                            <div style="font-size: smaller"><b>Sample:</b></div>
                                                <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">[&#x27;FooBar&#x27;, &#x27;client1&#x27;]</div>
                                    </td>
            </tr>
                        </table>
    <br/><br/>


Status
------



This module is **preview** which means that it is not guaranteed to have a backwards compatible interface.




Author
~~~~~~

- Wojciech Wypior (@wojtek0806)

