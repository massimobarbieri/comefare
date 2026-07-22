# Override
## Cookie banner
Il cookie banner è stato aggiunto nel file di override ``layout/partials/extend-head.html`` seguendo la guida pubblicata qui: https://discourse.gohugo.io/t/cookie-consent-script-display-banner-and-autoblock-tracking-tags-with-1-line-code-for-gdpr-ccpa/32239

Se dopo un upgrade di blowfish, si rompano gli override occorre mettere mano a questo file. Tuttavia la forma *extend* dovremme semplicemente aggiungere un include al file originale.

Il sorgente del js è qui: https://cdn.jsdelivr.net/gh/sprucejoy/cookie-consent-autoblock-gdpr/

Il file è pubblicato con licenza MIT

il codice aggiunto dell'head è il seguente:
```
<!--- START cookie consent code --->
    <script>
  window.__SJ_MESSAGE__ =
    'Per offrirti la migliore esperienza utente possibile, questo sito web utilizza i cookie. Continuando a navigare su questo sito, acconsenti all`utilizzo dei cookie.'
  window.__SJ_ACCEPT_BTN_TEXT__ = 'Accetta'
  window.__SJ_REJECT_BTN_TEXT__ = 'Rifiuta'
  window.__SJ_BAR_CLR__ = '#e74725'
</script>
  
    <script
      src="/js/cookie-consent.js"
      crossorigin="anonymous"
    ></script>
<!--- END cookie consent code --->
```

## Bug sulla lingua
Nell'ultima versione di Blowfish c'è un bug di traduzione causato da un apostrofo. Creato un file di override per risolvere questo problema. Il file si trova nella cartella i18n
