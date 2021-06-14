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
    <div class="form-group mt-2">
        <label>Name</label>
        <input type="text" class="form-control" name="name" aria-describedby="Name" placeholder="Enter your name">
    </div>
    <div class="form-group mt-2">
        <label>Surname</label>
        <input type="text" class="form-control" name="surname" aria-describedby="Surname" placeholder="Enter your surname">
    </div>
    <div class="form-group mt-2">
        <label for="exampleInputEmail1">Email address</label>
        <input type="email" class="form-control" id="exampleInputEmail1" name="email" aria-describedby="emailHelp" placeholder="Enter your email address">
    </div>
    <div class="form-group mt-2">
        <label for="exampleFormControlTextarea1">Message</label>
        <textarea class="form-control" id="exampleFormControlTextarea1" name="message" rows="3" placeholder="Enter your message here"></textarea>
    </div>
    <div class="form-check">
        <input class="form-check-input mt-2" type="checkbox" name="newletter" value="yes">
        <label class="form-check-label mt-2">
            Click here to receive our amazing newsletter.
        </label>
    </div>
    <button type="submit" class="btn btn-primary mt-3">Submit</button>
    </form>
</div>

<script>
    //get default border colours (to use on input when validation passes)
    var borderStylePass = document.querySelector('#name').style.border;
    var borderStylePass = document.querySelector('#surname').style.border;
    //set fail border colours (to use on input when validation fails)
    var borderStyleFail = '1px solid red';
    //get the form submit button
    var submit_button = document.querySelector('.form_submit');
    //attach form event listener
    submit_button.addEventListener("click", function(event){
        //get the form "name" and "surname" elements
        var name = document.querySelector('#name');
        var name = document.querySelector('#surname');
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
        if(!surname.value){
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