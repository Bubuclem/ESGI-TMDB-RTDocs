API TMDB
=========

TV
------------

GET /tv/popular
GET /tv/top_rated

.. list-table::
   :widths: 50 25 25
   :header-rows: 1

   * - name
     - type
     - optional/required

   * - id
     - integer
     - optional
   * - overview
     - string
     - optional
   * - poster_path
     - string or null
     - optional
   * - popularity
     - number
     - optional
   * - backdrop_path
     - string or null
     - optional
   * - vote_average
     - number
     - optional
   * - first_air_date
     - string
     - optional
   * - original_language
     - string
     - optional
   * - genre_ids
     - array[integer]
     - optional
   * - vote_count
     - integer
     - optional
   * - name
     - string
     - optional
   * - original_name
     - string
     - optional
   * - origin_country
     - array[string]
     - optional

Movies
------------

GET /movie/popular
GET /movie/top_rated

.. code-block:: console

   id	               integer	      optional
   overview	         string	      optional
   poster_path	      string or null	optional
   popularity	      number	      optional
   backdrop_path	   string or null	optional
   vote_average	   number	      optional
   release_date	   string	      optional
   original_language	string	      optional
   genre_ids	      array[integer]	optional
   vote_count	      integer	      optional
   title	            string	      optional
   original_title	   string	      optional
         
   video	boolean optional
   adult	boolean optional

Genres
------------

GET /genre/movie/list

.. code-block:: console

   id	   integer	optional
   name	string	optional

People
------------

GET/person/popular

.. code-block:: console

   poster_path	      string or null	optional
   adult	            boolean	      optional
   overview	         string	      optional
   release_date	   string	      optional
   original_title	   string	      optional
   genre_ids	      array[integer]	optional
   id	               integer	      optional
   media_type	      string	      required
   original_language	string	      optional
   title	            string	      optional
   backdrop_path	   string or null	optional
   popularity	      number	      optional
   vote_count	      integer	      optional
   video	            boolean	      optional
   vote_average	   number	      optional