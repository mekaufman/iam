---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# Conceptos de IAM
{: #iamconcepts}

Hay dos conceptos principales que destacan cuando desea aprender sobre {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM): la identidad y la gestión de acceso. Adicionalmente, puede aprender sobre grupos de acceso, grupos de recursos, usuarios, roles, políticas de acceso y otros.
{: shortdesc}

## Identidad
{: #identity}

El concepto de identidad en {{site.data.keyword.Bluemix_notm}} IAM consta de identidades de usuario, identidades de servicio y de app, claves de API y recursos. Los usuarios se identifican mediante su ID de cuenta de IBM o SoftLayer. Los ID de servicio son un segundo tipo de identidad que se utiliza en una cuenta. Los ID de servicio son las características de Cloud IAM utilizadas para proporcionar una identidad separada para servicios y aplicaciones. Puede crear un ID de servicio para que lo utilice una aplicación que necesita acceso a sus servicios de {{site.data.keyword.Bluemix_notm}} para que no se tengan que utilizar credenciales de usuario individual.

Para autenticarse con una API o CLI como un usuario o un ID de servicio, se pueden utilizar las claves de API de {{site.data.keyword.cloud_notm}}. Estas claves de API están proporcionadas a través de Cloud IAM y, por lo tanto, no se pueden utilizar de forma general para autenticarse con el IBMid fuera de IBM Cloud. Un usuario también puede tener una sola clave de API de la infraestructura clásica que se puede utilizar para acceder a las API de la infraestructura clásica; sin embargo, esto no es necesario, ya que puede utilizar las claves de API de {{site.data.keyword.cloud_notm}} para acceder a las mismas API.

La parte final del concepto de identidad en IAM es son los recursos de {{site.data.keyword.Bluemix_notm}}, que se identifican por sus nombres de recurso de nube (CRN). Para obtener más información, consulte [Nombres de recursos de nube](/docs/overview?topic=overview-crn#crn).

## Gestión de acceso
{: #am}

El concepto de gestión de acceso en {{site.data.keyword.Bluemix_notm}} está formado por unos cuantos componentes interrelacionados, incluyendo usuarios, recursos, políticas, roles, acciones y el sistema de control de {{site.data.keyword.Bluemix_notm}} IAM, que permite a los usuarios realizar acciones en recursos dentro de una cuenta.

{{site.data.keyword.Bluemix_notm}} IAM sigue un patrón [con el tiempo coherente](https://en.wikipedia.org/wiki/Eventual_consistency){: external} que es común a muchos servicios nativos de nube, lo que permite a IAM permanecer altamente disponible y funcionando en varias regiones globales. Los cambios que se realizan en las políticas de acceso de IAM, las autorizaciones, los ID de servicio, las claves de API, los grupos de acceso, los grupos de recursos, los usuarios o cualquier otro control de acceso se registran y se propagan en todos los componentes de IAM y los servicios habilitados para IAM en todo el mundo. Es posible que los cambios de acceso no entren en vigor hasta que se haya completado el proceso de propagación.

### Usuarios
{: #iam-users}

Todos los usuarios de una cuenta se identifican mediante sus IBMid o sus ID de cuenta de SoftLayer. Se puede invitar a los usuarios a la cuenta y darles acceso a recursos. Las políticas de acceso empiezan por el sujeto que a menudo es un usuario de su cuenta. Se puede asignar acceso a servicios de gestión de cuentas, a recursos individuales descendiendo hasta el nivel de instancia, o a un conjunto de recursos organizados en un grupo de recursos de cuenta.


### Grupos de acceso
{: #access-groups-iam}

Se puede crear un grupo de usuarios y de ID de servicio para poder asignar el mismo acceso a todas las entidades dentro del grupo con una o más políticas. Utilizando grupos de acceso, puede agilizar el proceso de asignación de acceso de forma que pueda gestionar una cantidad menor de políticas y reducir el número de políticas en una cuenta, lo que aumenta el rendimiento. Una vez que se han configurado los grupos, puede empezar a asignar políticas seleccionando un grupo de acceso como el sujeto de la política. Para obtener más información, consulte el apartado [Configuración de grupos de acceso](/docs/iam?topic=iam-groups).

### Recursos
{: #resources-access-management}

Los recursos de cuenta son las ofertas de servicio de suministro seleccionadas del catálogo o los recursos granulares dentro de una instancia de servicio. Estos recursos se añaden a un grupo de recursos cuando se crean desde el catálogo. La gestión de acceso de IAM habilita un acceso preciso, lo que significa que se puede establecer una política en una escala más amplia, para todos los recursos de un grupo de recursos, por ejemplo, o a un tipo de recurso específico como un grupo (bucket) de {{site.data.keyword.cos_full_notm}} con una instancia específica.


### Políticas de acceso
{: #access-policies-concept}

Las políticas de acceso determinan cómo se otorga permisos a usuarios, ID de servicio o grupos de acceso en la cuenta para acceder a los recursos de la cuenta. Las políticas incluyen un sujeto, un destino y un rol. El sujeto es el usuario, el ID de servicio o el grupo de acceso al que está proporcionando acceso. El objetivo de la política es el recurso al que desea proporcionar acceso. Y, los roles son la forma de definir el nivel de acceso o las acciones permitidas en el objetivo de la política. Hay distintos tipos de políticas que permiten acceder a recursos de cuenta: una política de grupo de recursos, una política de instancia de recursos, una política de toda la cuenta para acceder a todos los servicios habilitados para Identity and Access y una política sobre un servicio de gestión de la cuenta o sobre todos ellos. En función de sus selecciones, es posible que disponga de opciones de configuración personalizadas como la definición de acceso en recursos en una región específica o la definición de acceso al nivel granular de un recurso específico de servicio dentro de una instancia.

### Roles
{: #iam-roles-concept}

Los roles de acceso de Cloud IAM permiten a un usuario completar tareas específicas en el recurso definido en la política. Hay dos tipos de roles de acceso: gestión de plataforma y acceso de servicio. 

Los roles de gestión de plataforma definen las acciones permitidas para gestionar recursos a nivel de plataforma, como el acceso de usuario y la creación de instancias de servicio. Los roles de plataforma también se aplican a las acciones que se pueden llevar a cabo en el contexto de los servicios de gestión de cuentas, como invitar y eliminar usuarios, gestionar grupos de acceso, gestionar ID de servicio y ofertas de catálogo privadas. 

Los roles de acceso al servicio definen las acciones permitidas dentro del contexto del uso del servicio, como llamar a las API de servicio. Estos roles se personalizan en función del servicio seleccionado en la política.

### Acciones
{: #iam-roles-actions}

Las acciones se correlacionan con los roles de Cloud IAM para permitir a los usuarios realizar solo tareas específicas cuando se les asignan los diferentes roles. Las acciones permitidas para cada rol pueden cambiar en función del servicio al que se está accediendo puesto que cada servicio define cómo se correlaciona ese rol con el uso del servicio.

### Sistema de gestión de acceso
{: #access-management-system}

El sistema de control de Cloud IAM permite o deniega acciones de usuarios en el contexto de un servicio en función de la política asignada. Cuando un usuario intenta completar una acción específica, el sistema de control utiliza los atributos definidos en la política para determinar si el usuario tiene permiso para realizar esa tarea.
