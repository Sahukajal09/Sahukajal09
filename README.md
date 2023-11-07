- 👋 Hi, I’m @Sahukajal09
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Sahukajal09/Sahukajal09 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
main.html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

    <title>E-LearnningAdmin</title>
  </head>
  <body>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" data-toggle="modal" data-target="#exampleModal123">List Of All Users </a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" data-toggle="modal" data-target="#exampleModal">Response To User<span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
       
      </li>

      <li class="nav-item">
        
    </ul>
   
  </div>
</nav>
    <div style="background-color:yellow"><center><h1>Admin Panel</h1></center></div>
    
    <form action="admin.php" method="POST" enctype="multipart/form-data">
  <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-1 col-form-label col-form-label-sm"><b>Title</b></label>
    <div class="col-sm-10">
      <input type="text" class="form-control form-control-sm" name="t" id="colFormLabelSm" placeholder="Enter title/Topic name">
    </div>
  </div>
 <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-1 col-form-label col-form-label-sm"><b>Lecture ID</b></label>
    <div class="col-sm-10">
      <input type="text" class="form-control form-control-sm" name="li" id="colFormLabelSm" placeholder="Make content serial no./ID">
    </div>
  </div>
   <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-1 col-form-label col-form-label-sm"><b>Add description</b></label>
    <div class="col-sm-10">
      <input type="text" class="form-control form-control-sm-100" name="ad" id="colFormLabelSm" placeholder="Write about your content/summary of your content">
    </div>
  </div>
   <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-1 col-form-label col-form-label-sm"><b>Refrence</b></label>
    <div class="col-sm-10">
      <input type="text" class="form-control form-control-sm" name="ref" id="colFormLabelSm" placeholder="Mention refrence">
    </div>
  </div>

<div class="form-group col-md-2">
      <label for="inputState"><b>Visibility</b></label>
      <select name="vi" id="inputState" class="form-control">
        <option selected>Choose...</option>
        <option>Public</option>
        <option>Premium</option>
      </select>
    </div>
<div class="form-group col-md-2">
      <label for="inputState"><b>Content Level</b></label>
      <select name="cl" id="inputState" class="form-control">
        <option selected>Choose Standard/Class</option>
        <option>1</option>
        <option>2</option>
        <option>3</option>
        <option>4</option>
        <option>5</option>
        <option>6</option>
        <option>7</option>
        <option>8</option>
        <option>9</option>
        <option>10</option>
        <option>11</option>
        <option>12</option>
        <option>UG</option>
        <option>PG</option>
        
      </select>
    </div>
  <div class="form-group">
    <label for="exampleFormControlFile1"><b>choose content</b></label>
    <input type="file" class="form-control-file" name="image" id="exampleFormControlFile1">
  </div>
  <input type="submit" name="x" id="colFormLabelSm">
</form>

<?php
if(isset($_REQUEST["x"]))
{
    $errors= array();
      $file_name = $_FILES['image']['name'];
      $file_size =$_FILES['image']['size'];
      $file_tmp =$_FILES['image']['tmp_name'];
      $file_type=$_FILES['image']['type'];
      $file_ext=strtolower(end(explode('.',$_FILES['image']['name'])));
      $extensions= array("jpeg","jpg","png","doc","txt","mp3","mp4","pdf");
     move_uploaded_file($file_tmp,"upload/".$file_name);
    $p1=$_REQUEST["t"];
    $p2=$_REQUEST["li"];
    $p3=$_REQUEST["ad"];
    $p4=$_REQUEST["ref"];
    $p5=$_REQUEST["vi"];
    $p6=$_REQUEST["cl"];
    $p7=$_REQUEST["image"];
    $conn=mysqli_connect("localhost","id20627678_kunal","Kunal@1234");
    mysqli_select_db($conn,"id20627678_elearning");
    mysqli_query($conn,"insert into admin values('$p1','$p2','$p3','$p4','$p5','$p6','$file_name')");
    ?>
    <script>alert("Uploaded");</script>
    <?php
}
?>


    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.12.9/dist/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
  </body>
</html>
