# Update Nix Package to New Version

1. Open to fork: https://github.com/NixOS/nixpkgs/fork
2. Download your repo clone: ```git clone https://github.com/PUT_YOUR_DINGUS_GIT_USERNAME_HERE/nixpkgs.git```
4. Edit the default.nix file for the package updating the version and emptying out any sha256 strings. Example: ```./nixpkgs/pkgs/applications/display-managers/greetd/default.nix```
5. To get any sha256 that were emptied out ```cd nixpkgs && nix-build -a PACKAGE_NAME```
6. Fill in the sha256 with the provided strings from the ```nix-build``` in the default.nix file.
7. Run ```nix-build -a PACKAGE_NAME``` to see if the build completes with the new sha256.
8. If build completes successfully submit a Pull Request. Commit Title ```package: old_version -> new_version``` example: ```greetd: 0.9.0 -> 0.10.0```
9. Find package in ```https://search.nixos.org/packages``` and click source
10. Click Edit then set Branch in the top left to master.

### nurl for sha256
* Nurl can be used to fetch a sha256. Example: ```nurl https://git.sr.ht/~kennylevinsen/greetd 0.10.0```
