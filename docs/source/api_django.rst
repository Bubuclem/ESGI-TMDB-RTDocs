API Django
==========

Media
------------

.. code-block:: console

    id	                integer	        optional
    overview	        string	        optional
    poster_path	        string or null	optional
    popularity	        number	        optional
    backdrop_path	    string or null	optional
    vote_average	    number	        optional
    release_date	    string	        optional
    original_language	string	        optional
    genre_ids	        array[integer]	optional
    vote_count	        integer	        optional
    title	            string	        optional
    original_title	    string	        optional
    origin_country	    array[string]	optional
    video	            boolean	        optional
    adult	            boolean	        optional
            
    budget	            integer	        optional
    revenue	            integer	        optional
    runtime	            integer or null	optional
    status	            string	        optional
    tagline	            string or null	optional

Genres
------------

.. code-block:: console

    id	    integer	optional
    name	string	optional

People
------------

.. code-block:: console

    id	            integer	optional
    profile_path	string	optional
    adult	        boolean	optional
    name	        string	optional
    popularity	    number	optional
    Movies		
        id	                integer	        optional
        overview	        string	        optional
        poster_path	        string or null	optional
        popularity	        number	        optional
        backdrop_path	    string or null	optional
        vote_average	    number	        optional
        release_date	    string	        optional
        original_language	string	        optional
        genre_ids	        array[integer]	optional
        vote_count	        integer	        optional
        title	            string	        optional
        original_title	    string	        optional
            
    video	    boolean	optional
    adult	    boolean	optional
    media_type	string	required

Video
------------

.. code-block:: console

    id	            string	optional
    iso_639_1	    string	optional
    iso_3166_1	    string	optional
    name	        string	optional
    key	            string	optional
    site	        string	optional
    size	        integer	optional
    type	        string	optional
    official	    boolean	optional
    published_at	string	optional