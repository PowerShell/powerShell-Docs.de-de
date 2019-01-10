---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: WaitForSome-Ressource in DSC
ms.openlocfilehash: 906375a8fcf9b87d4b7487e63e6fae3f05b86d0d
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047260"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="2ac39-103">WaitForSome-Ressource in DSC</span><span class="sxs-lookup"><span data-stu-id="2ac39-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="2ac39-104">Gilt für: Windows PowerShell 5.0 und höher</span><span class="sxs-lookup"><span data-stu-id="2ac39-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="2ac39-105">Die DSC-Ressource (Desired State Configuration) **WaitForAny** kann innerhalb eines Knotenblocks in einer [DSC-Konfiguration](../../../configurations/configurations.md) verwendet werden, um Abhängigkeiten von Konfigurationen auf anderen Knoten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2ac39-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="2ac39-106">Diese Ressource ist erfolgreich, wenn sich die mit der Eigenschaft **ResourceName** angegebene Ressource auf einer Mindestanzahl von Knoten (angegeben durch **NodeCount**), die durch die Eigenschaft **NodeName** definiert sind, im gewünschten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="2ac39-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="2ac39-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ac39-107">Syntax</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

## <a name="properties"></a><span data-ttu-id="2ac39-108">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2ac39-108">Properties</span></span>

|  <span data-ttu-id="2ac39-109">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2ac39-109">Property</span></span>  |  <span data-ttu-id="2ac39-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ac39-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="2ac39-111">NodeCount</span><span class="sxs-lookup"><span data-stu-id="2ac39-111">NodeCount</span></span>| <span data-ttu-id="2ac39-112">Die Mindestanzahl von Knoten, die sich im gewünschten Zustand befinden muss, damit diese Ressource erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2ac39-112">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="2ac39-113">NodeName</span><span class="sxs-lookup"><span data-stu-id="2ac39-113">NodeName</span></span>| <span data-ttu-id="2ac39-114">Die Zielknoten der Ressource für die Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="2ac39-114">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="2ac39-115">Ressourcenname</span><span class="sxs-lookup"><span data-stu-id="2ac39-115">ResourceName</span></span>| <span data-ttu-id="2ac39-116">Der Ressourcenname für die Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="2ac39-116">The resource name to depend on.</span></span> <span data-ttu-id="2ac39-117">Wenn diese Ressource zu einer anderen Konfiguration gehört, müssen Sie den Namen als „[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]“ formatieren.</span><span class="sxs-lookup"><span data-stu-id="2ac39-117">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="2ac39-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="2ac39-118">RetryIntervalSec</span></span>| <span data-ttu-id="2ac39-119">Die Anzahl von Sekunden bis zu einem Neuversuch.</span><span class="sxs-lookup"><span data-stu-id="2ac39-119">The number of seconds before retrying.</span></span> <span data-ttu-id="2ac39-120">Der Mindestwert lautet 1.</span><span class="sxs-lookup"><span data-stu-id="2ac39-120">Minimum is 1.</span></span>|
| <span data-ttu-id="2ac39-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="2ac39-121">RetryCount</span></span>| <span data-ttu-id="2ac39-122">Die maximal zulässige Anzahl von Neuversuchen.</span><span class="sxs-lookup"><span data-stu-id="2ac39-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="2ac39-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="2ac39-123">ThrottleLimit</span></span>| <span data-ttu-id="2ac39-124">Die Anzahl von Computern, die gleichzeitig eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="2ac39-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="2ac39-125">Per Voreinstellung wird der new-cimsession-Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ac39-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="2ac39-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2ac39-126">DependsOn</span></span> | <span data-ttu-id="2ac39-127">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2ac39-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2ac39-128">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, __ResourceName__ und dessen Typ __ResourceType__ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="2ac39-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="2ac39-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2ac39-129">PsDscRunAsCredential</span></span> | <span data-ttu-id="2ac39-130">Informationen finden Sie unter [Verwenden von DSC mit Benutzeranmeldeinformationen](https://docs.microsoft.com/powershell/dsc/runasuser).</span><span class="sxs-lookup"><span data-stu-id="2ac39-130">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |

## <a name="example"></a><span data-ttu-id="2ac39-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ac39-131">Example</span></span>

<span data-ttu-id="2ac39-132">Ein Beispiel zur Verwendung dieser Ressource finden Sie unter [Angeben knotenübergreifender Abhängigkeiten](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="2ac39-132">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>