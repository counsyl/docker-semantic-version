# docker-semantic-version

This Docker image helps automate semantic versioning by using PBR under the hood.

[PBR](http://docs.openstack.org/developer/pbr/) will auto-increment your build from the last version based on your commit messages between the last release. If there's nothing special in them then the next version will be a Patch version. If you include `Sem-Ver: feature` at the beginning of any line of your commit message, then when calculating your next version, PBR will bump it to the next Minor version. Check the documentation for more `Sem-Ver` pseudo headers.

## Usage

To calculate the next version, all you need to do is run this command with your project's name replacing `my-project-name`:

    docker run -v my-project-name/.git:/pbr/.git -it myyk/docker-semantic-version

See the [PBR documentation](http://docs.openstack.org/developer/pbr/) for more on how to use the auto-incrementing semantic versioning `Sem-Ver` git commit annotation.
