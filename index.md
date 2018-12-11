## Neill's micro:bit resources

# micro:bit HOWTOs

{% for thing in site.howtos %}

## [{{ thing.title }}]({{ thing.link }})

<p class="post-excerpt">{{ thing.description | truncate: 160 }}</p>
<p>language: {{ thing.proglang }}</p>

{% endfor %}   


# Activities!

{% for thing in site.activities %}

## [{{ thing.title }}]({{ thing.link }})

<p class="post-excerpt">{{ thing.description | truncate: 160 }}</p>
<p>language: {{ thing.proglang }}</p>

{% endfor %}    

# Demos

Things to inspire ideas at dojos, jams, code clubs.  Some of these also have activities designed for them.
{% for thing in site.demos %}

## [{{ thing.title }}]({{ thing.link }})

<p class="post-excerpt">{{ thing.description | truncate: 160 }}</p>
<p>language: {{ thing.proglang }}</p>


{% endfor %}   

# Discussions

{% for thing in site.discussions %}

## [{{ thing.title }}]({{ thing.url }})

<p class="post-excerpt">{{ thing.description | truncate: 160 }}</p>

{% endfor %}   

# Workshops - rough notes

{% for thing in site.workshops %}

## [{{ thing.title }}]({{ thing.url }})

<p class="post-excerpt">{{ thing.description | truncate: 160 }}</p>

{% endfor %}   