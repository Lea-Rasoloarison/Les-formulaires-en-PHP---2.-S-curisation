# Les-formulaires-en-PHP---2.-S-curisation
Les formulaires en PHP - 2. Sécurisation

<?php

$error = array ();

if ($_POST){

    if(empty($_POST['nom'])){
        $error['nom'] = "Le nom est obligatoire";
    }if(empty($_POST['email'])){
        $error['email'] = "L'email est obligatoire";
    }if(empty($_POST['message'])){
        $error['message'] = "Le contenu est obligatoire";
    }if(empty($_POST['phoneNumber'])){
        $error['phoneNumber'] = "Le numéro de téléphone est obligatoire";
    }if(count ($error) == 0){
        return "succès";
        //header("location : succes.php")//;
        exit();
    }
}

?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Premier Formulaire</title>
    </head>

<body>

<p>Formulaire 2</p>

<form  action=""  method="post">

    <label for="mailSubject">Choisissez un sujet:</label>

    <select name="mailSubject" id="mailSubject">
        <option value="">--Please choose an option--</option>
        <option value="Commentaire">Commentaire</option>
        <option value="Demande">Demande</option>
        <option value="Réclamation">Réclamation</option>
        <option value="Question">Question</option>
        <option value="Avis">Avis</option>
        <option value="Autres">Autres</option>
    </select>

    <br><br>

    <div>
        <label  for="nom">Nom :</label>
        <input  type="text"  id="nom"  name="nom">
        <p> <?php if(isset($error['name'])) echo $error['name']; ?> </p>
    </div>
    <div>
        <label  for="email">Courriel :</label>
        <input  type="email"  id="email"  name="email">
        <p> <?php if(isset($error['email'])) echo $error['email']; ?> </p>

    </div>
    <div>
        <label  for="message">Message :</label>
        <textarea  id="message"  name="message"></textarea>
        <p> <?php if(isset($error['message'])) echo $error['message']; ?> </p>

    </div>
    <div>
        <label  for="phoneNumber">Numéro de téléphone :</label>
        <input  id="phoneNumber"  name="phoneNumber" type="number">
        <p> <?php if(isset($error['phoneNumber'])) echo $error['phoneNumber']; ?> </p>

    </div>
    <div  class="button">
        <button  type="submit">Envoyer votre message</button>
    </div>
</form>

</body>
</html>

