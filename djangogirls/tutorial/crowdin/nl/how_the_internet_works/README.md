# Hoe het internet werkt

> Dit hoofdstuk is geïnspireerd door een presentatie "How the Internet works" door Jessica McKellar (http://web.mit.edu/jesstess/www/).

We durven te wedden dat je het internet dagelijks gebruikt,maar weet je eigenlijk wel wat er gebeurt wanneer je een adres zoals http://djangogirls.org intypt in je browser en je op `enter` drukt?

Het eerste wat je moet begrijpen is dat een website gewoon een stelletje opgeslagen bestanden op een harde schijf zijn. Net zoals je video's, muziek of afbeeldingen. Echter is er één dingetje dat uniek is voor websites: ze bevatten computer code genaamd HTML.

Als je niet bekend bent met programmeren kan het moeilijk zijn om in eerste instantie HTML te begrijpen. Je web browsers(zoals Chrome, Safari, Firefox, etc.) zijn er anders wel gek op. Web browsers zijn ontwerpen om deze code te begrijpen. Ze volgen de instructies die omschreven staan in de code en presenteren de bestanden waar jouw website uit bestaat, precies zoals jij het wilt.

Net zoals bij elk bestand, moeten we de HTML bestanden ergens op een harde schijf opslaan. Voor het Internet gebruiken we speciale, krachtige computers genaamd *servers*. Ze hebben geen scherm, muis of toetsenbord omdat hun voornaamste doel het opslaan en serveren van gegevens is. Dit is waarom ze *servers* worden genoemd -- omdat ze jou data *serveren*.

Ok, maar je wilt weten hoe het internet er uit ziet, toch?

We hebben een plaatje voor jou getekend! Het ziet er zo uit:

![Figure 1.1][1]

 [1]: images/internet_1.png

Ziet er uit als een puinhoop, toch? In feite is het een netwerk van aangesloten machines (de hierboven genoemde *servers*). Honderden duizenden machines! Vele, vele kilometers kabels over de hele wereld! Je kunt een onderzeeër kabel kaart website bekijken (http://submarinecablemap.com) om te zien hoe ingewikkeld het net is. Hier is een screenshot van de website:

![Figure 1.2][2]

 [2]: images/internet_3.png

Het is fascinerend, nietwaar? Maar uiteraard is het niet mogelijk om draden te hebben per machine naar elke andere machine die verbonden is met het Internet. Dus, om een machine te bereiken (bijvoorbeeld degene waar http://djangogirls.org wordt opgeslagen) moeten we een verzoek versturen die langs vele, vele verschillende machines gaat.

Het ziet er zo uit:

![Figure 1.3][3]

 [3]: images/internet_2.png

Imagine that when you type http://djangogirls.org, you send a letter that says: "Dear Django Girls, I want to see the djangogirls.org website. Send it to me, please!"

Your letter goes to the post office closest to you. Then it goes to another that is a bit nearer to your addressee, then to another, and another until it is delivered at its destination. The only unique thing is that if you send many letters (*data packets*) to the same place, they could go through totally different post offices (*routers*). This depends on how they are distributed at each office.

![Figure 1.4][4]

 [4]: images/internet_4.png

Yes, it is as simple as that. You send messages and you expect some response. Of course, instead of paper and pen you use bytes of data, but the idea is the same!

Instead of addresses with a street name, city, zip code and country name, we use IP addresses. Your computer first asks the DNS (Domain Name System) to translate djangogirls.org into an IP address. It works a little bit like old-fashioned phonebooks where you could look up the name of the person you want to contact and find their phone number and address.

When you send a letter, it needs to have certain features to be delivered correctly: an address, stamp etc. You also use a language that the receiver understands, right? The same applies to the *data packets* you send to see a website. We use a protocol called HTTP (Hypertext Transfer Protocol).

So, basically, when you have a website, you need to have a *server* (machine) where it lives. When the *server* receives an incoming *request* (in a letter), it sends back your website (in another letter).

Since this is a Django tutorial, you will ask what Django does. When you send a response, you don't always want to send the same thing to everybody. It is so much better if your letters are personalized, especially for the person that has just written to you, right? Django helps you with creating these personalized, interesting letters :).

Enough talk, time to create!