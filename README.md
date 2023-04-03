
# Prvi domaći iz IIU

Ovde smo pokušali da rekreiramo rad pametnog uređaja za merenje temperature u prostorijama zgrade


## API Reference

#### Unos temperature za svaku sobu

```http
  POST /api/temperature
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `room` | `string` | Unos id od sobe |
| `temperature` | `string` | Unos temperature za tu sobu |
| `date` | `string` | Opcinoni unos datuma, ako ne unesemo uzima trenutno vreme, ako unosimo datum mora po sledećem formatu: dan/mesec/godina sat:minut:sekunda |

#### Kreiraj sobu

```http
  POST /api/room
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `name`      | `string` | After creating room, generates unique id for that specific room 


#### Vraćanje prosečne temperature i broj dana izmerenih

```http
  GET /api/average
```

Vraća prosečnu i broj dana izmerenih




## Run Locally

Clone the project

```bash
  git clone https://github.com/zeca19/iiu_prvi_domaci.git
```

Go to the project directory

```bash
  cd iiu_prvi_domaci
```

Install dependencies

```bash
  python -m venv (ime_virtualnog_okruzenja)
  source ./(ime_virtualnog_okruzenja)/Scripts/activate
  pip install -r requirements.txt
```

Before you run commands for running the server 

 First you need to make a account on elephantsql URL:https://www.elephantsql.com/.
 
 Then you need to get the api_key from your account and put in the .env.example file and change the file name to .env 

Start the server

```bash
  flask --app hello run
```


## Screenshots

Prilikom kreiranja sobe potrebno je samo uneti naziv sobe i povratna informacija dole treba da ispiše da li je soba kreirana i sačuvana ili je došlo do problema

![Kreiranje sobe](./images/iiu_domaci_1)


Nakon toga idemo na unos temperature

Ovde je potrebno da unesemo id sobe za koju unosimo temperaturu i temperaturu za tu sobu.Datum je opcioni parametar, ako ga stavimo onda gleda taj datum, ako ga ne stavimo unosi trenutni datum pomoću datetime modula


![Kreiranje temperature](./images/iiu_domaci_2)


Sad za dobijanje prosečne temperature i broj dana nije potrebno nikakav parametar da se unosi jedino da se pristupi



![Vraćanje podataka](./images/iiu_domaci_3)



Vidimo sad kako je to sve sačuvano na ElephantSql

Sačuvana soba 

![Čuvanje sobe](./images/iiu_domaci_4)


Čuvanje temperature

![Čuvanje temperature](./images/iiu_domaci_5)
## Authors

- [@Nađa Perić](https://www.github.com/nadjaperic)
- [@Aleksandra Pantelić](https://www.github.com/aleksandra1206)
- [@Milica Živanović](https://www.github.com/zivkam)



