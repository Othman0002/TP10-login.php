# TP10-login.php
php page de connexion 
<?php
session_start();
if (isset($_SESSION['erreurLogin']))
    $erreurLogin = $_SESSION['erreurLogin'];
else {
    $erreurLogin = "";
}
?>
<!DOCTYPE HTML>
<html>
<head>
    <meta charset="utf-8">
    <title>Se connecter</title>
    <link rel="stylesheet" type="text/css" href="../css/bootstrap.min.css">
    <link rel="stylesheet" type="text/css" href="../css/monstyle.css">

    <style>
        body {
            background-image: url('../images/pfe.jpg');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;
            min-height: 100vh;
            margin: 0;
            padding: 0;
        }

        .margetop60 {
            margin-top: 60px;
        }

        .panel {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 0 15px rgba(0,0,0,0.3);
            border-radius: 10px;
        }

        .panel-heading {
            font-weight: bold;
            font-size: 18px;
            text-align: center;
        }

        .form-control {
            border-radius: 5px;
        }

        .btn-success {
            width: 100%;
        }

        .btn-create {
            margin-top: 25px;
            display: inline-block;
            font-size: 14px;
        }
    </style>
</head>
<body>
<div class="container col-md-6 col-md-offset-3 col-lg-4 col-lg-offset-4">
    <div class="panel panel-primary margetop60">
        <div class="panel-heading">Se connecter :</div>
        <div class="panel-body">
            <form method="post" action="seConnecter.php" class="form">

                <?php if (!empty($erreurLogin)) { ?>
                    <div class="alert alert-danger">
                        <?php echo htmlspecialchars($erreurLogin); ?>
                    </div>
                <?php } ?>

                <div class="form-group">
                    <label for="login">Login :</label>
                    <input type="text" name="login" placeholder="Login"
                           class="form-control" autocomplete="off"/>
                </div>

                <div class="form-group">
                    <label for="pwd">Mot de passe :</label>
                    <input type="password" name="pwd"
                           placeholder="Mot de passe" class="form-control"/>
                </div>

                <button type="submit" class="btn btn-success">
                    <span class="glyphicon glyphicon-log-in"></span>
                    Se connecter
                </button>

                <!-- Bouton Créer un compte centré et plus en bas -->
                <div class="text-center btn-create">
                    <a href="nouvelUtilisateur.php" class="btn btn-link text-success">
                        <span class="glyphicon glyphicon-user"></span> Créer un compte
                    </a>
                </div>

            </form>
        </div>
    </div>
</div>
</body>
</html>
