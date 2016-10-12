# Menu Helper for Nova Framework

Creates a menu from an object of keys.
A typical table would be setup like this:

The parentID == 0 means it's a top level item with no children
Where the parentID has a number it matches the pageID so it belongs to the parent row.

For instance in the table below Hosting, Web Design and SEO are children of Services.

| pageID | pageTitle | pageSlug | parentID |
| ------ | ----------| -------- | -------- |
| 1 | About | about | 0 |
| 2 | Services | services | 0 |
| 3 | Hosting | hosting | 2 |
| 4 | Web Design | web-design | 2 |
| 5 | SEO | seo | 2 |
| 6 | Contact | contact | 0 |

##Install
Add Menu.php to app/Helpers 

##Usage

Create an Alias
````
use App\Helpers\Menu;
````

Page in the params:
- $rows = the object holding the keys
- $id - the name of the id column
- $title - the name of the title column
- $slug - the name of the slug column
- $parent - the name of the parent column

Usage Example
````
$pages = $this->model->getPages();
$data['menu'] = Menu::getList($pages, $id = 'pageID', $title = 'pageTitle', $slug = 'pageSlug', $parent = 'parentID');
````
