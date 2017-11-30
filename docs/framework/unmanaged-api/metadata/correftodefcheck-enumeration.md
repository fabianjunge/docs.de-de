---
title: CorRefToDefCheck-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRefToDefCheck
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRefToDefCheck
helpviewer_keywords: CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5144cd3ac261647c04ec7e3e27e28618c94fb439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="bbaf2-102">CorRefToDefCheck-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bbaf2-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="bbaf2-103">Gibt Flags an, mit denen gesteuert wird, welche Elemente, auf die verwiesen wird, zur Optimierung des Codes in ihre Definitionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbaf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbaf2-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="bbaf2-105">Member</span><span class="sxs-lookup"><span data-stu-id="bbaf2-105">Members</span></span>  
  
|<span data-ttu-id="bbaf2-106">Member</span><span class="sxs-lookup"><span data-stu-id="bbaf2-106">Member</span></span>|<span data-ttu-id="bbaf2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbaf2-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="bbaf2-108">Gibt an, dass Typverweise und Elementverweise in Definitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="bbaf2-109">Dies ist der Standardwert (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="bbaf2-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="bbaf2-110">Gibt an, dass alle referenzierten Elemente in Definitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="bbaf2-111">Gibt an, dass keine referenzierten Elemente in Definitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="bbaf2-112">Gibt an, dass nur Typverweise Typdefinitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="bbaf2-113">Gibt an, dass nur Member verweisen auf Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="bbaf2-114">D. h. sollte Elementverweisen Methodendefinitionen oder Felddefinitionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="bbaf2-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bbaf2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbaf2-115">Requirements</span></span>  
 <span data-ttu-id="bbaf2-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbaf2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbaf2-117">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bbaf2-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bbaf2-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbaf2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbaf2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbaf2-119">See Also</span></span>  
 [<span data-ttu-id="bbaf2-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="bbaf2-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)