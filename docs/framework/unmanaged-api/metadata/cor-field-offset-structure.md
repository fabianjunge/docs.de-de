---
title: COR_FIELD_OFFSET-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD_OFFSET
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_FIELD_OFFSET
helpviewer_keywords: COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8e821a9d4ffa5054f687eff7360bc8d7cefb9f09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="9a31b-102">COR_FIELD_OFFSET-Struktur</span><span class="sxs-lookup"><span data-stu-id="9a31b-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="9a31b-103">Speichert den Offset des angegebenen Felds innerhalb einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="9a31b-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a31b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a31b-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="9a31b-105">Member</span><span class="sxs-lookup"><span data-stu-id="9a31b-105">Members</span></span>  
  
|<span data-ttu-id="9a31b-106">Member</span><span class="sxs-lookup"><span data-stu-id="9a31b-106">Member</span></span>|<span data-ttu-id="9a31b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a31b-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="9a31b-108">Ein `mdFieldDef` Metadatentoken, das das Feld darstellt.</span><span class="sxs-lookup"><span data-stu-id="9a31b-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="9a31b-109">Das Feld offset innerhalb der Klasse.</span><span class="sxs-lookup"><span data-stu-id="9a31b-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a31b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a31b-110">Remarks</span></span>  
 <span data-ttu-id="9a31b-111">[IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) und [IMetaDataEmit:: SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) Methoden nehmen einen Versionsparameter vom Typ `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="9a31b-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a31b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a31b-112">Requirements</span></span>  
 <span data-ttu-id="9a31b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a31b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a31b-114">**Header:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9a31b-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="9a31b-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a31b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a31b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a31b-116">See Also</span></span>  
 [<span data-ttu-id="9a31b-117">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="9a31b-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="9a31b-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a31b-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9a31b-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a31b-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)