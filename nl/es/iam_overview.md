---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: IBM Cloud IAM, user identities, service ID, policies, access management, roles, actions

subcollection: iam


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Conceptos de IAM
{: #iamconcepts}

## Identidad
{: #identity}

El concepto de identidad en {{site.data.keyword.Bluemix_notm}} IAM consta de los siguientes componentes:

<dl>
<dt>Identidades de usuario</dt>
<dd>Todos los usuarios están identificados por su IBMid.</dd>
<dt>Identidades de servicio y app</dt>
<dd>Los ID de servicio son las características de Cloud IAM utilizadas para proporcionar una identidad separada para servicios y aplicaciones. Puede crear un ID de servicio para que lo utilice una aplicación que necesita acceso a sus servicios de {{site.data.keyword.Bluemix_notm}} para que no se tengan que utilizar credenciales de usuario individual.</dd>
<dt>Claves de API</dt>
<dd>Las claves de API de {{site.data.keyword.cloud_notm}} están disponibles a través de Cloud IAM para que las utilice para autenticar utilizando API o CLI como usuario o ID de servicio. Estas claves de API están proporcionadas a través de Cloud IAM y, por lo tanto, no se pueden utilizar de forma general para autenticarse con el IBMid fuera de IBM Cloud. Un usuario también puede tener una sola clave de API de la infraestructura clásica que se puede utilizar para acceder a las API de la infraestructura clásica; sin embargo, esto no es necesario, ya que puede utilizar las claves de API de {{site.data.keyword.cloud_notm}} para acceder a las mismas API. </dd>
<dt>Recursos</dt>
<dd>Los recursos de {{site.data.keyword.Bluemix_notm}} se identifican por sus nombres de recurso de nube (CRN). Para obtener más información, consulte [Nombres de recursos de nube](/docs/overview?topic=overview-crn#crn).</dd>
</dl>

## Gestión de acceso
{: #am}

El concepto de gestión de acceso en {{site.data.keyword.Bluemix_notm}} consta de unos cuantos componentes interrelacionados, incluyendo usuarios, recursos, políticas, roles, acciones y el sistema de control de Cloud IAM, que permite a los usuarios realizar acciones en recursos dentro de una cuenta.

Puede revisar la siguiente lista para obtener más información sobre estos componentes de Cloud IAM:

<dl>
<dt>Usuarios</dt>
<dd>Todos los usuarios dentro de una cuenta están identificados por sus IBMid. Se puede invitar a los usuarios a la cuenta y darles acceso a recursos. El acceso se puede asignar a recursos individuales, a nivel de instancia, o a un conjunto de recursos organizado en un grupo de recursos de cuenta.</dd>
<dt>Grupo de acceso</dt>
<dd>El propietario de la cuenta puede crear un grupo de usuarios y de ID de servicios para que sea posible asignar el mismo acceso a todas las entidades dentro del grupo con una única política.</dd>
<dt>Recursos</dt>
<dd>Los recursos de cuenta son las ofertas de servicio de suministro seleccionadas del catálogo o los recursos granulares dentro de una instancia de servicio.</dd>
<dt>Políticas</dt>
<dd>Las políticas determinan cómo se otorga permisos a usuarios, ID de servicio o grupos de acceso en la cuenta para acceder a los recursos de la cuenta. Las políticas incluyen un sujeto, un destino y un rol. El sujeto es el usuario, el ID de servicio o el grupo de acceso al que está proporcionando acceso. El objetivo de la política es el recurso al que desea proporcionar acceso. Y, los roles son la forma de definir el nivel de acceso o las acciones permitidas en el objetivo de la política. Hay distintos tipos de políticas que permiten acceder a recursos de cuenta: una política de grupo de recursos, una política de instancia de recursos, una política de toda la cuenta para acceder a todos los servicios habilitados para Identity and Access y una política sobre un servicio de gestión de la cuenta o sobre todos ellos. En función de sus selecciones, es posible que disponga de opciones de configuración personalizadas como la definición de acceso en recursos en una región específica o la definición de acceso al nivel granular de un recurso específico de servicio dentro de una instancia.</dd>
<dt>Roles</dt>
<dd>Los roles de acceso de Cloud IAM permiten a un usuario completar tareas específicas en el recurso definido en la política. Hay dos tipos de roles de acceso: gestión de plataforma y acceso de servicio. Los roles de gestión de plataforma definen las acciones permitidas para gestionar recursos a nivel de plataforma, como el acceso de usuario y la creación de instancias de servicio, por ejemplo. Los roles de plataforma también se aplican a las acciones que se pueden llevar a cabo en el contexto de los servicios de gestión de cuentas, como invitar y eliminar usuarios, gestionar grupos de acceso, gestionar ID de servicio y ofertas de catálogo privadas. Además, los roles de acceso de servicio definen las acciones permitidas dentro del contexto del uso del servicio, como llamar a las API de servicio. Estos roles se personalizan en función del servicio seleccionado en la política.</dd>
<dt>Acciones</dt>
<dd>Las acciones se correlacionan con los roles de Cloud IAM para permitir a los usuarios realizar solo tareas específicas cuando se les asignan los diferentes roles. Las acciones permitidas para cada rol pueden cambiar en función del servicio al que se está accediendo puesto que cada servicio define cómo se correlaciona ese rol con el uso del servicio. </dd>
<dt>Sistema de gestión de acceso</dt>
<dd>El sistema de control de Cloud IAM permite o deniega acciones de usuarios en el contexto de un servicio en función de la política asignada. Cuando un usuario intenta completar una acción específica, el sistema de control utiliza los atributos definidos en la política para determinar si el usuario tiene permiso para realizar esa tarea.</dd>
</dl>
