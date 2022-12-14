# Installation
> `npm install --save @types/set-value`

# Summary
This package contains type definitions for set-value (https://github.com/jonschlinkert/set-value).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/set-value.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/set-value/index.d.ts)
````ts
// Type definitions for set-value 4.0
// Project: https://github.com/jonschlinkert/set-value
// Definitions by: Daniel Rosenwasser <https://github.com/DanielRosenwasser>
//                 Piotr Błażejewicz <https://github.com/DanielRosenwasser>
// Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped

export = set;

// Technically, everything will fall to the last overload,
// but the first one can be useful for signature help.

/**
 * @param object The object to set `value` on
 * @param path The of the property to set.
 * @param value The value to set on `object[prop]`
 * @param [options]
 */

declare function set<T extends object, K extends keyof T>(object: T, path: K, value: T[K], options?: set.Options): void;
declare function set(object: object, path: set.InputType, value: any, options?: set.Options): void;

declare namespace set {
    interface Options {
        /**
         * Do not split properties that include a `/`.
         * By default, set-value assumes that properties with a `/` are not intended to be split.
         * This option allows you to disable default behavior.
         * Note that this option cannot be used if `options.separator` is set to `/`.
         * @default true
         */
        preservePaths?: boolean | undefined;
        /**
         * Custom separator to use for splitting object paths.
         * @default `.`
         */
        separator?: string | undefined;
        /**
         * Custom `.split()` function to use.
         */
        split?: SplitFunc | undefined;
        /**
         * Allows you to update plain object values, instead of overwriting them.
         * @default  `undefined`
         */
        merge?: boolean | MergeFunc | undefined;
    }

    type InputType = string | symbol | ReadonlyArray<string | symbol>;

    type MergeFunc = <TObject, TSource>(object: TObject, source: TSource) => TObject & TSource;

    type SplitFunc = (input: string, options?: Options) => string;
}

````

### Additional Details
 * Last updated: Tue, 06 Jul 2021 16:34:40 GMT
 * Dependencies: none
 * Global values: none

# Credits
These definitions were written by [Daniel Rosenwasser](https://github.com/DanielRosenwasser), and [Piotr Błażejewicz](https://github.com/DanielRosenwasser).
