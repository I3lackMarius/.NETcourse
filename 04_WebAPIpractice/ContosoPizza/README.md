Nome -- Descrizione
Controllers/ -- Contiene le classi con i metodi pubblici esposti come endpoint HTTP.
Program.cs -- Configura i servizi e la pipeline di richieste HTTP dell'app e contiene il punto di ingresso gestito dell'app.
ContosoPizza.csproj -- Contiene i metadati di configurazione per il progetto.
ConosoPizza.http -- Contiene la configurazione per testare le API REST direttamente da Visual Studio Code.

Compilare e testare l'API Web
Eseguire il comando seguente dell'interfaccia della riga di comando di .NET Core nella shell dei comandi:

CLI .NET

Copia
dotnet run
Il comando precedente:

Individua il file di progetto nella directory corrente.
Recupera e installa tutte le dipendenze di progetto necessarie per questo progetto.
Compila il codice del progetto.
Ospita l'API con server Web Kestrel di ASP.NET Core su un endpoint HTTP e HTTPS.
Quando viene creato il progetto, viene selezionata una porta compresa tra 5000 e 5300 per HTTP e una porta compresa tra 7000 e 7300 per HTTPS. È possibile cambiare facilmente le porte usate durante lo sviluppo mediante la modifica del file launchSettings.json del progetto. Questo modulo usa l'URL sicuro localhost che inizia con https.

L'output dovrebbe essere simile al seguente, a indicare che l'app è in esecuzione:

Console

Copia
Building...
info: Microsoft.Hosting.Lifetime[14]
Now listening on: https://localhost:7294
info: Microsoft.Hosting.Lifetime[14]
Now listening on: http://localhost:5118
info: Microsoft.Hosting.Lifetime[0]
Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
Hosting environment: Development  
Se si esegue questa app nel proprio computer, è possibile indirizzare un browser al collegamento HTTPS visualizzato nell'output (nel caso precedente, https://localhost:7294) per visualizzare la pagina risultante. Occorre ricordare questa porta, perché viene usata nell'intero modulo quando si usa {PORT}.

Importante

Controllare l'output del terminale se si verifica un comportamento imprevisto. Se la compilazione non riesce o si verificano altri errori, le informazioni del file di log sono utili per risolvere i problemi. Quando si apportano modifiche al codice, sarà necessario arrestare l'API Web premendo i tasti CTRL+C ed eseguendo di nuovo il comando dotnet run.

Aprire un Web browser e passare a:

Bash

Copia
https://localhost:{PORT}/weatherforecast
L'output JSON visualizzato dovrebbe essere simile all'esempio seguente:

JSON

Copia
[
{
"date": "2021-11-09T20:36:01.4678814+00:00",
"temperatureC": 33,
"temperatureF": 91,
"summary": "Scorching"
},
{
"date": "2021-11-09T20:36:01.4682337+00:00",
"temperatureC": -8,
"temperatureF": 18,
"summary": "Cool"
},
// ...
]
