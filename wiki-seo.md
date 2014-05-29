Currently we have several types of SEO links.

##SEO links using seo\_url\_db
*(can be found on Kent or TechJobs front page eg.)*

1. Add new categories, locations. jobtypes to appropriate db&#39;s tables (if needed).
2. Add the list of categories and job types to WG.
3. Run this tool once for categories, locations, job types: `/layouts/common/mw_tool_generateseourls.aspx`
4. Run the received queries.
5. INT db has to be synchronized with PROD db.
6. Add the following rules to .htaccess:
   
   ```apacheconf
   # SEO links
   RewriteCond %{HTTP_HOST} kent\.int\.matchwork\.com
   RewriteRule ^jobs/(.+\d+)$ /jobs/showjob.aspx?seo=$1 [NC,L]
   RewriteCond %{HTTP_HOST} kent\.int\.matchwork\.com
   RewriteRule ^jobs/(.+)$ /jobs/SearchResults.aspx?seo=$1 [NC,L]
   ```
7. Links should looks like:
   ```
   http://techjobs.int.matchwork.com/jobs/electrical-engineering/global-jobs/
   http://techjobs.int.matchwork.com/jobs/all-of-europe/germany/berlin-jobs/
   http://techjobs.int.matchwork.com/jobs/usa/dallas-jobs/
   ```
.htaccess rules redirects you to seo pages (`/jobs/ShowJob.aspx` and `/jobs/SearchResults.aspx`) and after this we get links like `http://techjobs.int.matchwork.com/jobs/SearchResults.aspx?seo=usa/dallas-jobs`. Control `Common.SeoUrlParser`, which should be placed on `/jobs/SearchResults/` and `/jobs/ShowJob/` pages, converts url into appropriate query string.
8. Configure Seo Browse-tree `/sitecore/content/Customers/Great Britain/Kent/Kent/FrontPage/Seo Browse-tree`. This is needed for correct work of search facets on SEO search results. `URL value` you can find in SQL queries, which we got above (#3).


##Simple predefined links
*(can be found on DGMedia front page eg.)*

1. 
