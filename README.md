# css-mashlib
CSS with mashlib recipe and templates/pod

### config
- package.json contains 2 dependencies :
  - CSS version.
    Each major version is linked to a different CSS mashlib recipe version
  - mashlib version
- config files are located in `config` folder
  - `config-mashlib.json` is identical to CSS mashlib recipe.
    it must be replaced for each new CSS mashlib recipe version

  - override-pod-templates.json replaces `default CSS templates/pod` folder by `css-mashlib/templates/pod`
    see https://github.com/CommunitySolidServer/CommunitySolidServer/issues/1510

- `css-mashlib/templates/pod` is structured to produce default CSS pod that is fully compatible with NSS pods.
  - WebID card$.ttl
  - pod structure
    - inbox
    - profile
    - public
    - settings

### start CSS
  The choice has been made to run a monopod CSS.
  
  Data is stored in the `css-mashlib/data` folder
  2 possibilities
    - `npm run start` (keep existing data)
    - `npm run start:clean` (reset CSS)

  At pod creation you are proposed to create a root pod (http://loclahost:3000) or a suffix pod (http://localhost:3000/<user>/).
  This allow to eventually test mashlib on subdomain/suffix CSS.