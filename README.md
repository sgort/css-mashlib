# css-mashlib
CSS with mashlib recipe and NSS like templates/pod.

This is a `http://localhost:3000` server for mashlib build test purpose. The repo is integrated with the [mashlib](https://github.com/SolidOS) stack build.

### config
- package.json contains 2 dependencies :
  - CSS version.
 
    **Each major version is linked to a different /config/config-mashlib.json**
  - mashlib version.
    
- config files are located in `config` folder
  - `config-mashlib.json` is derived from `/config/config-mashlib.json` [CSS mashlib recipe](https://github.com/communitySolidServer/recipe/mashlib).
    	
	  - Enable setup by replacing in line `"css:config/app/setup/disabled.json"` `disabled` with 'required'. see [gitter im comment](https://gitter.im/solid/community-server?at=621347740909252318ed6c42)
    
    - **The file must be replaced for each new CSS mashlib recipe version - at least for the context version**

  - `override-pod-templates.json` replaces default CSS `/templates/pod` folder by `/css-mashlib/templates/pod`
    
    see https://github.com/CommunitySolidServer/CommunitySolidServer/issues/1510

- `css-mashlib/templates/pod` is structured to produce default CSS pod that is fully compatible with NSS pods.
  - WebID document : card$.ttl
  - pod structure
    - inbox
    - profile
    - public
    - settings

### start CSS
- The choice has been made to run a monopod CSS.
  
- Data is stored in the `css-mashlib/data` folder
- To start CSS. There are 2 possibilities :
  - `npm run start` (keep existing data - if any)
  - `npm run start:clean` (reset CSS)

  At pod creation you are proposed to create a root pod (http://localhost:3000) or a suffix pod (http://localhost:3000/user/).
  This allow to eventually test mashlib on 2 CSS flavors : `subdomain` or `suffix`.
