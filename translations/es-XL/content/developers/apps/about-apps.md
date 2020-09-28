---
title: Acerca de las apps
intro: 'Puedes crear integraciones con las API de {{ site.data.variables.product.prodname_dotcom }} para agregar flexibilidad y reducir la fricción en tu propio flujo de trabajo. También puedes compartir las integraciones con otros en [{{ site.data.variables.product.prodname_marketplace }}](https://github.com/marketplace).'
redirect_from:
  - /apps/building-integrations/setting-up-a-new-integration/
  - /apps/building-integrations/
  - /apps/getting-started-with-building-apps/
  - /apps/about-apps
versions:
  free-pro-team: '*'
  enterprise-server: '*'
---

Las apps en {{ site.data.variables.product.prodname_dotcom }} te permiten automatizar y mejorar tu flujo de trabajo. Puedes crear apps para mejorar tu flujo de trabajo. {% if currentVersion == "free-pro-team@latest" %} También puedes compartir o vender apps en [{{ site.data.variables.product.prodname_marketplace }}](https://github.com/marketplace). Para aprender sobre cómo listar una app en {{ site.data.variables.product.prodname_marketplace }}, consulta la sección "[Comenzar con GitHub Marketplace](/marketplace/getting-started/)".{% endif %}

{{ site.data.reusables.marketplace.github_apps_preferred }}, Pero GitHub es compatible tanto con las {{ site.data.variables.product.prodname_oauth_app }} y con {{ site.data.variables.product.prodname_github_apps }}. Para obtener más información sobre cómo escoger un tipo de app, consulta las secciónes "[Acerca de las apps](/apps/about-apps/)" y "[Diferencias entre apps](/apps/differences-between-apps/)".

{{ site.data.reusables.apps.general-apps-restrictions }}

Para obtener una guía detallada del proceso de creación de una {{ site.data.variables.product.prodname_github_app }}, consulta la sección "[Crea tu primer {{ site.data.variables.product.prodname_github_app }}](/apps/building-your-first-github-app)".

### Acerca de {{ site.data.variables.product.prodname_github_apps }}

Las {{ site.data.variables.product.prodname_github_apps }} son actores de primera clase dentro de GitHub. Una {{ site.data.variables.product.prodname_github_app }} actúa por si misma, tomando las acciones a través de la API y utilizando directamente su propia identidad, lo que significa que no necesitas mantener un bot o cuenta de servicio como un usuario separado.

Las {{ site.data.variables.product.prodname_github_apps }} se pueden instalar directamente en las cuentas de organización y de usuario, y se les puede dar acceso a repositorios diferentes. Vienen con webhooks integrados y con permisos específicos y delimitados. Cuando configuras tu {{ site.data.variables.product.prodname_github_app }}, puedes seleccionar los repositorios a los cuales quieres acceder. Por ejemplo, puedes configurar una app llamada `MyGitHub` que escribe informes de problemas en el repositorio `octocat` y _únicamente_ en dicho repositorio. Para instalar una {{ site.data.variables.product.prodname_github_app }}, necesitas ser propietario de la organización o tener permisos administrativos en el repositorio.

{{ site.data.reusables.apps.app_manager_role }}

Las {{ site.data.variables.product.prodname_github_apps }} son aplicaciones que necesitan hospedarse en algún lugar. Para obtener instruciones paso a paso que cubran los temas de servidores y hospedaje, consulta la sección "[Crear tu primer {{ site.data.variables.product.prodname_github_app }}](/apps/building-your-first-github-app)".

Para mejorar tu flujo de trabajo, puedes crear una {{ site.data.variables.product.prodname_github_app }} que contenga varios scripts, o bien, una aplicación completa, y después conectarla a muchas otras herramientas. Por ejemplo, puedes conectar las {{ site.data.variables.product.prodname_github_apps }} a GitHub, Slack, a otras apps locales que tuvieras, programas de correo electrónico, o incluso a otras API.

Toma estas ideas en consideración cuando crees {{ site.data.variables.product.prodname_github_apps }}:

{% if currentVersion == "free-pro-team@latest" %}
* {{ site.data.reusables.apps.maximum-github-apps-allowed }} {% endif %}
* Una {{ site.data.variables.product.prodname_github_app }} debe tomar acciones independientemente del usuario (a menos de que dicha app utilice un token de [usuario a servidor](/apps/building-github-apps/identifying-and-authorizing-users-for-github-apps#user-to-server-requests)). {{ site.data.reusables.apps.expiring_user_authorization_tokens }}

* Asegúrate de que la {{ site.data.variables.product.prodname_github_app }} se integre con repositorios específicos.
* La {{ site.data.variables.product.prodname_github_app }} deberá conectarse a una cuenta personal o a una organización.
* No esperes que la {{ site.data.variables.product.prodname_github_app }} sepa y haga todo lo que puede hacer un usuario.
* No utilices a la {{ site.data.variables.product.prodname_github_app }} si solo necesitas el servicio de "Iniciar sesión en GitHub". Sin embargo, una {{ site.data.variables.product.prodname_github_app }} puede utilizar un [flujo de identificación de usuario](/apps/building-github-apps/identifying-and-authorizing-users-for-github-apps/) para registrar a los usuarios _y_ para hacer otras cosas.
* No crees una {{ site.data.variables.product.prodname_github_app }} si _únicamente_ quieres fungir como un usuario de GitHub y hacer todo lo que puede hacer un usuario. {% if currentVersion == "free-pro-team@latest" %}
* {{ site.data.reusables.apps.general-apps-restrictions }}{% endif %}

Para comenzar a desarrollar {{ site.data.variables.product.prodname_github_apps }}, comienza revisando la sección "[Crear una {{ site.data.variables.product.prodname_github_app }}](/apps/building-github-apps/creating-a-github-app/)".{% if currentVersion == "free-pro-team@latest" %} Para aprender a utilizar los manifiestos de las {{ site.data.variables.product.prodname_github_app }}, los cuales le permiten a las personas crear {{ site.data.variables.product.prodname_github_apps }} preconfiguradas, consulta la sección "[Crear {{ site.data.variables.product.prodname_github_apps }} a partir de un manifiesto](/apps/building-github-apps/creating-github-apps-from-a-manifest/)".{% endif %}

### Acerca de las {{ site.data.variables.product.prodname_oauth_app }}

OAuth2 es un protocolo que permite a las aplicaciones externas el solicitar autorización para usar detalles privados en una cuenta de {{ site.data.variables.product.prodname_dotcom }} del usuario sin acceder a su contraseña. Estas son preferentes sobre la Autenticación Básica, ya que los tokens pueden limitarse a ciertos tipos de datos y los usuarios pueden revocarlos en cualquier momento.

{{ site.data.reusables.apps.deletes_ssh_keys }}

Una {{ site.data.variables.product.prodname_oauth_app }} utiliza a {{ site.data.variables.product.prodname_dotcom }} como proveedor de identidad para autenticarse como el usuario que otorga el acceso a la app. Esto significa que, cuando un usuario otorga acceso a una {{ site.data.variables.product.prodname_oauth_app }}, también otorga permisos a _todos_ los repositorios a los cuales tienen acceso en su cuenta, y también a cualquier organización a la que pertenezcan que no haya bloqueado el acceso de terceros.

Crear una {{ site.data.variables.product.prodname_oauth_app }} es una buena opción si estás creando procesos más complejos de lo que puede manejar un script sencillo. Nota que las {{ site.data.variables.product.prodname_oauth_app }} son aplicaciones que necesitan hospedarse en algún lugar.

Considera estas ideas cuando crees {{ site.data.variables.product.prodname_oauth_app }}:

{% if currentVersion == "free-pro-team@latest" %}
* {{ site.data.reusables.apps.maximum-oauth-apps-allowed }} {% endif %}
* Una {{ site.data.variables.product.prodname_oauth_app }} siempre debe actuar como el usuario autenticado de {{ site.data.variables.product.prodname_dotcom }} a través de todo {{ site.data.variables.product.prodname_dotcom }} (por ejemplo, cuando proporciona notificaciones de usuario).
* Una {{ site.data.variables.product.prodname_oauth_app }} puede utilizarse como un proveedor de identidad si el usuario autenticado habilita la opción de "Ingresar con {{ site.data.variables.product.prodname_dotcom }}".
* No crees una {{ site.data.variables.product.prodname_oauth_app }} si quieres que tu aplicación actúe en un solo repositorio. Con el alcance de `repo` de OAuth, Las {{ site.data.variables.product.prodname_oauth_app }} podrán actuar en _todos_ los repositorios del usuario autenticado.
* No crees una {{ site.data.variables.product.prodname_oauth_app }} para que actúe como una aplicación para tu equipo o compañía. Las {{ site.data.variables.product.prodname_oauth_app }} se autentican como un solo usuario, así que, si una persona crea una {{ site.data.variables.product.prodname_oauth_app }} para el uso de una compañía, y luego salen de dicha compañía, nadie más tendrá acceso a ella.{% if currentVersion == "free-pro-team@latest" %}
* {{ site.data.reusables.apps.oauth-apps-restrictions }}{% endif %}

Para obtener más información sobre las {{ site.data.variables.product.prodname_oauth_app }}, consulta las secciones "[Crear una {{ site.data.variables.product.prodname_oauth_app }}](/apps/building-oauth-apps/creating-an-oauth-app/)" y "[Registrar tu app](/v3/guides/basics-of-authentication/#registering-your-app)".

### Tokens de acceso personal

Un [token de acceso personal](/articles/creating-a-personal-access-token-for-the-command-line/) es una secuencia de caracteres que funciona de forma similar a un [Token de OAuth](/apps/building-oauth-apps/authorizing-oauth-apps/) en el aspecto de que puedes especificar sus permisos a través de [alcances](/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/). Un token de acceso personal también es similar a una contraseña, pero puedes tener varios de ellos y puedes revocar el acceso de cada uno en cualquier momento.

Com ejemplo, puedes habilitar un token de acceso personal para tener acceso de escritura en tus repositorios. Si después ejecutas un comando cURL o escribes un script que [genera un informe de problemas](/v3/issues/#create-an-issue) en tu repositorio, pasarías el token de acceso personal para autenticarte. Puedes almacenar el token de acceso personal como una variable de ambiente para evitar el tener que teclearlo cada vez que lo utilices.

Considera estas ideas cuando utilices tokens de acceso personal:

* Recuerda utilizar este token para que te represente únicamente a ti.
* Puedes realizar solicitudes cURL de una sola ocasión.
* Puedes ejecutar scripts personales.
* No configures un script para que lo utilice todo tu equipo o compañía.
* No configures una cuenta de usuario compartida para que actúe como un usuario bot.

### Determinar qué integración debes crear

Antes de que comiences a crear integraciones, necesitas determinar la mejor forma de acceder, autenticar, e interactuar con las API de {{ site.data.variables.product.prodname_dotcom }}. La siguiente imagen te da algunas pregutnas para hacerte a ti mismo cuando decidas si vas a utilizar tokens de acceso personal, {{ site.data.variables.product.prodname_github_apps }}, o {{ site.data.variables.product.prodname_oauth_app }} para tu integración.

![Introducción al flujo de preguntas de apps](/assets/images/intro-to-apps-flow.png)

Considera estas preguntas acerca de cómo necesita comportarse tu integración y a qué necesita acceder:

* ¿Mi integración actuará únicamente como yo, o actuará más como una aplicación?
* ¿Quiero que actúe independientemente de mí como su propia entidad?
* ¿Accederá a todo lo que yo puedo acceder, o quiero limitar su acceso?
* ¿Es simple o compleja? Por ejemplo, los tokens de acceso personal sirven bien para scripts simples y cURLs, mientras que una {{ site.data.variables.product.prodname_oauth_app }} puede manejar scripts más complejos.

### Solicitar soporte

{{ site.data.reusables.support.help_resources }}