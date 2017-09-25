# pyroutelib3

A continuation of [pyroutelib2](https://github.com/gaulinmp/pyroutelib2).
Routing on OSM data in Python 3.

OSM Data tiles is stored in `tilescache/`


## Usage

```python
from pyroutelib3 import Router # Import the router
router = Router("<transport mode>") # Initialise it

start = router.data.findNode(lat, lon) # Find start and end nodes
end = router.data.findNode(lat, lon)

status, route = router.doRoute(start, end) # Find the route - a list of OSM nodes

if status == 'success':
    routeLatLons = list(map(router.nodeLatLon, route)) # Get actual route coorinates

```
**Transport Modes**: car, cycle, foot, horse, tram, train

**Statuses**: success, no_route, no_such_node, gave_up


## Todo
- [x] Porting to python3
- [x] Making pyroutelib a package
- [ ] Custom transport types
- [ ] Offline routers (load only local osm file)


## License

pyroutelib3 is distributed under GNU GPL v3.

Copyright 2007, Oliver White
Modifications: Copyright 2017, Mikołaj Kuranowski -
Based on https://github.com/gaulinmp/pyroutelib2

pyroutelib3 is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 3 of the License, or
(at your option) any later version.

pyroutelib3 is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with pyroutelib3. If not, see <http://www.gnu.org/licenses/>.