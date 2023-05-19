# Home-Assistant Feller-Wiser Integration
Hier beschreibe ich den Weg zur Integration von Feller-Wiser in Home-Assistant.

## Requirements
- funktionierende Home-Assistant Installation. Ich bevorzuge hier die einfache Installation via Docker
- Zugriff auf den Feller-Wiser Gateway. Dieser msus sich dafür im Netzwerk befinden.

## die API
Ist grundsätzlich [hier](https://github.com/Feller-AG/wiser-api) zu finden. Die Dokumentation ist, wie ich finde, sehr gelungen.

Um die API freizuschalten und erste Tests zu machen, verwende ich [Postman](https://www.postman.com/downloads/). Dort kann die API Dokumentaiton direkt eingelesen werden.

1.  Folgende Datei von der Feller Github Seite herunterladen: https://github.com/Feller-AG/wiser-api/blob/main/docs/5.1.25/ugateway_openapi_domain_public.yaml hier die Versionsnummer beachten und gegebenenfalls anpassen.
2.  In Postman unter "Collections" die entsprechende Datei importieren:
![image](https://github.com/St0bsel/home-assistant-feller-wiser-rest-integration/assets/16537723/e40d95b6-6b08-4526-ae67-45d29f2e83bb)
3.  Nun sollte die API wie folgt importiert worden sein und die Variabeln können angepasst werden:
![image](https://github.com/St0bsel/home-assistant-feller-wiser-rest-integration/assets/16537723/3bf7d61a-df64-49b5-8948-07075db7fe06)
4.  Als Erstes muss nun die API freigeschaltet werden: Weitere Infos dazu finden sich auch im entsprechenden [Repo von Feller](https://github.com/Feller-AG/wiser-tutorial)
![image](https://github.com/St0bsel/home-assistant-feller-wiser-rest-integration/assets/16537723/be7a1c6e-f892-4411-acd1-3dda3a5c7e7b)
> Der Wert "source" muss nicht definiert werden. Sollte die Wiser Konfiguration aber bereits über die eSetup App durchgeführt worden sein, können damit die entsprechenden Daten übernommen werden. Dies macht es einfacher, Loads später zuzuordnen.
> Weitere Infos in [in meinem Issue](https://github.com/Feller-AG/wiser-api/issues/10)
Als Respone wird ein Token ausgegeben, das wie oben beschrieben unter den Variabeln beziehungsweise in jedem Request definiert werden muss.
5.  
