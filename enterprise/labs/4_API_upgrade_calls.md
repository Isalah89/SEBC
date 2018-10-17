
API version

curl -u 'isalah89:cloudera' "http://n1.sebcdomain:7180/api/version"
v19




CM Version

curl -u 'isalah89:cloudera' "http://n1.sebcdomain:7180/api/v19/cm/version"
{
  "version" : "5.14.4",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20180707-0439",
  "gitHash" : "0971e84bdceb60db9b96533f46451f40ed8cbdf9",
  "snapshot" : false
}





 users

 curl -u 'isalah89:cloudera' "http://n1.sebcdomain:7180/api/v19/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "isalah89",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]




database  info
curl -u 'isalah89:cloudera' "http://n1.sebcdomain:7180/api/v19/cm/scmDbInfo"
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
