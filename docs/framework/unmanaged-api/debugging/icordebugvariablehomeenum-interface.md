---
title: ICorDebugVariableHomeEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum
helpviewer_keywords: ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e64a52ca70606f83138b636f7ccb62ba18908f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="e7d9e-102">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7d9e-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="e7d9e-103">Stellt einen Enumerator an lokale Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7d9e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e7d9e-104">Methods</span></span>  
  
|<span data-ttu-id="e7d9e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e7d9e-105">Method</span></span>|<span data-ttu-id="e7d9e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7d9e-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e7d9e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="e7d9e-108">Ruft die angegebene Anzahl von [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanzen, die Informationen über die lokalen Variablen und Argumente in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7d9e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7d9e-109">Remarks</span></span>  
 <span data-ttu-id="e7d9e-110">Die `ICorDebugVariableHomeEnum` Schnittstelle implementiert ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="e7d9e-111">Ein `ICorDebugVariableHomeEnum` Instanz wird mit aufgefüllt [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanzen durch Aufrufen der [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="e7d9e-112">Jede [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanzen in der Auflistung darstellt, eine lokale Variable oder ein Argument in einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="e7d9e-113">Die [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte in der Auflistung aufgelistet werden können, durch Aufrufen der [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e7d9e-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d9e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7d9e-114">Requirements</span></span>  
 <span data-ttu-id="e7d9e-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7d9e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d9e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7d9e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7d9e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7d9e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7d9e-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7d9e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d9e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d9e-119">See Also</span></span>  
 [<span data-ttu-id="e7d9e-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7d9e-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="e7d9e-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e7d9e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)