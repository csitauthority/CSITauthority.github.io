+++
title = "Recent Comments"
date = 2017-12-20T22:10:10+05:45
draft = false
summary = """
Recent disqus comments all over csitauthority.github.io
"""
+++


#### These are some of the recent comments all over the site

<!-- MOVE THIS SEGMENT TO SHORTCODE LATER -->
<style type="text/css">
	ul#comments {
  list-style-type: none;
  font-family: "Helvetica Neue",arial,sans-serif;
  font-size: 15px;
  color: #a5b2b9;
}

ul#comments li { margin-bottom: 30px; position: relative; }
ul#comments li a { text-decoration: none; color: rgb(102, 204, 204); }

.avatar-container { width: 60px; box-sizing: border-box; }
.avatar { width: 50px; height: 50px; border-radius: 5px; float: left; margin: 5px; }

.post-container { padding-top: 3px; margin-left: 70px;  box-sizing: border-box; }
.post-container p { color: #3f4549; }
.author_name { font-weight: bold; font-size: 13px; }

.timeago, .posted { 
  font-weight: 500;
  font-size: 12px;
  color: #a5b2b9;
  color: rgba(0,39,59,.35);
}

.bullet {
  padding: 0 2px;
  font-size: 10px;
  color: #ccc;
  line-height: 1.4;
}
</style>

<ul id="comments">
  <script id="comments-template" type="text/x-handlebars-template">
    {{#each response}}
      <li>
        <div class="avatar-container">
          <a href="{{author.profileUrl}}" target="_blank">
            <img src="{{author.avatar.small.permalink}}" class="avatar" alt="avatar" />
          </a>
        </div>
        <div class="post-container">
          <a href="{{author.profileUrl}}" class="author_name" target="_blank">
            <span class="author_name">{{author.name}}
          </a>
          
          <span class="bullet" aria-hidden="true">•</span>

          <span class="timeago" title="{{createdAt}}Z">{{createdAt}}</span>

          <p>{{{message}}}</p>

          <span class="posted">posted on <a href="{{thread.link}}" target="_blank">{{thread.title}}</a></span>
        </div>    
      </li>
    {{/each}}
  </script>
</ul>
      
<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/handlebars.js/1.3.0/handlebars.min.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/jquery-timeago/1.4.0/jquery.timeago.min.js"></script>
<script type="text/javascript">
	var DisqusRecent = {
  init: function( config ) {
    this.api_key     = config.api_key;
    this.forum       = config.forum;
    this.template    = config.template;
    this.container   = config.container;

    this.fetchRecentComments();
  },

  fetchRecentComments: function() {
    $.ajax({
      url: "https://disqus.com/api/3.0/forums/listPosts.jsonp?forum="+this.forum+"&related=thread&api_key="+this.api_key,
      dataType: "jsonp",
      context: this,

      success: function(results) {
        var source   = $(this.template).html();
        var template = Handlebars.compile(source);
        $(this.container).html(template(results));

        $('.timeago').timeago();
      }
    });
  }
}

$(function() {
  DisqusRecent.init({
    api_key:     'gidf0krBZdjU0zdg51gDFuQEMx6wqijXGR5T26m6SY6WdvT3xO3ghhuV2sVGcpOW',
    forum:       'csitauthority',
    template:    '#comments-template',
    container:   '#comments'
  });
});

<!-- OC: https://codepen.io/jaimeiniesta/pen/DhKrd -->
</script>