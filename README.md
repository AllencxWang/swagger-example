### The idea behind
the idea is to divide the original swagger file into smaller pieces, and reassemble those pieces through a build process. Take this POC for example, if you want to add api routes for a group (like a Manager in R1), you only have to: 

1. add a new file to src/paths/ directory
2. write detailed descriptions (urls, schemas, whatever) in that file
3. include that file in src/swagger.yaml using @@include syntax

### How to use

to get a reassembled swagger file, you only have to run the script below, and the output file will be dist/swagger.yaml
```sh
$ yarn
$ yarn run build
```

in this POC project, we put the original swagger file in original/swagger.yaml, and the split pieces in src/ folder, you can then compare the reassembled file with the original one to prove the POC works
```sh
$ yarn run diff
```

### How to edit
if you want to edit the reassembled swagger file, just run the script below and it will open Swagger-Editor for you
```sh
$ yarn run edit
```
one thing to remember is that all the changes you make will not reflect on the file, you have to manually copy those changes and paste it to the corresponding files

### How to view
if you want to use Swagger-UI to examine the reassembled swagger file, use the script below
```sh
$ yarn run ui
```

### Memo
- We only have a single definitions.yaml, currently. But it can also be split just like what we do to the paths.