# itcod-exchange
SOA ITCOD. EXCHANGE. 
Service automated exchange of files between users for the WebDAV interface.

Nginx requires build modules: WebDAV WebDavExt and Lua.

Copyright (c) 2015 by Yura Vdovytchenko (max@itcod.com)

Copyright (c)itcod 2015

path lua file: /etc/nginx/lua/itcod-exchange.lua

paths for access files for directoryes 

~/0000/export/.htexport -transfer files-> ~/1111/import/.htimport

.htimport - import access (trivial example of a string: 1111:all)

.htexport - export access (trivial example of a string: 0000:all)


Example Nginx virtual example.conf

local example = {
 
 
server {
    #...

    location / {
	#...
        header_filter_by_lua_file /etc/nginx/lua/itcod-exchange.lua;
    }
}

