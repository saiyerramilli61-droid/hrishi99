<!DOCTYPE html>
<html>
<head>
<title>Search Suggestion</title>
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>

<body>

<input type="text" id="search" placeholder="Search here">
<div id="result"></div>

<script>
$(document).ready(function(){
  $("#search").keyup(function(){
    var txt = $(this).val();
    $.ajax({
      url:"search.php",
      method:"POST",
      data:{search:txt},
      success:function(data){
        $("#result").html(data);
      }
    });
  });
});
</script>

</body>
</html>
