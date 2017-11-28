---
title: ICorDebugHeapValue3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3
helpviewer_keywords: ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5531689a3a4ba66fddfc98cadec7dc8d51c8629a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="8d550-102">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d550-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="8d550-103">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d550-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="8d550-104">Diese Schnittstelle erweitert die ICorDebugHeapValue und ICorDebugHeapValue2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8d550-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d550-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8d550-105">Methods</span></span>  
  
|<span data-ttu-id="8d550-106">Methode</span><span class="sxs-lookup"><span data-stu-id="8d550-106">Method</span></span>|<span data-ttu-id="8d550-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d550-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d550-108">GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="8d550-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="8d550-109">Gibt den verwalteten Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="8d550-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="8d550-110">GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="8d550-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="8d550-111">Stellt eine geordnete Liste von Threads in der Warteschlange auf das Ereignis, das einen Monitorsperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8d550-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d550-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d550-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d550-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8d550-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d550-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d550-114">Requirements</span></span>  
 <span data-ttu-id="8d550-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d550-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d550-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d550-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d550-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d550-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d550-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d550-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d550-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d550-119">See Also</span></span>  
 [<span data-ttu-id="8d550-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d550-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8d550-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8d550-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)