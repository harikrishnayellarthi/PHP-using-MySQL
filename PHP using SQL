<form action="../index.php" method="post">
      <fieldset class="form-group">
      <label for="firstname">First Name</label>
      <input type="text" name="firstname" class="form-control" id="firstname" placeholder="First Name">
    </fieldset>


    <fieldset class="form-group">
      <label for="lastname">Last Name</label>
      <input type="text" name="lastname" class="form-control" id="lastname" placeholder="Last Name">
    </fieldset>


        <fieldset class="form-group">
          <label for="exampleInputEmail1">Email address</label>
          <input type="text" name="email" class="form-control" id="email" placeholder="Enter email">
          <small class="text-muted">We'll never share your email with anyone else.</small>
      </fieldset>

      <button type="submit" id="form-button" class="btn btn-primary">Submit</button>

    </form>

$form = $_POST;
$id = $form['id'];
$firstname = $form['firstname'];
$lastname = $form['lastname'];
$email = $form['email'];


try {
$db = new PDO("mysql:host=" . DB_HOST. ";dbname=" .DB_NAME .";port=".DB_PORT,DB_USER,DB_PASS);
$db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

$add_supporter = $db->prepare("INSERT INTO supporters (id, firstname, lastname, email) 
                             VALUES (:id, :firstname, :lastname, :email)");

$add_supporter->bindParam(":id", $id);
$add_supporter->bindParam(":firstname", $firstname);
$add_supporter->bindParam(":lastname", $lastname);
$add_supporter->bindParam(":email", $email);
$add_supporter->execute();



} catch (Exception $e) {
echo "Error in connection to database" . $e->getMessage() . "</br>";
die();
}
