---
title: IMetaDataTables::GetNumTables-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNumTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 23aa78f8daf649c4fdba218cdc964e4e47070580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="c7246-102">IMetaDataTables::GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="c7246-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="c7246-103">Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.</span><span class="sxs-lookup"><span data-stu-id="c7246-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7246-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7246-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7246-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="c7246-106">[out] Ein Zeiger auf die Anzahl der Tabellen im aktuellen Gültigkeitsbereich der Instanz.</span><span class="sxs-lookup"><span data-stu-id="c7246-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7246-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7246-107">Requirements</span></span>  
 <span data-ttu-id="c7246-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7246-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7246-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c7246-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7246-110">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c7246-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7246-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7246-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7246-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7246-112">See Also</span></span>  
 [<span data-ttu-id="c7246-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7246-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="c7246-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7246-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)