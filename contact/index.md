---
layout: layouts/post.njk
title: Get in touch!
templateClass: tmpl-post
eleventyNavigation:
  key: Get in touch!
  order: 3
---


<div class="container w-75">
    <form name="contact" method="POST" data-netlify="true">
    <div class="form-group">
        <label>Name</label>
        <input type="text" class="form-control" name="name" aria-describedby="Name" placeholder="Enter your name">
    </div>
    <div class="form-group">
        <label>Surname</label>
        <input type="text" class="form-control" name="surname" aria-describedby="Surname" placeholder="Enter your surname">
    </div>
    <div class="form-group">
        <label for="exampleInputEmail1">Email address</label>
        <input type="email" class="form-control" id="exampleInputEmail1" name="email" aria-describedby="emailHelp" placeholder="Enter email">
    </div>
    <div class="form-group">
        <label for="exampleFormControlTextarea1">Example textarea</label>
        <textarea class="form-control" id="exampleFormControlTextarea1" name="message" rows="3"></textarea>
    </div>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
    </form>
</div>

<script>
    //get default border colours (to use on input when validation passes)
    var borderStylePass = document.querySelector('#name').style.border;
    //set fail border colours (to use on input when validation fails)
    var borderStyleFail = '1px solid red';
    //get the form submit button
    var submit_button = document.querySelector('.form_submit');
    //attach form event listener
    submit_button.addEventListener("click", function(event){
        //get the form "name" elemement
        var name = document.querySelector('#name');
        //get the form "email" element
        var email = document.querySelector('#email');
        //all validation is assumed to be passed until tested
        blnValidated = true;
        //change the border as it the validation passed
        name.style.border = borderStylePass;
        //if validation fails change the bln to false and change the input border colour
        if(!name.value){
            blnValidated = false;
            name.style.border = borderStyleFail;
        }
        //if validation fails change the bln to false and change the input border colour
        email.style.border = borderStylePass;
        if(!email.value){
            blnValidated = false;
            email.style.border = borderStyleFail;
        }
        //if validation failed do not allow the form to submit the data
        if(!blnValidated){
            event.preventDefault();
        }
    }, false);
</script>