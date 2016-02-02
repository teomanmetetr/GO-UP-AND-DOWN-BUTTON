# GO-UP-AND-DOWN-BUTTON
Scroll Top And Bottom CSS And JS

/* GO UP & DOWN BUTTON CSS --------------------------------*/

.UpDownButtons a {
  cursor: pointer;
  position: fixed;
  z-index: 9999;
  top: 40%;
}
.UpDownButtons a .ContainDiv {
  position: relative;
  width: 52px;
  height: 34px;
  border-bottom: 3px solid #333;
  left: 15px;
  overflow: hidden;
  opacity: 0.4;
}
.UpDownButtons a .ContainDiv .TriangleDiv {
  background: #41c4ab;
  position: relative;
  width: 48px;
  height: 48px;
  border: 3px solid #333;
  transform: rotate(45deg);
  top: 15px;
  left: 2px;
  border-radius: 15px;
}
.UpDownButtons a:hover .ContainDiv {
  opacity: 1 !important;
}
.UpDownButtons a:hover .ContainDiv > .TriangleDiv {
  border-radius: 0 !important;
}
.UpDownButtons .GoDownButton > div {
  border-bottom: none !important;
  border-top: 3px solid #333;
}
.GoDownButton {
  margin-top: 39px !important;
}
.GoDownButton .TriangleDiv {
  top: -32px !important;
}



/* GO UP & DOWN BUTTON SCSS --------------------------------*/

.UpDownButtons {
  a {
    cursor: pointer;
    position: fixed;
    z-index: 9999;
    top: 40%;
    .ContainDiv {
      position: relative;
      width: 52px;
      height: 34px;
      border-bottom: 3px solid #333;
      left: 15px;
      overflow: hidden;
      opacity: 0.4;
      .TriangleDiv {
        background: #41c4ab;
        position: relative;
        width: 48px;
        height: 48px;
        border: 3px solid #333;
        transform: rotate(45deg); 
        top: 15px;
        left: 2px;
        border-radius: 15px;
      }
    }
  }
  a:hover {
    .ContainDiv {
      opacity: 1 !important;
      & > .TriangleDiv {
        border-radius: 0 !important;
      }
    }
  }
  .GoDownButton {
    & > div {
      border-bottom: none !important;
      border-top: 3px solid #333;
    }
  }
}
.GoDownButton {
  margin-top: 39px !important;
  .TriangleDiv {
    top: -32px !important;
  }
}


/* GO UP & DOWN BUTTON HTML --------------------------------*/

<div class="UpDownButtons">
	<a class="GoUpButton" style="display: none;">
		<div class="ContainDiv">
			<div class="TriangleDiv"></div>
		</div></a> <a class="GoDownButton" style="display: none;">
		<div class="ContainDiv">
			<div class="TriangleDiv"></div>
		</div>
	</a>
</div>



/* GO UP & DOWN BUTTON JADE --------------------------------*/

.UpDownButtons
	a.GoUpButton
		.ContainDiv
			.TriangleDiv
	a.GoDownButton
		.ContainDiv
			.TriangleDiv
			
			
			
			
/* GO UP & DOWN BUTTON JS --------------------------------*/
		
$(window).scroll(function() {
	var scrollTop = $("body").scrollTop();
	if (scrollTop > 200){
		$(".GoUpButton, .GoDownButton").fadeIn(1000);
	}
	else{
		$(".GoUpButton, .GoDownButton").fadeOut(1000);
	}
});
$(".GoUpButton").click(function () {
	event.preventDefault();
	$("html, body").animate({
		scrollTop: 0
	}, "slow");
});
$(".GoDownButton").click(function () {
	$('html,body').animate({ scrollTop: 9999 }, 'slow');
});
