<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<title></title>
<link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
<link rel="stylesheet" href="fontawesome/css/all.css">
<title>Catlogues des PFEs</title>

<script type="text/javascript">


var xhr = new XMLHttpRequest();
    var connect="vide";

    function charge() {
            xhr.open("GET", "http://chakerbm.tn/ajax/pfe/pfes.php ", true);
            xhr.send();
            xhr.onreadystatechange = function() {
                if (xhr.readyState == 4 && xhr.status == 200) {
                    afficher(xhr.responseXML);
                }
            }
        }

        function charge_reseaux() {
            xhr.open("GET", "https://appessat707.000webhostapp.com/pfespartypes.php?type=reseaux", true);
            xhr.send();
            xhr.onreadystatechange = function() {
                if (xhr.readyState == 4 && xhr.status == 200) {
                    afficher(xhr.responseXML);
                }
            }
        }

        function charge_embarques() {
            xhr.open("GET", "https://appessat707.000webhostapp.com/pfespartypes.php?type=Embarques et IoT", true);
            xhr.send();
            xhr.onreadystatechange = function() {
                if (xhr.readyState == 4 && xhr.status == 200) {                  
                    afficher(xhr.responseXML);
                }
            }
        }

        function charge_dev() {
            xhr.open("GET", "https://appessat707.000webhostapp.com/pfespartypes.php?type=Developpement", true);
            xhr.send();
            xhr.onreadystatechange = function() {
                if (xhr.readyState == 4 && xhr.status == 200) {
                    // console.log(xhr.responseXML);
                    afficher(xhr.responseXML);
                }
            }
        }

        function charge_telecom() {
            xhr.open("GET", "https://appessat707.000webhostapp.com/pfespartypes.php?type=Telecom", true);
            xhr.send();
            xhr.onreadystatechange = function() {
                if (xhr.readyState == 4 && xhr.status == 200) {
                    // console.log(xhr.responseXML);
                    afficher(xhr.responseXML);
                }
            }
        }

        function afficher(data) {
            var els = data.getElementsByTagName("pfe");
            var liste = document.getElementById("tableBody");
            liste.innerHTML = "";
            for (var i = 0; i < els.length; i++) {

                  var tr = document.createElement('tr');
                var id = document.createElement('td');
                var titre = document.createElement('td');
                var type = document.createElement('td');

                id.innerHTML = els[i].getAttribute('id');
                titre.innerHTML = els[i].getAttribute('titre');
                type.innerHTML = els[i].getAttribute('type');

                tr.appendChild(id);
                tr.appendChild(titre);
                tr.appendChild(type);

                liste.appendChild(tr);

            }


        }

   
        
        


</script>

</head>


<body onload="charge()">
    <div class="card bg-primary text-white">
        <div class="card-header"><h1> Catalogue des PFEs (ESSAT) </h1> </div>
    </div>

    <div class="row" style="margin-top: 10px;">
        <div class="col-3">
        
            <div class="list-group">
                <a href="#" onclick="charge()" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center active">
                  Tous les PFEs<span class="badge bg-warning rounded-pill text-dark">13</span>               
                </a>

                <a href="#" onclick="charge_telecom()"  class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                  PFEs Télecom
                  <span class="badge bg-info rounded-pill text-white">3</span>
                </a>

                <a href="#" onclick="charge_dev()" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                    PFEs Développement
                    <span class="badge bg-info rounded-pill text-white">4</span>
                  </a>
                  <a href="#" onclick="charge_reseaux()" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                    PFEs Réseau
                    <span class="badge bg-info rounded-pill text-white">3</span>
                  </a>
                  <a href="#" onclick="charge_embarques()" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                    PFEs Embarqués & IOT
                    <span class="badge bg-info rounded-pill text-white">3</span>
                  </a>
            </div>
        </div>
        <div class="col-9">
            <div class="card bg-success text-white">
                <div class="card-header"><h5>Listes des PFEs</h5></div>
            </div>

            <section id="tabs" class="project-tab">
                <div class="container">
                    <div class="row">
                        <div class="col-md-12">
                            <div class="tab-content" id="nav-tabContent">
                                <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">
                                    <table class="table bg-light" >
                                        <thead>
                                            <tr>
                                                <th width="60">ID</th>
                                                <th width="800">Titre</th>
                                                <th width="100">Type</th>
                                            </tr>
                                        </thead>
                                        <tbody id="tableBody" >
                
                                        </tbody>
                                    </table>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            </section>
            
            
            

        </div>
    </div>
               
      
        

</body>
</html>
