# typedoc-plugin-versions
#### It keeps track of your document builds and provides select options for all minor versions.  
<br />
<img src="./media/Screenshot.jpg" width="500px" height="auto" border="1px solid light-grey" />
<br />

## Usage
```
npm i -D typedoc-plugin-versions
```
and in typedoc.json
```jsonc
"plugin": ["typedoc-plugin-versions"],
"versions": { //custom options for versions
	/**
	 * The minor version that you would like to be marked as `stable`  
	 * Defaults to the latest patch version of the version being built
	 */
	"stable": "1.1",
	/**
	 * The version that you would like to be marked as `dev`  
	 * Defaults to the latest patch version of the version being built
	 */
	"dev": "1.2.19",
	/**
	 * The url to the base folder where you will host your documentation set  
	 * Default: will try to determine the GitHUB package url from package.json and convert it to gh-page url.
	 */
	"homeUrl": "https://mydocs.com/docs",
	/**
	 * A custom DOM location to render the HTML `select` dropdown corresponding to typedoc rendererHooks.  
	 * Default: Injects to left of header using vanilla js - not a typedoc render hook.
	 */
	"domLocation": "navigation.begin"
}
```

## What sorcery is this, you may ask...
`Typedoc-plugin-versions` takes the architectural approach of JuliaLang [Documenter](https://juliadocs.github.io/Documenter.jl/stable/).

Documents are built (with no change to the typedoc flow) into subdirectories corresponding to the package.json version. Symlinks are created to minor versions, which are given as options in a `select` menu.

As long as you do not delete your historic document build folders, the document history will remain intact.

## CID
Work on a CID workflow for gitHub is in progress.