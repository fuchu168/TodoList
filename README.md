TodoList
========

HTML
<!doctype html>
<html lang="us">
<head>
	<meta charset="utf-8">
	<title>simple todo list</title>
	<link href="css/ui-lightness/jquery-ui-1.10.3.custom.css" rel="stylesheet">
	<script src="js/jquery-1.9.1.js"></script>
	<script src="js/jquery-ui-1.10.3.custom.js"></script>
	<script>
		$( document ).ready(function() {
			remover = function() {
    			$(this).remove();
			};

			$('input[type=text]').on('keydown', function(e) {
    			if (e.which == 13) {
        			var el = $("<div><p class='list-item'>"+ $(this).val() +"</p></div>");
   
        			$('.list').prepend(el);
        			$(this).val("");
        
        			el.on('click',remover);  
        			e.preventDefault();
    			}
			});
		});
	</script>

</head>
<body>

	<div id="input_field">
    	<form>
        	Add task: <input type="text" name="firstname" placeholder="input your task here"></input>
    	</form>  
	</div>

	<div class="list">
	</div>

</body>
</html>
