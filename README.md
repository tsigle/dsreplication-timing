# dsreplicaiton-timing Tool

```
Providing basic replication timing between multiple Ping Directory servers in
topology file.

Usage:  dsreplication-timing {options}

Available options include:

  LDAP Connection and Authentication Arguments

    -h, --hostname {host}
        The IP address or resolvable name to use to connect to the directory
        server.  If this is not provided, then a default value of 'localhost'
        will be used.
    -p, --port {port}
        The port to use to connect to the directory server.  If this is not
        provided, then a default value of 389 will be used.
    -D, --bindDN {dn}
        The DN to use to bind to the directory server when performing simple
        authentication.
    -w, --bindPassword {password}
        The password to use to bind to the directory server when performing
        simple authentication or a password-based SASL mechanism.
    -j, --bindPasswordFile {path}
        The path to the file containing the password to use to bind to the
        directory server when performing simple authentication or a
        password-based SASL mechanism.
    --promptForBindPassword
        Indicates that the tool should interactively prompt the user for the
        bind password.
    -Z, --useSSL
        Use SSL when communicating with the directory server.
    -q, --useStartTLS
        Use StartTLS when communicating with the directory server.
    -X, --trustAll
        Trust any certificate presented by the directory server.
    -K, --keyStorePath {path}
        The path to the file to use as the key store for obtaining client
        certificates when communicating securely with the directory server.
    -W, --keyStorePassword {password}
        The password to use to access the key store contents.
    -u, --keyStorePasswordFile {path}
        The path to the file containing the password to use to access the key
        store contents.
    --promptForKeyStorePassword
        Indicates that the tool should interactively prompt the user for the
        password to use to access the key store contents.
    --keyStoreFormat {format}
        The format (e.g., jks, jceks, pkcs12, etc.) for the key store file.
    -P, --trustStorePath {path}
        The path to the file to use as trust store when determining whether to
        trust a certificate presented by the directory server.
    -T, --trustStorePassword {password}
        The password to use to access the trust store contents.
    -U, --trustStorePasswordFile {path}
        The path to the file containing the password to use to access the trust
        store contents.
    --promptForTrustStorePassword
        Indicates that the tool should interactively prompt the user for the
        password to use to access the trust store contents.
    --trustStoreFormat {format}
        The format (e.g., jks, jceks, pkcs12, etc.) for the trust store file.
    -N, --certNickname {nickname}
        The nickname (alias) of the client certificate in the key store to
        present to the directory server for SSL client authentication.
    -o, --saslOption {name=value}
        A name-value pair providing information to use when performing SASL
        authentication.
    --useSASLExternal
        Use the SASL EXTERNAL mechanism to authenticate.
    --helpSASL
        Provide information about the supported SASL mechanisms, including the
        properties available for use with each.

  Other Arguments

  * --topologyFilePath topology.json
        Topology file from PingDirectory server
    --timingBaseDN ou=dsreplication-timing,dc=example,dc=com
        Topology file from PingDirectory server

  Usage Arguments

    --outputFile {path}
        Write all standard output and standard error messages to the specified
        file instead of to the console.
    --appendToOutputFile
        Indicates that the tool should append to the file specified by the
        --outputFile argument if it already exists.  If this argument is not
        provided and the output file already exists, it will be overwritten.
    --teeOutput
        Write all standard output and standard error messages to the console as
        well as to the specified output file.  The --outputFile argument must
        also be provided.
    -H, --help
        Display usage information for this program.
    --propertiesFilePath {path}
        The path to a properties file used to specify default values for
        arguments not supplied on the command line.
    --generatePropertiesFile {path}
        Write an empty properties file that may be used to specify default
        values for arguments.
    --noPropertiesFile
        Do not obtain any argument values from a properties file.
    --suppressPropertiesFileComment
        Suppress output listing the arguments obtained from a properties file.

  * Indicates the argument is required

Examples

  For each instance in the topology.json file, a modification and persistent
  search is created to monitor the timing of replicating the modifies.

    dsreplication-timing --topologyFilePath /path/to/topology.json \
         --timingBaseDN ou=dsreplication-timing,dc=example,dc=com \
         --bindDN cn=administrator
```
