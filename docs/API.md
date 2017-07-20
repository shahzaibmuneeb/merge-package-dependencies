## Objects

<dl>
<dt><a href="#exceptions">exceptions</a> : <code>object</code></dt>
<dd><p>Exceptions usable within package, exposed for convience during error handling.</p>
<ul>
<li>LogicalException</li>
<li>DomainException</li>
<li>InvalidArgumentExcepetion</li>
<li>RangeException</li>
<li>RuntimeException</li>
<li>HttpException</li>
<li>InvalidNpmPackageException</li>
<li>InvalidBowerPackageException</li>
</ul>
</dd>
</dl>

## Functions

<dl>
<dt><a href="#npmMerge">npmMerge(template, paths, [saveTo], [log])</a> ⇒ <code>object</code></dt>
<dd><p>Merge specified npm packages together.</p>
</dd>
<dt><a href="#bowerMerge">bowerMerge(template, paths, [saveTo], [log])</a> ⇒ <code>object</code></dt>
<dd><p>Merge specified bower packages together.</p>
</dd>
<dt><a href="#bowerValidate">bowerValidate(pkgJson)</a></dt>
<dd><p>Performs very basic bower.json spec validation.</p>
</dd>
</dl>

<a name="exceptions"></a>

## exceptions : <code>object</code>
Exceptions usable within package, exposed for convience during error handling.

**Kind**: global namespace  
<a name="npmMerge"></a>

## npmMerge(template, paths, [saveTo], [log]) ⇒ <code>object</code>
Merge specified npm packages together.

**Kind**: global function  
**Throws**:

- <code>InvalidArgumentException</code> if a provided argument cannot be used.
- <code>InvalidNpmPackageException</code> if any package is invalid.
- <code>LogicalException</code> if a inputs provided cannot be logically processed according to defined behaviour.


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| template | <code>object</code> |  | Template that packages will be merged into. Is validated with [package-json-validator](https://www.npmjs.com/package/package-json-validator). |
| template.name | <code>string</code> |  | Template MUST have a name. |
| template.version | <code>string</code> |  | Template MUST have a version. |
| paths | <code>Array.&lt;string&gt;</code> |  | Paths to package.json files. EG: "path/to/" (package.json is prepended) or "path/to/package.json" or "path/to/different.json". |
| [saveTo] | <code>string</code> | <code>null</code> | If string, saves the generated package.json to the specified path. Like 'paths', has 'package.json' prepended if required. |
| [log] | <code>boolean</code> | <code>false</code> | If true, progress and errors will be logged. Has no affect on exceptions thrown. |

<a name="bowerMerge"></a>

## bowerMerge(template, paths, [saveTo], [log]) ⇒ <code>object</code>
Merge specified bower packages together.

**Kind**: global function  
**Throws**:

- <code>InvalidArgumentException</code> if a provided argument cannot be used.
- <code>InvalidBowerPackageException</code> if any package is invalid.
- <code>LogicalException</code> if a inputs provided cannot be logically processed according to defined behaviour.


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| template | <code>object</code> |  | Template that packages will be merged into. Is validated with [bower-json](https://www.npmjs.com/package/bower-json). |
| template.name | <code>string</code> |  | Template MUST have a name. |
| paths | <code>Array.&lt;string&gt;</code> |  | Paths to bower.json files. EG: "path/to/" (bower.json is prepended) or "path/to/bower.json" or "path/to/different.json". |
| [saveTo] | <code>string</code> | <code>null</code> | If string, saves the generated bower.json to the specified path. Like 'paths', has 'bower.json' prepended if required. |
| [log] | <code>boolean</code> | <code>false</code> | If true, progress and errors will be logged. Has no affect on exceptions thrown. |

<a name="bowerValidate"></a>

## bowerValidate(pkgJson)
Performs very basic bower.json spec validation.

**Kind**: global function  
**Throws**:

- <code>InvalidBowerPackageException</code> if provided package is invalid.


| Param | Type | Description |
| --- | --- | --- |
| pkgJson | <code>string</code> | JSON representation of a bower.json package. |
