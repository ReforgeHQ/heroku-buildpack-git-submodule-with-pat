This Heroku buildpack adds support for Git submodules **where access to the submodule is via a Personal Access Token (PAT)**. It is forked from [SectorLabs/heroku-buildpack-git-submodule](SectorLabs/heroku-buildpack-git-submodule).

## Usage

1. Add the buildpack to your Heroku app as the first buildpack:

        heroku buildpacks:add --index 1 https://github.com/ReforgeHQ/heroku-buildpack-git-submodule-with-pat.git

2. Set the `GIT_REPO_URL` to the SSH URL of your Git repo:

        heroku config:set GIT_REPO_URL=git@github.com:ReforgeHQ/reforge-copilot

3. Set `GIT_SSH_KEY` to the private SSH key that can access the main repository:

        heroku config:set GIT_SSH_KEY="$(cat ~/.ssh/your_repository_private_key)"

4. Set `GIT_SUBMODULE_PAT` to the personal access token used to access the shared submodule.

        heroku config:set GIT_SUBMODULE_PAT="abc123"git ad

## Limitations
1. SSH Authentication only.

## License
```
MIT License

Copyright (c) 2017 Sector Labs

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
