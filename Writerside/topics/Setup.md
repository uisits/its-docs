# Setup

Application development team works closely with UIS ITS Database team and other department's on campus and builds applications as per project requirements.
Web applications are built using various technologies as per project requirements. Below is the tech stack that ITS Application Development team works with:

- [Docker](https://www.docker.com/)
- [Laravel Framework](https://laravel.com)
- [VueJS](https://vuejs.org)
- [TailwindCSS](https://tailwindcss.com)
- [Vuetify JS](https://vuetifyjs.com)
- [React Native](https://reactnative.dev/)

Other commonly used software products.
- [Jetbrains PHP Storm](https://www.jetbrains.com/phpstorm/)
    - Ensure you signup using `@uis` account to receive a `free` license.
- [Jetbrains DataGrip](https://www.jetbrains.com/datagrip/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [TablePlus](https://tableplus.com/)
- Api Platforms: [Postman](https://www.postman.com/) or [Insomnia](https://insomnia.rest/)


## Setup Local Environment

> Some important information
>
> We encourage using either Linux or macOS with administrator privileges as a development machine.
>
> If you are using a Windows machine please ensure that you have [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) installed and working.
> {style="warning"}

1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
2. You are now ready to pull our ITS image to begin development. Open your terminal and run the commands below:

   >    Note
   >
   >    If you are not on campus network remember to connect to VPN before proceeding.
   >
   >    Reach out to [Tulio](mailto:tllos1@uis.edu) or [Prasad](mailto:pchin3@uis.edu) for username and password.
   {style="warning"}

    ```Shell
      docker login -u user -p password uisdocker1.uisad.uis.edu:8443
      docker pull uisdocker1.uisad.uis.edu:8443/ubuntu-php8.2-fpm-apache:latest
   ```
3. Let's edit our `hosts` file in order to configure our `localhost` to `apps.uis.edu`:
    <tabs>
    <tab title="Windows">
        <procedure>
        <step>Edit your hosts file located at <code>C:\Windows\System32\drivers\etc\hosts</code></step>
        <step>Add the line: <code>127.0.0.1    apps.uis.edu</code></step>
        </procedure>
    </tab>
    <tab title="macOS/Linux">
        <procedure>
        <step>Edit your hosts file located at <code>/etc/hosts</code></step>
        <step>Add the line: <code>127.0.0.1    apps.uis.edu</code></step>
        </procedure>
    </tab>
    </tabs>
4. Let's build our first container using UIS ITS image.
    <tabs>
    <tab title="All other Chips">

    ```Shell
    docker run -p 443:443 -v /path/to/your/local/project/folder:/var/www/laravel -e DOCKER_HOST=blog -e CONTAINER_NAME=blog -e APPLICATION_NAME=blog -dP --name="blog" --hostname=blog uisdocker1.uisad.uis.edu:8443/ubuntu-php8.2-fpm-apache:latest
    ```
    </tab>
    <tab title="macOS M chips">

    ```Shell
    docker run --platform linux/amd64 -p 443:443 -v /path/to/your/local/project/folder:/var/www/laravel -e DOCKER_HOST=blog -e CONTAINER_NAME=blog -e APPLICATION_NAME=blog -dP --name="blog" --hostname=blog uisdocker1.uisad.uis.edu:8443/ubuntu-php8.2-fpm-apache:latest
    ```
    </tab>
    </tabs>
5. You can open your code in your favourite editor or visit the url `https://apps.uis.edu/blog` in your browser.

<seealso>
    <category ref="ui">
         <a href="https://laravel-news.com/">Laravel News</a>
         <a href="https://laracasts.com/">Laracasts</a>
         <a href="https://bootcamp.laravel.com/">Laravel Bootcamp</a>
         <a href="https://www.youtube.com/@LaravelPHP/videos">Laracon</a>
    </category>
</seealso>
