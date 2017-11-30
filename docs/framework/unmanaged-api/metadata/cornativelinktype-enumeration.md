---
title: CorNativeLinkType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8da034590bc5e0b2cbd9456d9d5b4ef4970f259
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="767e4-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="767e4-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="767e4-103">Stellt Werte bereit, die den im nativen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="767e4-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="767e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="767e4-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="767e4-105">Member</span><span class="sxs-lookup"><span data-stu-id="767e4-105">Members</span></span>  
  
|<span data-ttu-id="767e4-106">Member</span><span class="sxs-lookup"><span data-stu-id="767e4-106">Member</span></span>|<span data-ttu-id="767e4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="767e4-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="767e4-108">Gibt an, dass keines der Schlüsselwörter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="767e4-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="767e4-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="767e4-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="767e4-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben wird</span><span class="sxs-lookup"><span data-stu-id="767e4-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="767e4-111">Gibt an, dass ein Schlüsselwort "Auto" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="767e4-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="767e4-112">Gibt an, dass ein OLE-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="767e4-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="767e4-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="767e4-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="767e4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="767e4-114">Requirements</span></span>  
 <span data-ttu-id="767e4-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="767e4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767e4-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="767e4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="767e4-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="767e4-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="767e4-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="767e4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767e4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="767e4-119">See Also</span></span>  
 [<span data-ttu-id="767e4-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="767e4-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)