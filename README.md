OpenOrder WebService, Copyright(c) 2009, DBC

Introduction
------------

This repo contains the OpenOrder webservice and client. It is part of the Open Library System Suite.

The OpenOrder service serves several functions related to ordering of materials managed by libraries. 
The service can provide definitive information on whether a specific resource can be ordered, it can
receive orders and pass them on for further processing in the OLS Base Over Bestillinger (BOB) system, 
and it can update the status of registered orders.


License
-------
DBC-Software Copyright ?. 2009, Danish Library Center, dbc as.

This library is Open source middleware/backend software developed and distributed 
under the following licenstype:

GNU, General Public License Version 3. If any software components linked 
together in this library have legal conflicts with distribution under GNU 3 it
will apply to the original license type.

Software distributed under the License is distributed on an "AS IS" basis,
WITHOUT WARRANTY OF ANY KIND, either express or implied. See the License
for the specific language governing rights and limitations under the
License.

Around this software library an Open Source Community is established. Please
leave back code based upon our software back to this community in accordance to
the concept behind GNU. 

You should have received a copy of the GNU Lesser General Public
License along with this library; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA


Documentation
-------------
http://gnit.dk/doc/opensearch ?

USe Doxygen to get code documentation


Installation
------------
OpenOrder-webservice requires [class_lib-webservice](https://github.com/DBCDK/class_lib-webservice) be installed.

In the php.ini file:
- make sure that always_populate_raw_post_data = On

Copy openorder.ini_INSTALL to openorder.ini and edit it to reflect your setup

Copy openorder.wsdl_INSTALL to openorder.wsdl and modify 
the location of the service (at the end of the file)

Consider copying robots.txt_INSTALL to robots.txt


In the php_exec-catalog the esgaroth_wrapper must be placed. It could look something like:

#!/bin/sh
/usr/www-local/esgaroth-orderpolicy/bin/esgaroth-shell --search "builtin: plugin: file:/usr/www-local/esgaroth-orderpolicy/esgaroth-lib file:/usr/www-local/esgaroth-orderpolicy/jslib-lib file:/usr/www-local/esgaroth-orderpolicy/esgaroth-config" /usr/www-local/esgaroth-orderpolicy/esgaroth-script/orderpolicy.js $1 $2 1> /dev/null 2> /dev/null

