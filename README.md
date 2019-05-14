# Virtual Team Toolbox
This is the barebones HTML for the Virtual Team Toolbox project for the UGA MIS Department. This is a work in progress, and this is just a rough template.

# How to add / edit content
This website is built on the Bootstrap framework, so first please make sure you are familiar with Bootstrap 4 syntax so you are able to read the code and understand the structure.

## Home Page
Home page sections are built into `container` sections, usually with a `col` inside of them. Look for `<p>` tags to find places where content can be edited. This page is build like a landing page, and should be relatively easy to understand and edit.

## Toolbox Page
This is the page with the categories listed in boxes with icons. Here's the structure of that:
This is all inside of a container as well:
```
<div class="row">
    <div class="col category-box">
        <a href="cat-pm.html">
            <i class="fas fa-tasks"></i>
            <h3>Project Management</h3>
        </a>
    </div>
    <div class="col category-box">
        <a href="#">
            <i class="fas fa-folder-open"></i>
            <h3>Document Storage & Collaboration</h3>
        </a>
    </div>
    <div class="col category-box">
        <a href="#">
            <i class="fas fa-code-branch"></i>
            <h3>Version Control</h3>
        </a>
    </div>
    <div class="col category-box">
            <a href="#">
                <i class="fas fa-envelope"></i>
                <h3>Formal Communication</h3>
            </a>
    </div>
</div><!-- End Row -->
```                
This section currently has 2 of these rows inside of a container. Each row has 4 columns that are automatically figured out by Bootstrap by just setting a `col` class. Now we see the inner structure of `category-box` and the content inside. This is just the stylized box with a https://fontawesome.com/ icon inside. The icon files are linked already, so you should be able to easily add any free icons that you want later on.

## Inner Pages
These are pages such as `cat-pm.html` and `trello-intro.html`

These pages all follow a similar structure, and adding content is very easy. First of all, make sure you update the `<title>` tage when adding/editing a page.

Then,  move on to the navbar on the left side. Here's the basic structure:
```
<a href="#menu1" class="list-group-item" data-toggle="collapse" data-parent="#sidebar">
    <span class="hidden-sm-down">Project Management <i class="fa fa-caret-down"></i></span> 
</a>
<div class="collapse" id="menu1">
    <a href="cat-pm.html" class="list-group-item">
        <span class="hidden-sm-down">Goals</span> 
    </a>
    <a href="#menu2" class="list-group-item">
        <span class="hidden-sm-down">Tools</span> 
    </a>
    <a href="#menu3" class="list-group-item" data-toggle="collapse" data-parent="#sidebar">
        <span class="hidden-sm-down">Trello <i class="fa fa-caret-down"></i></span> 
    </a>
    <div class="collapse" id="menu3">
        <a href="trello-intro.html" class="list-group-item active-list-item" data-parent="#menu2">Introduction</a>
        <a href="trello-setup.html" class="list-group-item" data-parent="#menu2">Setup</a>
        <a href="trello-cards.html" class="list-group-item" data-parent="#menu2">Cards</a>
        <a href="trello-labels.html" class="list-group-item" data-parent="#menu2">Labels</a>
        <a href="trello-teams.html" class="list-group-item" data-parent="#menu2">Teams</a>

    </div>
    <!-- <a href="#menu4" class="list-group-item">
        <span class="hidden-sm-down">Item 3</span> 
    </a>
    <a href="#menu5" class="list-group-item">
        <span class="hidden-sm-down">Item 4</span> 
    </a> -->
</div><!-- End PM Collapse -->
```                            

All of this sits inside a class of `list-group`, and you will always be adding/removing stuff from inside of this area. A few things of note:
- The first `<a>` tag we see has an ID of menu1, and has a data-toggle="collapse" as well as a data-parent. All of this is very important, and all of this helps signify that it is a **top-level menu item**
    - Specifically, the #menu1 helps identify it as a toggle and must be unique for the script to work
- Then we see a `<div class="collapse" id="menu1">` This is where we signify an "inner" menu under that initial link. The structure here is very important, and you must refer to the ID that will toggle this
- Inside that we have all of the rest of our links for this category. Each link has a unique ID, as if it were going to be a toggle. Not necessary unless the link will be a toggle, but nice to have
- Then we see a Trello link with a similar structure as our top-level menu. This is another toggle that follows the previous format discussed.
    - Also you will notice a utility class called `active-list-item` on the link for trello-intro.html. This helps show the user which page they are currently on.
- To add new links below the PM category, simply go under the commented div ending of PM Collapse, and add a new group similar to this one.


### Actual Lesson Content
This is the final area that you will need to edit when adding new lessons. Here's the structure to look for:
```
<div class="col-md-8 lesson-body">
    <h2 class="text-center">Project Management - Goals</h2>
    <!-- Lesson video will go here -->
    <img class="img-fluid" src="https://via.placeholder.com/900x300.png?text=Video+Here" />

    <!-- Start Actual Lesson Body -->
    <h3 class="mt-3">What you will learn in this lesson</h3>

    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Immo alio genere; Istic sum, inquit. </p>

    <p>Deinde dolorem quem maximum? Quis est tam dissimile homini. Ne discipulum abducam, times. Tollitur beneficium, tollitur gratia, quae sunt vincla concordiae. Praeclare hoc quidem. </p>

    <p>Cur post Tarentum ad Archytam? Qua ex cognitione facilior facta est investigatio rerum occultissimarum. </p>

    <p>Pugnant Stoici cum Peripateticis. Sed haec omittamus; Recte, inquit, intellegis. Sedulo, inquam, faciam. Et nemo nimium beatus est; Simus igitur contenti his. Dici enim nihil potest verius. Hic nihil fuit, quod quaereremus. </p>

    <p>Sed haec nihil sane ad rem; Conferam tecum, quam cuique verso rem subicias; Comprehensum, quod cognitum non habet? Duo Reges: constructio interrete. </p>
    <a href="#" class="btn btn-light">&#8249; Previous</a>
    <a href="#" class="btn btn-light float-right">Next &#8250;</a>
</div>
```

The `<h2>` will be the lesson title. Eventually if you were to have videos, they would replace that img tag. For right now, you can remove it or just use a basic image in its place.
The h3 is a subheading really, I have omitted it in the trello lessons.
Then you just place your content below that, **make sure to use `<p>` tags to separate paragraphs**
Then we have our previous and next links. You can omit them if you like, I have used them to provide secondary navigation in the trello lessons though.

And that's it! Your lesson is live!


## Conclusion
While it may seem a bit complicated, once you get used to the structure it's quite easy to add/edit lessons. I hope this product can be helpful in the long-run.
