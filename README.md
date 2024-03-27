# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:

```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <title>One Piece</title>
    <style>
        a{
            font-size: 30px;
            font-family: 'Segoe UI';
            text-decoration: none;
            color: black;
        }
        a:hover{
            color: darkblue;
        }
        ::placeholder
        {
          font-family: 'Times New Roman';
          font-size: 30px;
          font-style: initial;
          text-align: center;
        }
        h1{
          font-family: Tahoma;
          color: crimson;
          border-color: black;
        }
        
    </style>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body style="background-color: aquamarine;" >
    
  <div style="display: flex;">
    <div style="width: 28%;">
        <img src="oplg2.png" alt="" style="height: 150px;">
    </div>
    <div style="width: 40%;">
        <a href="traf.html" style="padding: 8px;">|| About ||</a>
        <a href="Zoro.html" style="padding: 8px;">Plot ||</a>
        <a href="rengo.html" style="padding: 8px;">Arcs ||</a>
        <a href="traf.html" style="padding: 8px;">Characters ||</a>
    </div>
    <div style="width: 32%;">
        <input type="text" name="search" placeholder="Search" style="padding-left: 3px ;border-radius: 10px;border-color: black;background-image: url(see.png);background-size: contain;background-repeat: no-repeat;background-position: 2%;text-align: center;font-size: 30px;border: 5px solid black;width: 380px;">
        <input type="submit" class="sub" name="subm" value="Go" style="height: 30px;font-size: 20px;font-family: 'Lucida Grande';">
    </div>
    
    
    
    </div><br>
        <center>
        <h1 style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; font-style: italic;font-size: 50px;color: aquamarine;background-color: black ;">ONE PIECE</h1>
        <h2 style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; font-style: italic;font-size: 50px;color: aquamarine;background-color: black ;">Greatest Story Ever Told</h2><br>
      </center>
      <p style="font-size: 20px;font-family:Tahoma;color: black;padding: ;">Although there are many great stories, even greater than One Piece, One Piece deserves to be a worldwide popular culture. We want One Piece to be enjoyed by millions of internet fans, we want One Piece to be the part of the internet popular culture like "Games of Thrones", "Harry Potter", "Star Wars", and many other big projects. This site is to show what One Piece is about and to show that One Piece is not what 4Kids made it to be. Since most English speaking people don't like the dub due to weird art and a messed up story, we want to show the truth about what they are missing and what One Piece really is. Our goal is to put everything about One Piece here, to expand its popularity, we want One Piece to be notable. We want One Piece to be wildly discussed, for the fanfiction to grow, for the fanbase to grow, to enrich the series with national attention. We encourage you to come in and see what One Piece is all about and enjoy the story.</p><br><br>
        <div id="carouselExampleIndicators" class="carousel slide">
            <div class="carousel-indicators">
              <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
              <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
              <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
            </div>
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img src="op3.jpeg" class="d-block w-100" alt="..." height="800px">
              </div>
              <div class="carousel-item">
                <img src="op1.jpeg" class="d-block w-100" alt="..." height="800px">
              </div>
              <div class="carousel-item">
                <img src="op2.jpeg" class="d-block w-100" alt="..." height="800px">
              </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Next</span>
            </button>
            <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
          </div><br>
          <div style="display: flex;">
          <div style="width: 60%;padding-left: 50px;">
            <p style="font-size: 20px;font-family:Tahoma;color: black;">Monkey D. Luffy's straw hat is the main symbol of the entire series and is the origin of his nickname "Straw Hat Luffy." His straw hat was given to him by his idol, "Red-Haired" Shanks when Luffy was a child, and he promised to give the hat back to Shanks once he becomes a great pirate (or in other words, the Pirate King).Much later, during the Straw Hat Pirates' departure for Fish-Man Island, it was revealed by Silvers Rayleigh that this straw hat originally belonged to Gol D. Roger.Although Luffy's straw hat is his treasure, he is seen without it on occasion. This is usually because he does not want anything bad to happen to it, in which case he usually gives it to another member of his crew for safekeeping. It has been damaged twice in the manga canon. The first time it was damaged by Buggy when he was fighting Luffy. Buggy spat on the hat as well when he learned that it previously belonged to Shanks. After the fight, Nami repaired it for him.</p>
            </div>
            <div style="width: 40%;">
            <img src="Luffy & Shanks.jpeg" alt="" height="300px">
          </div>
          </div><br>
          
          
          </div>
          <div style="display: flex;">
            <div class="card" style="width: 18rem;margin: 10px;">
              <img src="straw.jpg" class="card-img-top" alt="..." height="150px">
              <div class="card-body">
                <h5 class="card-title">Straw Hat Pirates</h5>
                <p class="card-text">The Straw Hat Pirates, also known as the Mugiwara Pirates, Straw Hat Crew, or simply the Straw Hats, are an infamous and powerful pirate crew that originated from the East Blue.They are led by Monkey D. Luffy.</p>
                <a href="https://onepiece.fandom.com/wiki/Straw_Hat_Pirates?so=search" class="btn btn-primary">More</a>
              </div>
            </div>
            <div class="card" style="width: 18rem;margin: 10px;">
              <img src="heart.jpeg" class="card-img-top" alt="..." height="150px">
              <div class="card-body">
                <h5 class="card-title">Heart Pirates</h5>
                <p class="card-text">The Heart Pirates were an infamous and notable rookie pirate crew from the North Blue and introduced on Sabaody Archipelago around the time the Straw Hat Pirates arrived there two years ago. Their captain, Trafalgar D. Water Law, is a member of the Worst Generation</p>
                <a href="https://onepiece.fandom.com/wiki/Heart_Pirates" class="btn btn-primary">More</a>
              </div>
            </div>
            <div class="card" style="width: 18rem;margin: 10px;">
              <img src="red.jpeg" class="card-img-top" alt="..." height="150px">
              <div class="card-body">
                <h5 class="card-title">Red Haired Pirates</h5>
                <p class="card-text">The Red Hair Pirates are a powerful and infamous pirate crew in the One Piece universe, led by Red-Haired Shanks, one of the Four Emperors and a former apprentice of the Roger Pirates.</p>
                <a href="https://onepiece.fandom.com/wiki/Red_Hair_Pirates" class="btn btn-primary">More</a>
              </div>
            </div>
            <div class="card" style="width: 18rem;margin: 10px;">
              <img src="kid.jpeg" class="card-img-top" alt="..." height="150px">
              <div class="card-body">
                <h5 class="card-title">Kid Pirates</h5>
                <p class="card-text">The Kid Pirates were an infamous and notable rookie pirate crew introduced during the Sabaody Archipelago Arc during the time the Straw Hat Pirates arrived there two years ago. As such, they are part of the Worst Generation.</p>
                <a href="https://onepiece.fandom.com/wiki/Kid_Pirates?so=search" class="btn btn-primary">More</a>
              </div>
            </div>
            <div class="card" style="width: 18rem;margin: 10px;">
              <img src="Kaido Jolly Roger.jpeg" class="card-img-top" alt="..." height="150px">
              <div class="card-body">
                <h5 class="card-title">Beast Pirates</h5>
                <p class="card-text">The Beasts Pirates[2] are an extremely infamous and powerful pirate crew led by their governor-general, Kaidou, formerly one of the Four Emperors. They were based in Wano Country, specifically headquartered on Onigashima.</p>
                <a href="https://onepiece.fandom.com/wiki/Beasts_Pirates" class="btn btn-primary">More</a>
              </div>
            </div>
          </div>
            
          
    
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:

![alt text](<snmp/Screenshot (135).png>)

![alt text](<snmp/Screenshot (136).png>)

![alt text](<snmp/Screenshot (137).png>)

![alt text](<snmp/Screenshot (138).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
