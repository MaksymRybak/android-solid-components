non mi ricordo l'origine di questo progetto, un tutorial su youtube / corso pluralsight..
scrivo qui i dettagli di progetto.

il progetto non si builda con Android Studio, non sto a perdere il tempo per capire il motivo.
componenti UI usati: RecyclerView, Toolbar, SwipeRefreshLayout
a SwipeRefreshLayout e' agganciato un listener per recuperare i dati dalla rete usando la libreria Volley
	richiesta GET per recuperare un array di oggetti JSON
	i dati sono scritti e letti localmente in FileOutputStream (aka internal storage)
	JSON array viene mappato in una lista di oggetti Model (mapping automatico usando com.fasterxml.jackson.databind.ObjectMapper)
	dopo array di oggetti viene elaborato in un Task assincrono - in questo Task si prepara un'altra lista di oggetti per caricarli 
	in un RecyclerView, visualizzando i dati solo quello che ci servono
controllo se l'app ha il permesso alla LOCATION (ACCESS_FINE_LOCATION)
usato mGoogleApiClient per recuperare la location corrente (coordinate)

	
	