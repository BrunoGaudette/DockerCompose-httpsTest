# DockerCompose-httpsTest
Simple solution to test docker-compose communication between containers through https.
The solution was build on Windows with Visual Studio 2019 v16.7.1

#How-to
Run docker-compose.
The MVC website sould start. On the home page, enter the URL of the API to connect to and hit "Submit Request".

The APi is exposed on ports 8086:80 and 44386:443.

http://host.docker.internal:8086/WeatherForecast
https://host.docker.internal:44386/WeatherForecast

#Expected results
The call should work either through http and https

#Actual results
The call works on http, but fail on https

>AuthenticationException: The remote certificate is invalid according to the validation procedure.
>System.Net.Security.SslStream.StartSendAuthResetSignal(ProtocolToken message, AsyncProtocolRequest asyncRequest, ExceptionDispatchInfo exception)

>HttpRequestException: The SSL connection could not be established, see inner exception.
>System.Net.Http.ConnectHelper.EstablishSslConnectionAsyncCore(Stream stream, SslClientAuthenticationOptions sslOptions, CancellationToken cancellationToken)>

#Question
How can we trust the certificate for https development environment.

