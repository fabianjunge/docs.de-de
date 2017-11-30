---
title: ICorPublish::EnumProcesses-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c556cffa95b4d6471b8a07954ec7b93ddbdb21c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="1843d-102">ICorPublish::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="1843d-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="1843d-103">Ruft einen Enumerator für die verwaltete Prozesse auf diesem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1843d-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1843d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1843d-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1843d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1843d-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="1843d-106">Der Wert der [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) -Enumeration, der den Typ des Prozesses abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1843d-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="1843d-107">In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.</span><span class="sxs-lookup"><span data-stu-id="1843d-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="1843d-108">Ein Zeiger auf die Adresse des ein [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) -Instanz, die der Enumerator der Prozesse ist.</span><span class="sxs-lookup"><span data-stu-id="1843d-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1843d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1843d-109">Remarks</span></span>  
 <span data-ttu-id="1843d-110">Der Enumerator die Auflistung der Prozesse basiert auf einem Snapshot der Prozesse, die beim Ausführen der `EnumProcesses` -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1843d-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="1843d-111">Der Enumerator enthält keine Prozesse, die vor dem Beenden oder starten, nachdem `EnumProcesses` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1843d-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="1843d-112">Die `EnumProcesses` -Methode möglicherweise mehr als einmal aufgerufen werden, für dieses [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) Instanz eine neue Auflistung Prozesse auf dem neuesten Stand zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1843d-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="1843d-113">Vorhandene Sammlungen nicht beeinträchtigt durch nachfolgende Aufrufe von der `EnumProcesses` Methode.</span><span class="sxs-lookup"><span data-stu-id="1843d-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1843d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1843d-114">Requirements</span></span>  
 <span data-ttu-id="1843d-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1843d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1843d-116">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1843d-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1843d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1843d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1843d-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1843d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1843d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1843d-119">See Also</span></span>  
 [<span data-ttu-id="1843d-120">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1843d-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)